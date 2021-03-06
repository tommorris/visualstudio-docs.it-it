---
title: Debug di un modello di testo T4
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, troubleshooting
- text templates, debugging
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: fa551316e955b5e14d2b2030a7150a9b4daaab71
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31954352"
---
# <a name="debugging-a-t4-text-template"></a>Debug di un modello di testo T4
È possibile impostare i punti di interruzione nei modelli di testo. Per eseguire il debug di un modello di testo in fase di progettazione, salvare il file di modello di testo e quindi scegliere **Debug modello T4** nel menu di scelta rapida del file in Esplora soluzioni. Per eseguire il debug di un modello di testo in fase di esecuzione, è sufficiente eseguire il debug dell'applicazione a cui appartiene.

 Per eseguire il debug di un modello di testo, è necessario comprendere i passaggi per il processo di trasformazione del modello. Diversi tipi di errori possono verificarsi all'interno di ogni passaggio. I passaggi sono i seguenti.

|Passaggio|Modello della fase di progettazione: quando si verifica|Il modello in fase di esecuzione: quando si verifica|
|----------|--------------------------------------------|-----------------------------------------|
|Codice viene generato dal modello di testo.<br /><br /> Errori nelle direttive, o non corrispondente o disordered `<#...#>` tag.|Quando si salva il modello o richiamare la trasformazione di testo.|Quando si salva il modello o richiamare la trasformazione di testo.|
|Codice generato viene compilato.<br /><br /> Errori di compilazione nel codice del modello.|Immediatamente dopo il passaggio precedente.|Con il codice dell'applicazione.|
|Il codice viene eseguito.<br /><br /> Errori di run-time nel codice del modello.|Immediatamente dopo il passaggio precedente.|Quando l'applicazione viene eseguita e richiama il codice del modello.|

 Nella maggior parte dei casi, i numeri di riga nel codice del modello sono indicati nella segnalazione errori. Quando il report di errore fa riferimento a un nome file temporaneo, la causa è una parentesi non corrispondente nel codice del modello di testo.

 È possibile impostare punti di interruzione nei modelli di testo e il debug come di consueto.

## <a name="common-errors-and-fixes"></a>Errori comuni e correzioni
 Nella tabella seguente sono elencati gli errori più comuni e le correzioni.

