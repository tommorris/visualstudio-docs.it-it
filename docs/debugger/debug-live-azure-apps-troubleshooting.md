---
title: Risoluzione dei problemi e problemi noti per il debug di snapshot | Microsoft Docs
ms.date: 11/07/2017
ms.technology: vs-ide-debug
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d5b5eeefe2bbed542ef18689fd7e16073174bd3
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284107"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Risoluzione dei problemi e problemi noti per il debug di snapshot in Visual Studio

Se i passaggi descritti in questo articolo non risolvono il problema, contattare il tecnico snaphelp@microsoft.com.

## <a name="issue-snappoint-does-not-turn-on"></a>Problema: Punto di ancoraggio non attiva

Se viene visualizzata un'icona di avviso ![icona di avviso punto di ancoraggio](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "icona di avviso punto di ancoraggio") con il punto di ancoraggio anziché l'icona di punto di ancoraggio regolari, quindi il punto di ancoraggio non è attivata.

![Punto di ancoraggio non attivata](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "punto di ancoraggio non attiva")

Eseguire questi passaggi:

1. Assicurarsi di avere la stessa versione del codice sorgente che è stato usato per compilare e distribuire il app.isua1. Assicurarsi che si siano caricando i simboli corretti per la distribuzione. A tale scopo, visualizzare il **moduli** finestra durante il debug di Snapshot e verificare la colonna del File di simboli viene illustrato un file con estensione pdb caricato per il modulo si esegue il debug. Il Debugger di Snapshot tenterà automaticamente di scaricare e usare i simboli per la distribuzione.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>Problema: I simboli non vengono caricati quando si apre uno Snapshot

Se verrà visualizzata la seguente finestra, i simboli non è stato caricato.

![Non è possibile caricare i simboli](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "non è possibile caricare i simboli")

Eseguire questi passaggi:

- Fare clic su di **modificare le impostazioni dei simboli...** collegamento in questa pagina. Nel **Debug > simboli** impostazioni, aggiungere una directory cache dei simboli. Riavviare il debug di snapshot dopo aver impostato il percorso dei simboli.

   I simboli o un file con estensione pdb, disponibili nel progetto devono corrispondere la distribuzione del servizio App. La maggior parte delle distribuzioni (distribuzione tramite Visual Studio, integrazione continua/recapito Continuo con le pipeline di Azure o Kudu, e così via) verranno pubblicati i file di simboli insieme al servizio App. Impostare la directory cache dei simboli consente a Visual Studio usare questi simboli.

   ![Impostazioni dei simboli](../debugger/media/snapshot-troubleshooting-symbol-settings.png "impostazioni dei simboli")

- In alternativa, se l'organizzazione Usa un server di simboli o Elimina i simboli in un percorso diverso, usare le impostazioni dei simboli per caricare i simboli corretti per la distribuzione.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>Problema: non è possibile visualizzare l'opzione "Collegare Snapshot Debugger" in Cloud Explorer

Eseguire questi passaggi:

- Verificare che sia installato il componente Debugger di Snapshot. Aprire l'installazione di Visual Studio e verificare i **Snapshot Debugger** componente del carico di lavoro di Azure.
- Assicurarsi che l'app sia supportato. Attualmente, solo ASP.NET (4.6.1+) e le app ASP.NET Core (2.0 +) distribuite in servizi App di Azure sono supportate.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>Problema: è visibile solo gli snapshot limitato in strumenti di diagnostica

![Punto di ancoraggio limitate](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "limitate punto di ancoraggio")

Eseguire questi passaggi:

- Gli snapshot occupano memoria piccolo ma è previsto un addebito commit. Se il Debugger di Snapshot rileva che il server è in condizioni di carico di memoria pesanti, non registra snapshot. È possibile eliminare gli snapshot già acquisiti interrompendo la sessione del Debugger di Snapshot e riprovare.

## <a name="known-issues"></a>Problemi noti

- Debug di snapshot con più client di Visual Studio con lo stesso servizio App non è attualmente supportato.
- Ottimizzazioni di linguaggio intermedio Roslyn non sono completamente supportate nei progetti ASP.NET Core. Per alcuni progetti ASP.NET Core, potrebbe non essere in grado di vedere alcune variabili o usare alcune variabili nelle istruzioni condizionali. 
- Variabili speciali, ad esempio *$FUNCTION* oppure *$CALLER*, non è possibile valutare in istruzioni condizionali o punti di registrazione per i progetti ASP.NET Core.
- Debug di snapshot non funziona nei servizi di App che hanno [memorizzazione nella cache locale](/azure/app-service/app-service-local-cache) attivata.
- Snapshot di debug di App per le API non è attualmente supportato.

## <a name="site-extension-upgrade"></a>Aggiornamento di estensione del sito

Debug di snapshot e Application Insights variano in base un ICorProfiler, che viene caricato il processo del sito e fa in modo che i problemi di blocco di file durante l'aggiornamento. È consigliabile assicurarsi che non ci sia alcun tempo di inattività per il sito di produzione del processo.

- Creare un [Slot di distribuzione](/azure/app-service/web-sites-staged-publishing) all'interno del servizio App e Distribuisci il tuo sito nello slot.
- Trasferire lo Slot di produzione da Esplora Cloud in Visual Studio o dal portale di Azure.
- Arrestare il sito dello Slot. Questo richiederà alcuni secondi per terminare il processo w3wp.exe di sito da tutte le istanze.
- Aggiornare l'estensione dello Slot del sito dal sito di Kudu o il portale di Azure (*pannello servizio App > Strumenti di sviluppo > estensioni > aggiornamenti*).
- Avviare il sito dello Slot. È consigliabile visitare il sito per riscaldamento nuovamente.
- Trasferire lo Slot di produzione.

## <a name="see-also"></a>Vedere anche

[Debug in Visual Studio](../debugger/index.md)  
[Il debug in tempo reale delle App ASP.NET usando il Debugger di Snapshot](../debugger/debug-live-azure-applications.md)  
[Domande frequenti sul debug di snapshot](../debugger/debug-live-azure-apps-faq.md)  
