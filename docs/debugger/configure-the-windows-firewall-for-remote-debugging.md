---
title: Configurare il Firewall di Windows per il debug remoto | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 66e3230a-d195-4473-bbce-8ca198516014
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9688948ebe2fa5e045578ee808e068d59450d748
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433391"
---
# <a name="configure-the-windows-firewall-for-remote-debugging"></a>Configurare Windows Firewall per il debug remoto
Questo argomento illustra come configurare il firewall per abilitare il debug remoto nei computer che eseguono i sistemi operativi seguenti:  
  
-   Windows 10  
  
-   Windows 8/8.1  
  
-   Windows 7   
  
-   Windows Server 2012 R2  

-   Windows Server 2012
  
-   Windows Server 2008 R2 
  
 Se la rete su cui si esegue il debug non è protetta da un firewall, questa configurazione non è necessaria. In caso contrario, è necessario modificare la configurazione del firewall sia nel computer che ospita Visual Studio, sia nel computer remoto di cui si esegue il debug.  
  
 **IPSec** : se la rete richiede che le comunicazioni avvengano tramite IPSec, è necessario aprire porte aggiuntive sia sul computer host di Visual Studio sia sul computer remoto.  
  
 **Server Web** : se si esegue il debug di un server Web remoto, è necessario aprire una porta supplementare sul computer remoto. (Per IIS, la porta 80 deve essere aperta.)  
  
 Tenere presente che non è necessario che entrambi i computer eseguano lo stesso sistema operativo. Ad esempio, il computer di Visual Studio può eseguire Windows 10 e il computer remoto può eseguire Windows Server 2012 R2.      
  
## <a name="ports-on-the-remote-computer-that-enable-remote-debugging"></a>Porte nel computer remoto che abilitano il debug remoto  
  
|**Porte**|**In ingresso/in uscita**|**Protocollo**|**Descrizione**|   
|-|-|-|-|  
|4022|In ingresso|TCP|Per Visual Studio 2017. Il numero di porta aumenta di 2 per ogni versione di Visual Studio. Per altre informazioni, vedere [Visual Studio Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md).|  
|4023|In ingresso|TCP|Per Visual Studio 2017. Il numero di porta aumenta di 2 per ogni versione di Visual Studio. (Solo usata per remote debug un processo a 32 bit dalla versione a 64 bit del debugger remoto.) Per altre informazioni, vedere [Visual Studio Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md).| 
|3702|In uscita|UDP|(Facoltativo) Richiesto per remote debugger discovery.|    
  
## <a name="how-to-configure-ports-in-windows-firewall"></a>Come configurare le porte in Windows Firewall  

