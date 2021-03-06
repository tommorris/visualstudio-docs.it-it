---
title: Debug remoto in Visual Studio | Microsoft Docs
ms.custom: remotedebugging
ms.date: 07/02/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46913c1bb671c1986c4f302a84d4183fe17f5878
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2018
ms.locfileid: "38778294"
---
# <a name="remote-debugging"></a>Remote Debugging
È possibile eseguire il debug di un'applicazione Visual Studio che è stata distribuita in un computer diverso. A questo scopo si usa Visual Studio Remote Debugger.

Per istruzioni dettagliate sul debug remoto, vedere questi argomenti.

|Scenario|Collegamento|
|-|-|-|
|Servizio app di Azure|[Debugger di snapshot](../debugger/debug-live-azure-applications.md) o [Remote debug ASP.NET in Azure](../debugger/remote-debugging-azure.md)|
|Macchina virtuale Azure|[Eseguire il debug remoto di ASP.NET in Azure](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[Eseguire il debug di un'applicazione Azure Service Fabric](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[ASP.NET Core eseguire il debug remoto](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) o [Remote Debug ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|In c# o Visual Basic|[Eseguire il debug remoto di un progetto C# o Visual Basic](../debugger/remote-debugging-csharp.md)|
|C++|[Eseguire il debug remoto di un progetto C++](../debugger/remote-debugging-cpp.md)|
|App di Windows universale (UWP)|[Eseguire App UWP in un computer remoto](../debugger/run-windows-store-apps-on-a-remote-machine.md) o [il Debug di un pacchetto dell'app installato](../debugger/debug-installed-app-package.md)|

Se sufficiente da scaricare e installare il debugger remoto e non sono necessarie le istruzioni aggiuntive per lo scenario, seguire i passaggi descritti in questo articolo.

## <a name="download-and-install-the-remote-tools"></a>Scaricare e installare remote tools

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="unblock_msvsmon"></a> Sbloccare il download di remote tools in Windows Server

Le impostazioni di sicurezza predefinite in Internet Explorer in Windows Server possono rendere molto tempo per il download di componenti, ad esempio gli strumenti remoti.

* Sicurezza avanzata è abilitata in Internet Explorer, che impedisce l'apertura di siti Web e l'accesso a risorse web, a meno che il dominio che contiene la risorsa è esplicitamente consentito (vale a dire, attendibili). Anche se è possibile disabilitare questa impostazione, non è consigliabile che perché può presenta un rischio per la sicurezza.

* In Windows Server 2016, un'impostazione predefinita in **Opzioni Internet** > **sicurezza** > **Internet**  >   **Livello personalizzato** > **Scarica** anche disabilita il download di file. Se si sceglie di scaricare gli strumenti remoti direttamente in Windows Server, è necessario abilitare il download di file.

Per scaricare gli strumenti di Windows Server, è consigliabile una delle operazioni seguenti:

* Scaricare remote tools in un computer diverso, ad esempio un in esecuzione Visual Studio e quindi copiare il *.exe* file da Windows Server.

* Eseguire il debugger remoto [da una condivisione file](#fileshare_msvsmon) nel computer di Visual Studio.

* Scaricare gli strumenti remoti direttamente nel Server di Windows e accettare le richieste per aggiungere siti attendibili. Siti Web moderni includono spesso molte risorse di terze parti, in modo che ciò può comportare molti dei prompt. Inoltre, tutti i collegamenti di reindirizzamento potrebbe essere necessario essere aggiunti manualmente. È possibile scegliere di aggiungere alcuni dei siti attendibili prima di iniziare il download. Passare a **Opzioni Internet > sicurezza > siti attendibili > siti** e aggiungere i seguenti siti.

  * VisualStudio.microsoft.com
  * download.visualstudio.microsoft.com
  * sulle: vuoto

  Per le versioni precedenti del debugger in my.visualstudio.com, aggiungere questi siti aggiuntivi per assicurarsi che tale account di accesso ha esito positivo:

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * My.VisualStudio.com
  * Login.microsoftonline.com
  * Login.Live.com
  * Secure.aadcdn.microsoftonline-p.com
  * msft.STS.microsoft.com
  * auth.GFX.ms
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.Prod.cms.RT.microsoft.com

    Se si sceglie di aggiungere questi domini durante il download di remote tools, scegli **Add** quando richiesto.

    ![Finestra di dialogo contenuto bloccato](../debugger/media/remotedbg-blocked-content.png)

    Quando si scarica il software, si ottengono alcune richieste aggiuntive di concedere autorizzazioni per caricare vari script del sito web e risorse. In my.visualstudio.com, è consigliabile aggiungere i domini aggiuntivi per assicurarsi che tale account di accesso ha esito positivo.

## <a name="requirements_msvsmon"></a> Requisiti

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]

## <a name="fileshare_msvsmon"></a> (Facoltativo) Per eseguire il debugger remoto da una condivisione file

È possibile trovare il debugger remoto (*msvsmon.exe*) in un computer con Visual Studio Community, Professional o Enterprise già installato. Per alcuni scenari, il modo più semplice per impostare il debug remoto consiste nell'eseguire il debugger remoto (msvsmon.exe) da una condivisione file. Per le limitazioni di utilizzo, vedere pagina della Guida del debugger remoto (**aiutare > utilizzo** nel debugger remoto).

1. Trovare *msvsmon.exe* nella directory corrispondente alla versione di Visual Studio. Per Visual Studio Enterprise 2017:

      *Programma file (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*

      *Programma file (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. Condividi i **Remote Debugger** cartella nel computer di Visual Studio.

3. Nel computer remoto, eseguire *msvsmon.exe* dalla cartella condivisa. Seguire le [istruzioni di configurazione](#bkmk_setup).

> [!TIP]
> Per l'installazione dalla riga di comando e i riferimenti alla riga di comando, vedere la pagina della Guida per *msvsmon.exe* digitando ``msvsmon.exe /?`` nella riga di comando nel computer con installato Visual Studio (o passare a **Guida > utilizzo**nel debugger remoto).

## <a name="bkmk_setup"></a> Configurare il debugger remoto

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> Configurare il debugger remoto
È possibile modificare alcuni aspetti della configurazione del debugger remoto dopo che è stata avviata per la prima volta.

-   Se è necessario aggiungere le autorizzazioni per altri utenti per connettersi al debugger remoto, selezionare **strumenti > autorizzazioni**. È necessario avere privilegi di amministratore per concedere o negare autorizzazioni.

     > [!IMPORTANT]
     > È possibile eseguire il debugger remoto con un account utente diverso dall'account utente in uso nel computer di Visual Studio, ma è necessario aggiungere l'account utente diverso alle autorizzazioni del debugger remoto.

     In alternativa, è possibile avviare il debugger remoto dalla riga di comando con il **/Allow \<username >** parametro: **msvsmon /Allow \< username@computer>**.

-   Se è necessario modificare la modalità di autenticazione o il numero di porta oppure specificare un valore di timeout per remote tools: scegliere **strumenti > Opzioni**.

     Per un elenco dei numeri di porta usati per impostazione predefinita, vedere [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md).

     > [!WARNING]
     >  È possibile scegliere di eseguire Remote Tools in modalità Nessuna autenticazione che, tuttavia, è fortemente sconsigliata perché priva di qualsiasi sicurezza di rete. Scegliere la modalità Nessuna autenticazione solo se si ha la certezza che la rete non è soggetta a rischi derivanti da traffico ostile o dannoso.

##  <a name="bkmk_configureService"></a> (Facoltativo) Configurare il debugger remoto come servizio
Per il debug in ASP.NET e altri ambienti server, si deve eseguire il debugger remoto come amministratore o, se si desidera sempre in esecuzione, eseguire il debugger remoto come servizio.

 Se si desidera configurare il debugger remoto come servizio, seguire questa procedura.

1.  Trovare la **Configurazione guidata del debugger remoto** (rdbgwiz.exe). Si tratta di un'applicazione separata dal debugger remoto. È disponibile solo quando si installa Remote Tools e non è inclusa nell'installazione di Visual Studio.

2.  Avviare la configurazione guidata. Quando viene visualizzata la prima pagina, fare clic su **Avanti**.

3.  Selezionare la casella di controllo **Esegui Visual Studio 2015 Remote Debugger come servizio** .

4.  Aggiungere il nome dell'account utente e la password.

     Potrebbe essere necessario aggiungere il **Accedi come servizio** utente direttamente a questo account (trovare **criteri di sicurezza locali** (secpol. msc) nella **avviare** pagina o nella finestra (o tipo  **secpol** un prompt dei comandi). Quando viene visualizzata la finestra, fare doppio clic su **Assegnazione diritti utente**e trovare **Accedi come servizio** nel riquadro di destra. Fare doppio clic. Aggiungere l'account utente per il **delle proprietà** finestra e fare clic su **OK**). Scegliere **Avanti**.

5.  Selezionare il tipo di rete con cui si vuole che Remote Tools comunichi. Almeno un tipo di rete deve essere selezionato. Se i computer sono connessi tramite un dominio, è necessario scegliere il primo elemento. Se i computer sono connessi tramite un gruppo di lavoro o un gruppo home, è necessario scegliere il secondo o il terzo elemento. Scegliere **Avanti**.

6.  Se è possibile avviare il servizio, viene visualizzato il messaggio **Configurazione guidata di Visual Studio Remote Debugger completata**. Se non è possibile avviare il servizio, viene visualizzato il messaggio **Impossibile completare la Configurazione guidata di Visual Studio Remote Debugger**. La pagina offre anche alcuni suggerimenti da seguire per l'avvio del servizio.

7.  Scegliere **Fine**.

 A questo punto il debugger remoto è in esecuzione come servizio. È possibile verificarlo passando **Pannello di controllo > servizi** e cercando **Visual Studio 2015 Remote Debugger**.

 È possibile arrestare e avviare il servizio debugger remoto da **Pannello di controllo > servizi**.

## <a name="set-up-debugging-with-remote-symbols"></a>Configurare il debug con simboli remoti

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>Vedere anche

- [Tour delle funzionalità del debugger](../debugger/debugger-feature-tour.md)
- [Configurare Windows Firewall per il debug remoto](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [Assegnazioni delle porte del debugger remoto](../debugger/remote-debugger-port-assignments.md)
- [Debug di ASP.NET Core in un Computer remoto con IIS remoto](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [Errori e risoluzione dei problemi relativi al debug remoto](../debugger/remote-debugging-errors-and-troubleshooting.md)