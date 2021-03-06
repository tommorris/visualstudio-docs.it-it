---
title: Diagnosticare i problemi dopo la distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a3463eab-a352-4d17-8551-adbaad526db0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cd3313957ae1cccbd3f56b1fafacfed58570531f
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542507"
---
# <a name="diagnose-problems-after-deployment-using-intellitrace"></a>Diagnosticare i problemi dopo la distribuzione usando IntelliTrace

Per diagnosticare i problemi nell'app Web ASP.NET dopo la distribuzione usando IntelliTrace, includere le informazioni di compilazione nella versione per consentire a Visual Studio di trovare automaticamente i file di origine corretti e i file di simboli necessari per il debug del log IntelliTrace.

 Se si usa Microsoft Monitoring Agent per controllare IntelliTrace, è necessario configurare il monitoraggio delle prestazioni delle applicazioni nel server Web. In questo modo vengono registrati gli eventi di diagnostica durante l'esecuzione dell'applicazione e vengono salvati gli eventi nel file di log IntelliTrace. È quindi possibile esaminare gli eventi in Visual Studio Enterprise (ma non edizioni Professional o Community), passare al codice nel punto in cui si è verificato l'evento, esaminare i valori registrati in quel momento e spostarsi avanti o indietro lungo il codice che è stato eseguito. Dopo aver trovato e risolto il problema, ripetere il ciclo per compilare, rilasciare e monitorare la versione per risolvere eventuali problemi futuri più tempestivamente e rapidamente.

 ![Codice, compilare, rilasciare, monitoraggio, diagnosi, correzione](../debugger/media/ffr_cycle.png "FFR_Cycle")

 **È necessario:**

-   Visual Studio, Azure DevOps o Team Foundation Server 2017, 2015, 2013, 2012 o 2010 per configurare la compilazione

-   Microsoft Monitoring Agent per monitorare i dati di diagnostica della registrazione dell'applicazione

-   Visual Studio Enterprise (ma non edizioni Professional o Community) per esaminare i dati diagnostici ed eseguire il debug del codice con IntelliTrace

##  <a name="SetUpBuild"></a> Passaggio 1: Includere le informazioni con il rilascio di compilazione
 Configurare il processo di compilazione per creare un manifesto di compilazione (*buildinfo. config* file) per il web del progetto e includere il manifesto con il rilascio. Il manifesto contiene informazioni relative al progetto, al controllo del codice sorgente e al sistema di compilazione usati per creare una specifica build. Con queste informazioni, è possibile trovare tramite Visual Studio l'origine e i simboli corrispondenti, dopo aver aperto il log IntelliTrace per esaminare gli eventi registrati.

###  <a name="AutomatedBuild"></a> Creare il manifesto di compilazione per una compilazione automatica con Team Foundation Server

 Seguire questi passaggi se si usa il controllo della versione di Team Foundation o Git.

####  <a name="TFS2017"></a> Azure DevOps e Team Foundation Server 2017

Visual Studio 2017 non include il *buildinfo. config* file, che è stato deprecato e quindi rimosso. Per eseguire il debug di App web ASP.NET dopo la distribuzione, usare uno dei metodi seguenti:

* Per la distribuzione in Azure, usare [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/).

* Se si desidera utilizzare IntelliTrace, aprire il progetto in Visual Studio e caricare i file di simboli dalla compilazione corrisponda. È possibile caricare i file di simboli dal **moduli** finestra o configurando i simboli nel **Tools** > **opzioni** > **debug**   >  **Simboli**.


####  <a name="TFS2013"></a> Team Foundation Server 2013
 Configurare la pipeline di compilazione per aggiungere i percorsi dell'origine, compilazione e simboli al manifesto di compilazione (file buildinfo. config). Team Foundation Build crea automaticamente questo file e lo inserisce nella cartella di output del progetto.

1.  [Modificare la pipeline di compilazione o creare una nuova pipeline di compilazione.](/azure/devops/pipelines/get-started-designer?view=vsts)

     ![Visualizza compilazione della pipeline in TFS 2013](../debugger/media/ffr_tfs2013viewbuilddefinition.png "FFR_TFS2013ViewBuildDefinition")