Quando si installa Visual Studio o il debugger remoto, il software tenterà di aprire le porte appropriate. Tuttavia, in alcuni scenari (ad esempio, tramite un firewall di terze parti), potrebbe essere necessario aprire manualmente una porta. Se è necessario verificare che le porte siano aperte, vedere [Troubleshooting](#troubleshooting). Alcune istruzioni per l'apertura di una porta potrebbero essere diverse nelle versioni precedenti di Windows.

Per aprire una porta:
  
1. Aprire il **avviare** menu, cercare **Windows Firewall con sicurezza avanzata**.

2. Quindi scegliere **regole connessioni in entrata > nuova regola > porta**, quindi fare clic su **successivo**. (Per le regole in uscita, scegliere **regole in uscita** invece.)

3. Scegliere uno **TCP** oppure **UDP**, a seconda del numero di porta.

4. Sotto **porte locali specifiche**, immettere il numero di porta, fare clic su **successivo**.

5. Fare clic su **Allow the Connection** , quindi fare clic su **Avanti**.

6. Selezionare uno o più tipi di rete da abilitare per la porta e fare clic su **successivo**.

    Il tipo selezionato deve includere la rete a cui è connesso il computer remoto.
7. Aggiungere il nome (ad esempio, **msvsmon**, **IIS**, o **distribuzione Web**) per la regola e fare clic su **fine**.

    Si dovrebbe vedere la nuova regola nell'elenco Regole connessioni in entrata o in uscita.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se si riscontrano problemi nella connessione all'App con il debugger remoto, devi verificare che le porte appropriate siano aperte.

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-visual-studio-computer"></a>Verificare che le porte siano aperte nel Firewall Windows nel Computer di Visual Studio  
 Le istruzioni per configurare Windows firewall sono leggermente diverse a seconda del sistema operativo. In Windows 8/8.1, Windows 10 e Windows Server 2012, la parola **app** viene utilizzata; in Windows 7 o Windows Server 2008, la parola **programma** viene usato;  Nei passaggi seguenti si userà il termine **app**.  
  
1.  Aprire la pagina di Windows Firewall. A questo scopo digitare **Windows Firewall** nella casella di ricerca del menu **Start**.  
  
2.  Fare clic su **Consenti app o funzionalità attraverso Windows Firewall**.  
  
3.  Nell'elenco **App e funzionalità consentite** cercare **Visual Studio Remote Debugger Discovery**. Se è elencato, assicurarsi che sia selezionato e che siano selezionati anche uno o più tipi di rete.  
  
4.  Se **Visual Studio Remote Debugger Discovery** non è incluso nell'elenco, fare clic su **Consenti un'altra app**. Se non viene ancora visualizzato nei **aggiungere un'app** finestra, fare clic su **Sfoglia** e passare a  **\<directory di installazione di Visual Studio > \Common7\IDE\Remote Debugger**. Individuare la cartella appropriata per l'applicazione (x86, x64, Appx) e quindi selezionare **msvsmon.exe**. Fare quindi clic su **Aggiungi**.  
  
5.  Nel **le App e funzionalità consentite** elenco, selezionare **Visual Studio Remote Debugger**. Selezionare uno o più tipi di rete (**di dominio, casa/lavoro (privata), pubblica**) con cui si vuole che Remote Debugging Monitor comunichi. Tra i tipi deve essere inclusa la rete a cui è connesso il computer di Visual Studio. 

### <a name="verify-that-ports-are-open-in-the-windows-firewall-on-the-remote-computer"></a>Verificare che le porte siano aperte nel Firewall Windows nel computer remoto  
 I componenti di debug remoto possono essere installati nel computer remoto o eseguiti da una directory condivisa. Il firewall del computer remoto deve essere configurato in entrambi i casi. I componenti di debug remoto si trovano in:  
  
 **\<Directory di installazione di Visual Studio > \Common7\IDE\Remote Debugger**  
  
 Le istruzioni per configurare Windows firewall sono leggermente diverse a seconda del sistema operativo. In Windows 8/8.1, Windows 10 e Windows Server 2012, la parola **app** viene utilizzata; in Windows 7 o Windows Server 2008, la parola **programma** viene usato;  Nei passaggi seguenti si userà il termine **app**.  
  
1.  Aprire la pagina di Windows Firewall. A questo scopo digitare **Windows Firewall** nella casella di ricerca del menu **Start**.  
  
2.  Fare clic su **Consenti app o funzionalità attraverso Windows Firewall**.  
  
3.  Nel **le App e funzionalità consentite** elencare, cercare **Visual Studio Remote Debugger**. Se è elencato, assicurarsi che sia selezionato e che siano selezionati anche uno o più tipi di rete.  
  
4.  Se **Visual Studio Remote Debugger** non è elencato, fare clic su **Consenti un'altra app**. Se non viene ancora visualizzato nei **aggiungere una finestra dell'app**, fare clic su **Sfoglia** e passare a  **\<directory di installazione di Visual Studio > \Common7\IDE\Remote Debugger**. Individuare la cartella appropriata per l'applicazione (x86, x64, Appx) e quindi selezionare **msvsmon.exe**. Fare quindi clic su **Aggiungi**.  
  
5.  Nel **App consentite** elenco, selezionare **Visual Studio Remote Debugger**. Selezionare uno o più tipi di rete (**di dominio, casa/lavoro (privata), pubblica**) con cui si vuole che Remote Debugging Monitor comunichi. Tra i tipi deve essere inclusa la rete a cui è connesso il computer di Visual Studio. 

### <a name="managed-or-native-compatibility-mode-open-additional-ports-on-the-remote-computer"></a>(Modalità compatibilità gestito o nativo) Aprire porte aggiuntive sul computer remoto

Se si utilizza la modalità di compatibilità per il debugger (**strumenti > Opzioni > debug**), saranno necessario aprire porte aggiuntive. Modalità di compatibilità consente a una versione legacy del debugger e diverse porte sono obbligatorie.

> [!NOTE]
> La versione legacy di debugger è il debugger di Visual Studio 2010.
  
|**Porte**|**In ingresso/in uscita**|**Protocollo**|**Descrizione**|  
|-|-|-|-|  
|135, 139, 445|In uscita|TCP|Obbligatorio.|  
|137, 138|In uscita|UDP|Obbligatorio.|  
|500, 4500|In uscita|UDP|Necessario se i criteri del dominio richiedono che la comunicazione di rete avvenga tramite IPSec.|  
|80|In uscita|TCP|Richiesto per il debug di server Web.|
  
## <a name="see-also"></a>Vedere anche  
 [Debug remoto](../debugger/remote-debugging.md)