---
title: Eseguire il Debug remoto un progetto Visual C++ | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 8b8eca0d-122f-4eda-848a-cf0945f207d0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 334a0b964033282458c211d69af30aad20dbd6bc
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2018
ms.locfileid: "38781945"
---
# <a name="remote-debugging-a-visual-c-project-in-visual-studio"></a>Un progetto Visual C++ in Visual Studio di debug remoto
Per eseguire il debug di un'applicazione di Visual Studio in un altro computer, installare ed eseguire remote tools sul computer in cui si distribuirà l'app, configurare il progetto per connettersi al computer remoto da Visual Studio e quindi distribuire ed eseguire l'app.

![Componenti del debugger remoto](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

Per informazioni sulle app di Windows universali (UWP) di debug remoto, vedere [eseguire il Debug di un pacchetto dell'App installato](debug-installed-app-package.md).

## <a name="requirements"></a>Requisiti

Il debugger remoto è supportato in Windows 7 e versioni successive (non phone) e le versioni di Windows Server a partire da Windows Server 2008 Service Pack 2. Per un elenco completo dei requisiti, vedere [requisiti](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Non è supportato tra due computer connessi tramite un proxy di debug. Debug tramite una latenza elevata o una connessione di larghezza di banda ridotta, ad esempio Internet, accesso remoto o la rete Internet tra paesi non è consigliabile e può avere esito negativo o essere inaccettabile.
  
## <a name="download-and-install-the-remote-tools"></a>Scaricare e installare remote tools

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
> [!TIP]
> In alcuni scenari, può essere più efficiente per eseguire il debugger remoto da una condivisione file. Per altre informazioni, vedere [eseguire il debugger remoto da una condivisione file](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a> Configurare il debugger remoto

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Se è necessario aggiungere le autorizzazioni per altri utenti, modificare la modalità di autenticazione o il numero di porta per il debugger remoto, vedere [configurare il debugger remoto](../debugger/remote-debugging.md#configure_msvsmon).

## <a name="remote_cplusplus"></a> Debug remoto di un progetto Visual C++  
 Nella procedura seguente, il nome e percorso del progetto sono C:\remotetemp\MyMfc e il nome del computer remoto viene **MJO DL**.  
  
1.  Creare un'applicazione MFC denominata **mymfc.**  
  
2.  Impostare un punto di interruzione in una posizione nell'applicazione che sia facilmente raggiungibile, ad esempio nella **MainFrm. cpp**, all'inizio di `CMainFrame::OnCreate`.  
  
3.  In Esplora soluzioni fare doppio clic sul progetto e scegliere **proprietà**. Aprire il **debug** scheda.  
  
4.  Impostare il **Debugger da avviare** al **Debugger Windows remoto**.  
  
     ![RemoteDebuggingCPlus](../debugger/media/remotedebuggingcplus.png "RemoteDebuggingCPlus")  
  
5.  Apportare le seguenti modifiche alle proprietà:  
  
    |Impostazione|Valore|
    |-|-|  
    |Comando remoto|C:\remotetemp\mymfc.exe|  
    |Directory di lavoro|C:\remotetemp|  
    |Nome server remoto|MJO-DL:*NumeroPorta*|  
    |Connessione|Remoto con autenticazione di Windows|  
    |Tipo di debugger|Solo nativo|  
    |Directory di distribuzione|C:\remotetemp|  
    |File aggiuntivi da distribuire|C:\data\mymfcdata.txt|  
  
     Se si distribuiscono file aggiuntivi (facoltativi), la cartella deve essere presente in entrambi i computer.  
  
6.  In Esplora soluzioni fare doppio clic la soluzione e scegliere **Configuration Manager**.  
  
7.  Per il **Debug** configurazione, selezionare la **Distribuisci** casella di controllo.  
  
     ![RemoteDebugCplusDeploy](../debugger/media/remotedebugcplusdeploy.png "RemoteDebugCplusDeploy")  
  
8.  Avviare il debug (**Debug > Avvia debug**, o **F5**).  
  
9. Il file eseguibile viene distribuito automaticamente al computer remoto.  
  
10. Se richiesto, immettere le credenziali di rete per la connessione al computer remoto.  
  
     Le credenziali necessarie sono specifiche di configurazione della sicurezza della rete. Ad esempio, in un computer di dominio, si potrebbe scegliere un certificato di sicurezza o immettere il nome di dominio e la password. In un computer non di dominio, è possibile immettere il nome del computer e un nome di account utente valido, ad esempio **MJO-DL\name@something.com**, con password non corretta.  
  
11. Nel computer di Visual Studio l'esecuzione viene arrestata in corrispondenza del punto di interruzione.  
  
    > [!TIP]
    >  In alternativa, è possibile distribuire i file come passaggio separato. Nel **Esplora soluzioni** fare doppio clic il **mymfc** nodo e quindi scegliere **Distribuisci**.  
  
 Se sono presenti file non di codice che devono essere usati dall'applicazione, è necessario includerli nel progetto di Visual Studio. Creare una cartella di progetto per i file aggiuntivi (nelle **Esplora soluzioni**, fare clic su **Aggiungi > nuova cartella**.) Quindi aggiungere i file nella cartella (nelle **Esplora soluzioni**, fare clic su **Aggiungi > elemento esistente**, quindi selezionare i file). Nel **delle proprietà** pagina per ogni file, impostare **copia in Directory di Output** a **Copia sempre**.
  
## <a name="set-up-debugging-with-remote-symbols"></a>Configurare il debug con simboli remoti 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)] 
  
## <a name="see-also"></a>Vedere anche  
 [Debug in Visual Studio](../debugger/index.md)  
 [Debugger Feature Tour](../debugger/debugger-feature-tour.md)  (Tour delle funzionalità del debugger)  
 [Configurare il Firewall di Windows per il debug remoto](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Assegnazioni di porta del Debugger remoto](../debugger/remote-debugger-port-assignments.md)   
 [Debug remoto di ASP.NET in un computer remoto con IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Errori e risoluzione dei problemi relativi al debug remoto](../debugger/remote-debugging-errors-and-troubleshooting.md)