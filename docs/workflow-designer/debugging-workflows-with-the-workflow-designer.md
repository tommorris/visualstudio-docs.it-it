---
title: Debug dei flussi di lavoro mediante Progettazione flussi di lavoro
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Visual Studio Workflow Designer [WFD], debugging workflows
- Workflow Designer [WFD], debugging workflows
ms.assetid: d71308cf-d464-4536-8711-0d0a8eadb255
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 482e13a91513151d7c4595e0a622f223751ae553
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755314"
---
# <a name="debug-workflows-with-the-workflow-designer"></a>Eseguire il debug dei flussi di lavoro con la finestra di progettazione del flusso di lavoro

Il **finestra di progettazione del flusso di lavoro** offre la possibilità di eseguire il debug dei flussi di lavoro e attività personalizzate. Il processo e il comportamento sono simili a quello del debugger di Visual Studio predefinito.

## <a name="invoke-the-workflow-debugger"></a>Richiama il debugger del flusso di lavoro

Generalmente si esegue il debug dei flussi di lavoro nello stesso modo in cui si esegue il debug di programmi scritti negli altri linguaggi di programmazione di Visual Studio. È possibile avviare il debugger del flusso di lavoro nei modi seguenti:

- Selezionare **Connetti a processo** nel **Debug** menu per selezionare il processo host in esecuzione per l'istanza del flusso di lavoro. La procedura è identica a quella di collegamento a un processo host nel codice gestito.

- Premere **F5** per avviare l'esecuzione di un'istanza del flusso di lavoro o per continuare a eseguire dopo aver raggiunto un punto di interruzione.

- Usare debug remoto. Per informazioni sul debug remoto, vedere [procedura: abilitare il debug remoto](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

   > [!NOTE]
   > Se l'applicazione del flusso di lavoro ha come destinazione x86 architettura ed è contenuta in un computer che eseguono un sistema operativo a 64 bit, il debug remoto non funzionerà a meno che non è installato Visual Studio nel computer remoto o la destinazione per l'applicazione del flusso di lavoro viene modificata in  **Qualsiasi CPU**.

## <a name="step-through-code"></a>Esaminare il codice

- **Esegui istruzione**: passaggio in un'attività premendo **F11**. Il debugger avanza in qualsiasi gestore definito. Se nessun gestore è definito, viene eseguita l'istruzione/routine dell'attività oppure, con CompositeActivity contenenti altre attività, viene eseguita l'istruzione della prima attività in stato di esecuzione.

- **Esci:** uscire da un'attività premendo **MAIUSC**+**F11**. Uscendo da un'istruzione/routine di un'attività, l'attività corrente e tutte le relative attività di pari livello vengono eseguite fino al completamento. Il debugger reimposta quindi il padre dell'attività corrente. Uscendo da un gestore del codice, il debugger reimposta l'attività alla quale è associato il gestore.

- **Esegui istruzione/routine**: Esegui istruzione/routine di un'attività premendo **F10**. Quando viene eseguita l'istruzione/routine di un oggetto CompositeActivity, il debugger reimposta il primo figlio eseguibile del CompositeActivity. Quando viene eseguita l'istruzione/routine di un attività diversa da CompositeActivity, ad esempio <xref:System.Activities.Statements.Assign>, il debugger esegue l'attività e i gestori ad essa associati e reimposta l’attività successiva. Se l'attività eseguita è l'ultima attività figlio di un oggetto CompositeActivity, dopo l'esecuzione il debugger reimposterà l'attività padre.

## <a name="debug-with-f5"></a>Eseguire il debug con F5

Se si sta creando un'app di console del flusso di lavoro, è sufficiente premere **F5** per avviare il debug nell'applicazione e del flusso di lavoro. Se si compila una libreria attività autonomamente, è necessario specificare un'applicazione host eseguibile come progetto di avvio. Per impostare un progetto di avvio **Esplora soluzioni**, fare clic sul nome del progetto dell'host e selezionare **imposta come progetto di avvio**.