2.  Scegliere il modello predefinito (TfvcTemplate.12.xaml) o il proprio modello personalizzato.

     ![Scegliere il modello di processo di compilazione &#45; TFS 2013](../debugger/media/ffr_tfs2013buildprocesstemplate.png "FFR_TFS2013BuildProcessTemplate")

3.  Specificare dove salvare il file dei simboli (PDB) in modo da indicizzare automaticamente l'origine.

     Se si usa un modello personalizzato, verificare che disponga di un'attività per l'indicizzazione dell'origine. In seguito verrà aggiunto un argomento MSBuild per specificare il percorso in cui salvare i file dei simboli.

     ![Impostare il percorso dei simboli nella pipeline di compilazione TFS 2013](../debugger/media/ffr_tfs2013builddefsymbolspath.png "FFR_TFS2013BuildDefSymbolsPath")

     Per altre informazioni sui simboli, vedere [pubblicare i dati dei simboli](/azure/devops/pipelines/tasks/build/index-sources-publish-symbols?view=vsts).

4.  Aggiungere questo argomento MSBuild per inserire i percorsi di TFS e simboli nel file manifesto di compilazione:

     **/p:IncludeServerNameInBuildInfo = true**

     Chiunque possa aver accesso al server Web può visualizzare questi percorsi nel manifesto di compilazione. Assicurarsi che il server di origine sia sicuro.

5.  Se si usa un modello personalizzato, aggiungere questo argomento MSBuild per specificare dove salvare il file dei simboli:

     **/p: buildsymbolstorepath =**\<*percorso dei simboli*>

     ![Includere informazioni del server di compilazione nella definizione di compilazione TFS 2013](../debugger/media/ffr_tfs2013builddefincludeserverinfo.png "FFR_TFS2013BuildDefIncludeServerInfo")

     Aggiungere le righe seguenti al file di progetto Web (estensione csproj o vbproj):

    ```xml
    <!-- Import the targets file. Change the folder location as necessary. -->
       <Import Project=""$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v$(VisualStudioVersion)\BuildInfo\Microsoft.VisualStudio.ReleaseManagement.BuildInfo.targets" />

    ```

     Chiunque possa aver accesso al server Web può visualizzare questi percorsi nel manifesto di compilazione. Assicurarsi che il server di origine sia sicuro.

6.  Eseguire una nuova compilazione.

    Passare a [passaggio 2: rilasciare l'app](#DeployRelease)

####  <a name="TFS2012_2010"></a> Team Foundation Server 2012 o 2010
 Seguire questi passaggi per creare automaticamente il manifesto di compilazione (file BuildInfo.config) per il progetto e inserire il file nella cartella di output del progetto. Il file viene visualizzato come "*ProjectName*.BuildInfo.config" nella cartella di output ma viene rinominato "BuildInfo.config" nella cartella di distribuzione dopo la pubblicazione dell'applicazione.

1.  Installare Visual Studio 2013 (qualsiasi edizione) nel server Team Foundation Build.

2.  Nella pipeline di compilazione, specificare dove salvare i simboli in modo da indicizzare automaticamente l'origine.

     Se si usa un modello personalizzato, verificare che disponga di un'attività per l'indicizzazione dell'origine.

3.  Aggiungere gli argomenti MSBuild alla pipeline di compilazione:

    -   **/p:VisualStudioVersion = 12.0**

    -   **/p:MSBuildAssemblyVersion = 12.0**

    -   **/TV:12.0**

    -   **/p:IncludeServerNameInBuildInfo = true**

    -   **/p: buildsymbolstorepath =**\<*percorso dei simboli*>

4.  Eseguire una nuova compilazione.

    Passare a [passaggio 2: rilasciare l'app](#DeployRelease)

###  <a name="ManualBuild"></a> Creare il manifesto di compilazione per una compilazione manuale usando Visual Studio
 Seguire questi passaggi per creare automaticamente il manifesto di compilazione (file BuildInfo.config) per il progetto e inserire il file nella cartella di output del progetto. Il file viene visualizzato come "*ProjectName*.BuildInfo.config" nella cartella di output ma viene rinominato "BuildInfo.config" nella cartella di distribuzione dopo la pubblicazione dell'applicazione.

1.  Scaricare il progetto Web in **Esplora soluzioni**.

2.  Aprire il file di progetto (estensione .csproj o .vbproj). Aggiungere queste righe:

    ```xml
    <!-- **************************************************** -->
    <!-- Build info -->
    <PropertyGroup>
       <!-- Generate the BuildInfo.config file -->
       <GenerateBuildInfoConfigFile>True</GenerateBuildInfoConfigFile>
       <!-- Include server name in build info -->
       <IncludeServerNameInBuildInfo>True</IncludeServerNameInBuildInfo>
       <!-- Include the symbols path so Visual Studio can find the matching deployed code when you start debugging. -->
       <BuildSymbolStorePath><path to symbols></BuildSymbolStorePath>
    </PropertyGroup>
    <!-- **************************************************** -->
    ```

3.  Archiviare il file di progetto aggiornato.

4.  Eseguire una nuova compilazione.

    Passare a [passaggio 2: rilasciare l'app](#DeployRelease)

###  <a name="MSBuild"></a> Creare il manifesto di compilazione per una compilazione manuale usando MSBuild.exe
 Aggiungere gli argomenti di compilazione quando si eseguirà una compilazione:

 **/p:GenerateBuildInfoConfigFile = true**

 **/p:IncludeServerNameInBuildInfo = true**

 **/p: buildsymbolstorepath =**\<*percorso dei simboli*>

##  <a name="DeployRelease"></a> Passaggio 2: Rilasciare l'app
 Se si usa la [pacchetto di Web. deploy](https://msdn.microsoft.com/library/dd394698.aspx) creato dal processo di compilazione per distribuire l'app, il manifesto di compilazione viene rinominato automaticamente da "*ProjectName*. Buildinfo. config"a"Buildinfo. config"e viene inserito nella stessa cartella Web. config file dell'app sul server web.

 Se vengono usati altri metodi per distribuire l'applicazione, assicurarsi che il manifesto di compilazione sia rinominato da "*ProjectName*.BuildInfo.config" a "BuildInfo.config" inserito nella stessa cartella del file Web.config dell'applicazione, nel server Web.

## <a name="step-3-monitor-your-app"></a>Passaggio 3: Monitorare l'applicazione
 Impostare il monitoraggio delle prestazioni dell'applicazione sul server Web in modo tale da poter monitorare l'insorgere di problemi nell'applicazione, registrare eventi diagnostici e salvare tali eventi nel file di log IntelliTrace. Visualizzare [monitorare la versione per i problemi di distribuzione](../debugger/using-the-intellitrace-stand-alone-collector.md).

##  <a name="InvestigateEvents"></a> Passaggio 4: Individuare il problema
 È necessario che sia presente Visual Studio Enterprise nel computer di sviluppo o in un altro computer per esaminare gli eventi registrati ed eseguire il debug del codice con IntelliTrace. È inoltre possibile usare strumenti come CodeLens, mappe del debugger e mappe del codice per diagnosticare il problema.

### <a name="open-the-intellitrace-log-and-matching-solution"></a>Aprire il log IntelliTrace e la soluzione corrispondente

1.  Aprire il log IntelliTrace (file .iTrace) da Visual Studio Enterprise. In alternativa, fare doppio clic sul file se nello stesso computer è presente Visual Studio Enterprise.

2.  Scegliere **Apri soluzione** per fare in modo che Visual Studio apra automaticamente la soluzione o il progetto corrispondente, se il progetto non è stato compilato come parte di una soluzione. [D: i log IntelliTrace mancano le informazioni sull'applicazione distribuita. Per quale motivo? Quale operazione devo eseguire?](#InvalidConfigFile)

     Visual Studio esegue automaticamente lo shelving di qualsiasi modifica in sospeso all'apertura della soluzione o del progetto corrispondente. Per ottenere ulteriori dettagli su questo shelveset, aprire la finestra **Output** o **Team Explorer**.

     Prima di apportare modifiche, verificare di disporre dell'origine corretta. Se si usano i rami, è possibile che il ramo su cui si sta lavorando sia diverso rispetto a quello in cui Visual Studio cerca l'origine corrispondente, ad esempio il ramo della versione.

     ![Apri soluzione dal log di IntelliTrace](../debugger/media/ffr_itsummarypageopensolution.png "FFR_ITSummaryPageOpenSolution")

     Se è presente un'area di lavoro mappata per questa soluzione o questo progetto, Visual Studio la seleziona per inserirvi l'origine trovata.

     ![Apri dal controllo del codice sorgente all'area di lavoro mappata](../debugger/media/ffr_openprojectfromsourcecontrol_mapped.png "FFR_OpenProjectFromSourceControl_Mapped")

     In caso contrario, scegliere un'altra area di lavoro già mappata o crearne una nuova. Visual Studio esegue il mapping dell'intero ramo a quest'area di lavoro.

     ![Apri dal controllo del codice sorgente &#45; Crea nuova area di lavoro](../debugger/media/ffr_openprojectfromsourcecontrol_createnewworkspace.png "FFR_OpenProjectFromSourceControl_CreateNewWorkspace")

     Per creare un'area di lavoro con mapping specifici o un nome diverso dal nome del computer, scegliere **Gestisci**.

     [D: perché Visual Studio che l'area di lavoro selezionata è inadatta?](#IneligibleWorkspace)

     [D: perché non è possibile continuare finché non si sceglie una raccolta team o una raccolta diversa?](#ChooseTeamProject)

### <a name="diagnose-a-performance-problem"></a>Identificare un problema di prestazioni

1.  In **Violazioni prestazioni**esaminare gli eventi di prestazioni registrati, i relativi tempi di esecuzione totali e altre informazioni sugli eventi. Esaminare ulteriori dettagli sui metodi chiamati durante un evento di prestazioni specifico.

     ![Visualizzare i dettagli evento prestazioni](../debugger/media/ffr_itsummarypageperformance.png "FFR_ITSummaryPagePerformance")

     È inoltre sufficiente fare doppio clic sull'evento.

2.  Nella pagina dell'evento rivedere i tempi di esecuzione per queste chiamate. Cercare una chiamata lenta nell'albero di esecuzione.

     Le chiamate più lente vengono visualizzate nella specifica sezione in caso di più chiamate, annidate o meno.

     Espandere tale chiamata per rivedere tutte le chiamate e i valori annidati registrati in quel momento. Avviare quindi il debug dalla chiamata.

     ![Avviare il debug dalla chiamata al metodo](../debugger/media/ffr_itsummarypageperformancemethodscalled.png "FFR_ITSummaryPagePerformanceMethodsCalled")

     È inoltre sufficiente fare doppio clic sulla chiamata.

     Se il metodo è incluso nel codice dell'applicazione, Visual Studio passa a tale metodo.

     ![Passare al codice dell'applicazione dall'evento prestazioni](../debugger/media/ffr_itsummarypageperformancegotocode.png "FFR_ITSummaryPagePerformanceGoToCode")

     È possibile esaminare altri valori registrati, lo stack di chiamate, eseguire un'istruzione alla volta nel codice o usare la finestra **IntelliTrace** per [spostarsi in avanti o indietro tra gli altri metodi](../debugger/intellitrace.md) chiamati durante questo evento di prestazioni.

    - [Che cos'è tutti gli altri eventi e informazioni riportati nel log IntelliTrace?](../debugger/using-saved-intellitrace-data.md)
    - [Quali altre operazioni posso eseguire da qui?](#WhatElse)
    - [Servono altre informazioni sugli eventi delle prestazioni?](https://blogs.msdn.microsoft.com/devops/2013/09/20/performance-details-in-intellitrace/)

### <a name="diagnose-an-exception"></a>Diagnosticare un'eccezione

1.  In **Dati eccezione**esaminare gli eventi di eccezione registrati, i relativi tipi, i messaggi e il momento in cui si sono verificate le eccezioni. Per esaminare il codice in dettaglio, avviare il debug dall'evento più recente in un gruppo di eccezioni.

     ![Avviare il debug da eventi di eccezione](../debugger/media/ffr_itsummarypageexception.png "FFR_ITSummaryPageException")

     È inoltre sufficiente fare doppio clic sull'evento.

     Se l'eccezione si è verificata nel codice dell'applicazione, Visual Studio passa a questa posizione.

     ![Passare al codice dell'applicazione da un evento di eccezione](../debugger/media/ffr_itsummarypageexceptiongotocode.png "FFR_ITSummaryPageExceptionGoToCode")

     È possibile esaminare altri valori registrati, lo stack di chiamate o usare la finestra **IntelliTrace** per [spostarsi in avanti o indietro tra gli altri eventi registrati](../debugger/intellitrace.md), il codice correlato e i valori registrati in questi specifici momenti.

     [Che cos'è tutti gli altri eventi e informazioni riportati nel log IntelliTrace?](../debugger/using-saved-intellitrace-data.md)

###  <a name="WhatElse"></a> Quali altre operazioni posso eseguire da qui?

-   [Ottenere altre informazioni su questo codice](../ide/find-code-changes-and-other-history-with-codelens.md). Per trovare i riferimenti a questo codice, la cronologia delle modifiche, risolvono bug correlati, gli elementi di lavoro, revisioni del codice o unit test - tutto senza uscire dall'editor - usare gli indicatori CodeLens nell'editor.

     ![CodeLens &#45; visualizzare i riferimenti a questo codice](../debugger/media/ffr_itsummarypageperformancecodelensreferences.png "FFR_ITSummaryPagePerformanceCodeLensReferences")

     ![CodeLens &#45; visualizzazione cronologia delle modifiche per questo codice](../debugger/media/ffr_itsummarypageperformancecodelensauthors.png "FFR_ITSummaryPagePerformanceCodeLensAuthors")

-   [Eseguire il mapping della posizione nel codice durante il debug.](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md) Per rilevare visivamente i metodi chiamati durante la sessione di debug, eseguire il mapping dello stack di chiamate.

     ![Eseguire il mapping dello stack di chiamate durante il debug](../debugger/media/ffr_itsummarypageperformancedebuggermap.png "FFR_ITSummaryPagePerformanceDebuggerMap")

###  <a name="FAQ"></a> Domande e risposte

####  <a name="WhyInclude"></a> D: perché include informazioni su my project, controllo del codice sorgente, compilazione e simboli versione?
 Visual Studio usa queste informazioni per trovare la soluzione e l'origine corrispondenti alla versione su cui si sta eseguendo il debug. Dopo aver aperto il log IntelliTrace e aver selezionato un evento per avviare il debug, Visual Studio usa simboli per trovare e visualizzare il codice dove si è verificato l'evento. È quindi possibile esaminare i valori registrati e spostarsi in avanti o indietro nell'esecuzione del codice.

 Se si usa TFS e queste informazioni non sono nel manifesto di compilazione (file buildinfo. config), Visual Studio cerca l'origine corrispondente e i simboli nel TFS attualmente connesso. Se Visual Studio non trova il TFS corretto o l'origine corrispondente, verrà richiesto di scegliere un altro TFS.

####  <a name="InvalidConfigFile"></a> D: i log IntelliTrace mancano le informazioni sull'applicazione distribuita. Per quale motivo? Che cosa si può fare?
 Questo può verificarsi quando la distribuzione viene effettuata dal computer di sviluppo oppure non si è connessi a TFS durante la distribuzione.

1.  Passare alla cartella di distribuzione del progetto.

2.  Trovare e aprire il manifesto di compilazione (file BuildInfo.config).

3.  Assicurarsi che il file contenga le informazioni richieste:

-   **ProjectName**

     Il nome del progetto in Visual Studio. Ad esempio:

    ```xml
    <ProjectName>FabrikamFiber.Extranet.Web</ProjectName>
    ```

-   **Della proprietà SourceControl è**

-   Le informazioni sul sistema di controllo del codice sorgente e queste proprietà richieste:

    -   **TFS**

        -   **ProjectCollectionUri**: URI per Team Foundation Server e l'insieme di progetti

        -   **ProjectItemSpec**: percorso del file del progetto dell'applicazione (estensione .csproj o .vbproj)

        -   **ProjectVersionSpec**: versione del progetto

         Ad esempio:

        ```xml
        <SourceControl type="TFS">
           <TfsSourceControl>
              <ProjectCollectionUri>http://fabrikamfiber:8080/tfs/FabrikamFiber</ProjectCollectionUri>
              <ProjectItemSpec>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectItemSpec>
              <ProjectVersionSpec>LFabrikamFiber_BuildAndPublish_20130813@$/WorkInProgress</ProjectVersionSpec>
           </TfsSourceControl>
        </SourceControl>
        ```

    -   **Git**

        -   **GitSourceControl**: posizione dello schema **GitSourceControl**

        -   **RepositoryUrl**: URI per Team Foundation Server, insieme di progetti e repository Git

        -   **ProjectPath**: percorso del file del progetto dell'applicazione (estensione .csproj o .vbproj)

        -   **CommitId**: ID del commit

         Ad esempio:

        ```xml
        <SourceControl type="Git">
           <GitSourceControl xmlns="http://schemas.microsoft.com/visualstudio/deploymentevent_git/2013/09">
              <RepositoryUrl>http://gittf:8080/tfs/defaultcollection/_git/FabrikamFiber</RepositoryUrl>
              <ProjectPath>/FabrikamFiber.CallCenter/FabrikamFiber.Web/FabrikamFiber.Web.csproj</ProjectPath>
              <CommitId>50662c96502dddaae5cd5ced962d9f14ec5bc64d</CommitId>
           </GitSourceControl>
        </SourceControl>
        ```

-   **Compila**

     Informazioni sul sistema di compilazione, `"TeamBuild"` o `"MSBuild"`e queste proprietà richieste:

    -   **BuildLabel** (per TeamBuild): nome e il numero della build. Questa etichetta viene usata anche come nome dell'evento di distribuzione. Per altre informazioni sui numeri di build, vedere [usare i numeri per assegnare nomi significativi alle compilazioni completate di build](/azure/devops/pipelines/build/options?view=vsts).

    -   **SymbolPath** (Consigliato): elenco di URI per le posizioni dei simboli (file PDB)separati da punto e virgola. Questi URI possono essere URL o UNC. In tal modo è più facile trovare i simboli corrispondenti, utili per il debug.

    -   **BuildReportUrl** (per TeamBuild): posizione del report di compilazione in TFS

    -   **BuildId** (per TeamBuild): URI per i dettagli della compilazione in TFS. Questo URI viene usato anche come ID per l'evento di distribuzione. Deve essere un ID univoco se non si usa TeamBuild.

    -   **BuiltSolution**: percorso del file di soluzione usato da Visual Studio per trovare e aprire la soluzione corrispondente. Si tratta del contenuto della proprietà **SolutionPath** MsBuild.

     Ad esempio:

    -   **TFS**

        ```xml
        <Build type="TeamBuild">
           <MsBuild>
              <BuildLabel kind="label">FabrikamFiber_BuildAndPublish_20130813.1</BuildLabel>
              <SymbolPath>\\fabrikamfiber\FabrikamFiber.CallCenter\Symbols</SymbolPath>
              <BuildReportUrl kind="informative, url" url="http://fabrikamfiber:8080/tfs/FabrikamFiber/_releasePipeline/FindRelease?buildUri=fabrikamfiber%3a%2f%2f%2fBuild%2fBuild%2f448">Build Report Url</BuildReportUrl>
              <BuildId kind="id">1c4444d2-518d-4673-a590-dce2773c7744,fabrikamfiber:///Build/Build/448</BuildId>
              <BuiltSolution>$/WorkInProgress/FabrikamFiber/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>
           </MsBuild>
        </Build>
        ```

    -   **Git**

        ```xml
        <Build type="MSBuild">
           <MSBuild>
              <SymbolPath>\\gittf\FabrikamFiber.CallCenter\Symbols</SymbolPath>
              <BuiltSolution>/FabrikamFiber.CallCenter/FabrikamFiber.CallCenter.sln</BuiltSolution>
           </MSBuild>
        </Build>
        ```

####  <a name="IneligibleWorkspace"></a> D: perché Visual Studio che l'area di lavoro selezionata è inadatta?
 **R:** L'area di lavoro selezionata non include mapping tra la cartella del controllo del codice sorgente e una cartella locale. Per creare un mapping per questa area di lavoro, scegliere **Gestisci**. In caso contrario, scegliere un'area di lavoro già mappata o creare una nuova area di lavoro.

 ![Apri dal controllo del codice sorgente con nessuna area di lavoro mappata](../debugger/media/ffr_openprojectfromsourcecontrol_notmapped.png "FFR_OpenProjectFromSourceControl_NotMapped")

####  <a name="ChooseTeamProject"></a> D: perché non è possibile continuare finché non si sceglie una raccolta team o una raccolta diversa?
 **R:** Questo può verificarsi per uno qualsiasi dei seguenti motivi:

-   Visual Studio non è connesso a TFS.

     ![Apri dal controllo del codice sorgente &#45; non connesso](../debugger/media/ffr_openprojectfromsourcecontrol_notconnected.png "FFR_OpenProjectFromSourceControl_NotConnected")

-   In Visual Studio non è stata trovata la soluzione o il progetto nella raccolta del team corrente.

     Quando il manifesto di compilazione file (\<*NomeProgetto*>. Buildinfo. config) non specifica in cui Visual Studio può individuare l'origine corrispondenza, Visual Studio Usa il TFS attualmente connesso per identificare la soluzione corrispondente o il progetto. Se la raccolta del team corrente non dispone dell'origine corrispondente, in Visual Studio viene richiesto di connettersi a una raccolta del team diversa.

-   Visual Studio non è stata trovata la soluzione o il progetto nella raccolta specificata dal file manifesto di compilazione (\<*NomeProgetto*>. Buildinfo. config).

     È possibile che il TFS specificato non disponga più dell'origine corrispondente o non esista più, probabilmente perché è stata eseguita la migrazione a un nuovo TFS. Se il TFS specificato non esiste, è possibile che si verifichi il timeout di Visual Studio dopo circa un minuto e viene quindi richiesto di connettersi a una raccolta diversa. Per continuare, connettersi al server TFS corretto.

     ![Apri dal controllo del codice sorgente &#45; migrate](../debugger/media/ffr_openprojectfromsourcecontrol_migrated.png "FFR_OpenProjectFromSourceControl_Migrated")

####  <a name="WhatWorkspace"></a> D: che cos'è un'area di lavoro?
 **R:** le [dell'area di lavoro viene memorizzata una copia dell'origine](/azure/devops/repos/tfvc/create-work-workspaces?view=vsts) in modo che è possibile sviluppare e svilupparla prima di archiviare il lavoro. Se non è già presente un'area di lavoro mappata specificatamente alla soluzione o al progetto trovato, in Visual Studio viene richiesto di scegliere un'area di lavoro disponibile oppure di crearne una nuova con il nome del computer in uso come nome predefinito dell'area di lavoro.

####  <a name="UntrustedSymbols"></a> D: perché viene visualizzato questo messaggio sui simboli non attendibili?
 ![Eseguire il debug con percorso dei simboli non attendibili? ](../debugger/media/ffr_ituntrustedsymbolpaths.png "FFR_ITUntrustedSymbolPaths")

 **R:** questo messaggio viene visualizzato quando il percorso dei simboli nel file manifesto di compilazione (\<*ProjectName*>. Buildinfo. config) non è incluso nell'elenco dei percorsi dei simboli attendibili. È possibile aggiungere il percorso dell'elenco di percorsi di simboli nelle opzioni del debugger.