|Messaggio di errore|Descrizione|Soluzione|
|-------------------|-----------------|--------------|
|Non è riuscito a caricare la classe base{0}' da cui trasformazione classe eredita.|Si verifica se non è possibile trovare la classe base specificata nel `inherits` parametro in una direttiva del modello. Il messaggio fornisce il numero di riga della direttiva template.|Verificare che la classe specificata esista e che l'assembly che è presente in sia specificato in una direttiva assembly.|
|Impossibile risolvere il testo di inclusione per file:{0}|Si verifica quando non è possibile trovare un modello incluso. Il messaggio fornisce il nome del file di inclusione richiesto.|Assicurarsi che il percorso del file è relativo al percorso del modello originale, o che il file è in un percorso a cui è registrato con l'host o che vi è un percorso completo del file.|
|Sono stati generati errori durante l'inizializzazione dell'oggetto trasformazione. La trasformazione non verrà eseguita.|Si verifica quando 'Initialize ()' della classe di trasformazione non è riuscito o ha restituito false.|Il codice nella funzione Initialize () deriva dalla classe di base di trasformazione specificata nella \<#@template#> direttiva e dai processori di direttiva. L'errore che ha causato initialize probabilmente l'errore è in elenco errori. Esaminare il motivo dell'errore. È possibile esaminare il codice generato per Initialize () seguendo le procedure per eseguire il debug di un modello.|
|L'assembly '{0}'per il processore di direttiva'{1}' non è stato concesso il set di autorizzazioni FullTrust. Per fornire i processori di direttiva, sono consentiti solo assembly attendibili. Il processore di direttiva non verrà caricato.|Si verifica quando il sistema non concede autorizzazioni FullTrust a un assembly contenente un processore di direttiva. Il messaggio fornisce il nome dell'assembly e il nome del processore di direttiva.|Assicurarsi di utilizzare solo assembly attendibili nel computer locale.|
|Il percorso '{0}' deve essere locale al computer o parte dell'area attendibile.|Si verifica quando una direttiva o una direttiva assembly fa riferimento a un file non presente nel computer locale o in area siti attendibili di rete.|Assicurarsi che la directory in cui la direttiva o direttive dell'assembly si trovano nell'area attendibile. È possibile aggiungere una directory di rete per l'area siti attendibili tramite Internet Explorer.|
|Più errori di sintassi, ad esempio "Non valido token ' catch'" o "uno spazio dei nomi non può contenere direttamente membri"|Troppe parentesi graffe di chiusura nel codice del modello. Il compilatore confonde con il codice di generazione standard.|Controllare il numero di parentesi graffe e le parentesi all'interno di delimitatori di codice di chiusura.|
|Cicli condizionali non compilato o eseguito correttamente. Ad esempio: `<#if (i>10)#> Number is: <#= i #>`.<br /><br /> Questo codice genera sempre il valore di è. Solo "numero è:" è condizionale.|In c#, utilizzare sempre le parentesi graffe per racchiudere i blocchi di testo incorporati nelle istruzioni di controllo.|Aggiungere le parentesi graffe: `<#if (i>10) { #>    Number is: <#= i #><# } #>`.|
|"Espressione troppo complessa" quando l'elaborazione di un modello in fase di progettazione o la compilazione di un modello di runtime (pre-elaborato).<br /><br /> [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] smette di funzionare quando si tenta di controllare il codice generato da un modello di runtime.|Blocco di testo è troppo lungo. Blocchi di testo T4 converte un'espressione di concatenazione di stringa, con una stringa letterale per ogni riga del modello. Blocchi di testo molto lunghi possono oltrepassare i limiti delle dimensioni del compilatore.|Suddividere il blocco di testo lungo con un blocco di espressione, ad esempio:<br /><br /> `<#= "" #>`|

## <a name="warning-descriptions-and-fixes"></a>Correzioni e le descrizioni di avviso
 Nella tabella seguente elenca gli avvisi più comuni insieme alle correzioni, se disponibile.

|Messaggio di avviso|Descrizione|Soluzione|
|---------------------|-----------------|--------------|
|Il caricamento del file di inclusione '{0}' ha restituito una stringa null o vuota.|Si verifica se un file di modello di testo incluso è vuoto. Il messaggio fornisce il nome del file del file incluso.|Rimuovere la direttiva di inclusione o assicurarsi che il file disponga di contenuto.|
|La compilazione di trasformazione:|Antepone la stringa per tutti gli errori o avvisi provenienti dal compilatore durante la compilazione della trasformazione. Questa stringa significa che il compilatore ha generato un errore o avviso.|Se si dispone di un problema durante la ricerca della DLL, occorre specificare il percorso completo o un nome sicuro completo se la DLL si trovi nella Global Assembly Cache.|
|Il parametro '{0}' esiste già nella direttiva. Il parametro duplicato verrà ignorato.|Si verifica quando un parametro è specificato più volte in una direttiva. Il messaggio fornisce il nome del parametro e il numero di riga della direttiva.|Rimuovere la specifica di parametro duplicato.|
|Si è verificato un errore durante il caricamento del file di inclusione '{0}'. La direttiva include verrà ignorata.|Si verifica quando non è possibile trovare un file specificato in un `include` direttiva. Il messaggio fornisce il nome del file e il numero di riga della direttiva.|Assicurarsi che il file di inclusione è presente nella stessa directory del file di modello di testo originale o in una delle directory di inclusione che sono registrati con l'host.|
|Una classe di base non valida specificata per la classe della trasformazione. La classe di base deve derivare da TextTransformation.|Si verifica quando il `inherits` parametro in una direttiva del modello specifica una classe che eredita da `TextTransformation`. Il messaggio fornisce il numero di riga della direttiva template.|Specificare una classe che deriva da `TextTransformation`.|
|Impostazioni cultura non valida specificata nella direttiva 'template'. Le impostazioni cultura devono essere nel formato "xx-XX". Verrà usata la lingua inglese.|Si verifica quando il parametro delle impostazioni cultura in una direttiva template è stato specificato correttamente. Il messaggio fornisce il numero di riga della direttiva template.|Modificare il parametro delle impostazioni cultura per una lingua valida nel formato "xx-XX".|
|Un valore di debug non valido '{0}' è stata specificata nella direttiva del modello. Il valore di debug deve essere "true" o "false". Verrà utilizzato il valore predefinito è "false".|Si verifica quando il `debug` parametro in una direttiva template è stato specificato correttamente. Il messaggio fornisce il numero di riga della direttiva template.|Impostare il parametro debug su "true" o "false".|
|Un valore di HostSpecific non valido '{0}' è stata specificata nella direttiva del modello. Il valore di HostSpecific deve essere "true" o "false". Verrà utilizzato il valore predefinito è "false".|Si verifica quando il parametro host specifico in un `template` direttiva è stata specificata correttamente. Il messaggio fornisce il numero di riga della direttiva template.|Impostare il parametro specifica dell'host su "true" o "false".|
|Un linguaggio non valido '{0}' è stata specificata nella direttiva 'template'. La lingua deve essere "C#" o "VB". Verrà utilizzato il valore predefinito "C#".|Si verifica quando si specifica una lingua non supportata nel `template` direttiva. Sono consentiti solo "C#" o "VB" (distinzione tra maiuscole e minuscole). Il messaggio fornisce il numero di riga della direttiva template.|Impostare il `language` parametro nella direttiva template "C#" o "VB".|
|Trovate più direttive output nel modello. Tutti tranne il primo verranno ignorati.|Si verifica quando più `output` direttive vengono specificate in un file modello. Il messaggio fornisce il numero di riga della direttiva output duplicati.|Rimuovere i duplicati `output` direttive.|
|Trovate più direttive template nel modello. Tutti tranne il primo verranno ignorati. Più parametri per la direttiva template devono essere specificati all'interno di una direttiva template.|Si verifica se si specificano più `template` direttive all'interno di un file di modello di testo (inclusi i file inclusi). Il messaggio fornisce il numero di riga della direttiva template duplicati.|Aggregare i diversi `template` direttive in un unico `template` direttiva.|
|È stato specificato alcun processore di direttiva denominata '{0}'. La direttiva verrà ignorata.|Si verifica se si specifica un `custom` direttiva, ma non offrono un `processor` attributo. Il messaggio fornisce il nome della direttiva e il numero di riga.|Fornire un `processor` attributo con il nome del `directive` processore per la direttiva.|
|Un processore denominato '{0}'non trovato per la direttiva denominata'{1}'. La direttiva verrà ignorata.|Si verifica quando il sistema non è possibile trovare il `directive` processore specificato all'interno di un `custom` direttiva. Il messaggio fornisce il nome della direttiva, nome del processore e il numero di riga della direttiva.|Impostare il `processor` attributo della direttiva per il nome del processore di direttiva.|
|Un parametro obbligatorio '{0}'per la direttiva'{1}' non è stato trovato. La direttiva verrà ignorata.|Si verifica quando il sistema non fornisce un parametro obbligatorio direttiva. Il messaggio fornisce il nome del parametro mancano, il nome della direttiva e il numero di riga.|Specificare il parametro mancante.|
|Il processore denominato '{0}'non supporta la direttiva denominata'{1}'. La direttiva verrà ignorata.|Si verifica quando un processore di direttiva non supporta una direttiva. Il messaggio fornisce il numero di riga e il nome della direttiva danneggiato insieme al nome del processore di direttiva.|Correggere il nome della direttiva.|
|La direttiva include per il file '{0}' causa un ciclo infinito.|Se le istruzioni di inclusione circolare visualizzato vengono specificati (ad esempio, il file include file B, che include il file).|Non specificare circolare le direttive di inclusione.|
|Esecuzione di trasformazione:|Antepone la stringa per tutti gli errori o avvisi generati durante l'esecuzione della trasformazione.|Non applicabile.|
|Un tag di inizio o fine imprevisto trovato all'interno di un blocco. Assicurarsi che non sia stato digitato erroneamente un tag di inizio o fine, e che non è necessario alcun blocco annidato nel modello.|Visualizzato quando si dispone di un'eccezione imprevista \<# o #>. Vale a dire, se dispone di un \<# dopo un altro tag aperto che non è stato chiuso, oppure l'utente dispone di un #> quando è presente alcun tag aperto prima di esso. Il messaggio fornisce il numero di riga del tag non corrispondenti.|Rimuovere il tag di inizio o fine non corrispondente o utilizzare un carattere di escape.|
|Una direttiva è stata specificata in un formato non corretto. La direttiva verrà ignorata. Specificare la direttiva nel formato `<#@ name [parametername="parametervalue"]*  #>`|Se non si specifica una direttiva nel formato corretto, visualizzato dal parser. Il messaggio fornisce il numero di riga della direttiva non corretto.|Assicurarsi che tutte le direttive siano nel formato `<#@ name [parametername="parametervalue"]*  #>`. Per ulteriori informazioni, vedere [direttive di modello di testo T4](../modeling/t4-text-template-directives.md).|
|Non è stato possibile caricare l'Assembly '{0}'per il processore di direttiva registrato'{1}'<br /><br /> {2}|Si verifica quando un processore di direttiva non è stato caricato dall'host. Il messaggio identifica l'assembly fornito per il processore di direttiva e il nome del processore di direttiva.|Verificare che il processore di direttiva sia registrato correttamente e che l'assembly esista.|
|Non è riuscito a trovare il tipo '{0}'nell'Assembly'{1}'per il processore di direttiva registrato'{2}'<br /><br /> {3}|Si verifica quando un tipo di processore di direttiva non è stato caricato dall'assembly. Il messaggio fornisce il nome del tipo, assembly e processore di direttiva.|Vshost Trova informazioni processore di direttiva (nome, assembly e tipo) nel Registro di sistema. Verificare che il processore di direttiva sia registrato correttamente e che il tipo esiste nell'assembly.|
|Si è verificato un problema durante il caricamento dell'assembly '{0}'|Si verifica quando si è verificato un problema durante il caricamento di un assembly. Il messaggio fornisce il nome dell'assembly.|È possibile specificare gli assembly da caricare in \<@# assembly #> direttive e dai processori di direttiva. Il messaggio di errore che segue questa stringa deve fornire più dati su perché il caricamento dell'assembly non è riuscita.|
|Si è verificato un problema durante la creazione e l'inizializzazione del processore di direttiva denominato '{1}'. Il tipo di elaborazione è {0}. La direttiva verrà ignorata.|Si verifica quando il sistema non è stato possibile creare o inizializzare un processore di direttiva. Il messaggio fornisce il numero di riga e il nome della direttiva e il tipo di elaborazione.|Assicurarsi che si utilizza il processore di direttiva corretto e che il processore di direttiva ha un costruttore predefinito pubblico. In caso contrario, è possibile utilizzare le opzioni di debug per scoprire perché il metodo Initialize () del processore di direttiva non riesce. Per ulteriori informazioni, vedere [risoluzione dei problemi di modelli di testo](../modeling/debugging-a-t4-text-template.md).|
|È stata generata un'eccezione durante l'elaborazione di una direttiva denominata '{0}'.|Si verifica quando un processore di direttiva genera un'eccezione durante l'elaborazione di una direttiva.|Assicurarsi che i parametri per il processore di direttiva siano corretti.|
|L'host ha generato un'eccezione durante il tentativo di risolvere il riferimento all'assembly '{0}'.|Si verifica quando l'host genera un'eccezione quando tenta di risolvere un riferimento all'assembly. Il messaggio fornisce l'assembly di riferimento di stringa.|Assembly riferimenti provenire da \<@# assembly #> direttive e dai processori di direttiva. Assicurarsi che il parametro 'name' fornito nel parametro dell'assembly sia corretto.|
|Provare a specificare non supportato {1} valore '{0}' per la direttiva {2}|Si verifica con RequiresProvidesDirectiveProcessor (tutti i processori di direttiva generati derivano da essa), quando si fornisce non supportato argomento richiede o fornisce.|Assicurarsi che i nomi in name = 'value' fornite coppie di richiede e fornisce i parametri siano corretti.|