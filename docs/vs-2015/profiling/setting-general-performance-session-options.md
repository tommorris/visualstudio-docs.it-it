---
title: Impostazione delle opzioni generali della sessione di prestazioni | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.general
ms.assetid: 6b60bd1b-2198-4261-b84e-9b2d8494a992
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: abf40be314191096447e389ef145385d2e0f616b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47526542"
---
# <a name="setting-general-performance-session-options"></a>Impostazione delle opzioni generali della sessione di prestazioni
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [impostazione delle opzioni di sessione generale di prestazioni](https://docs.microsoft.com/visualstudio/profiling/setting-general-performance-session-options).  
  
È possibile impostare il metodo di raccolta e le convenzioni di denominazione per i dati di profilatura per una sessione di prestazioni degli strumenti di profilatura di [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nella pagina **Generale** della finestra di dialogo delle proprietà per la sessione di prestazioni. Per aprire questa finestra di dialogo da **Esplora prestazioni**, fare clic con il pulsante destro del mouse sulla sessione di prestazioni e quindi scegliere **Proprietà**.  
  
 **Requisiti**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
## <a name="choosing-data-collection-methods"></a>Scelta del metodo di raccolta dati  
 Per impostare il metodo di raccolta di base, è necessario selezionare una delle opzioni in **Raccolta dati per profilatura**. Le opzioni sono descritte nella tabella seguente:  
  
|||  
|-|-|  
|**Campionamento**. Il metodo di campionamento raccoglie informazioni di profilatura a intervalli regolari. Questo metodo è utile per individuare problemi relativi all'uso del processore e rappresenta il metodo consigliato nella maggior parte dei casi per iniziare l'analisi delle prestazioni.|-   [Collecting Performance Statistics by Using Sampling](../profiling/collecting-performance-statistics-by-using-sampling.md) (Raccolta di statistiche sulle prestazioni tramite il campionamento)|  
|**Strumentazione**. Il metodo di strumentazione inserisce in una copia di un modulo di profilatura codice che registra ogni ingresso, uscita e chiamata di funzione delle funzioni nel modulo durante un'esecuzione della profilatura. Questo metodo è utile per raccogliere informazioni dettagliate sulle tempistiche per una sezione del codice e per comprendere l'impatto delle operazioni di input e output sulle prestazioni dell'applicazione.|-   [Collecting Detailed Timing Data by Using Instrumentation](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md) (Raccolta di dati di intervallo dettagliati tramite la strumentazione)|  
|**Concorrenza**. Il metodo di concorrenza raccoglie i dati per ogni evento che blocca l'esecuzione del codice, ad esempio quando un thread attende che l'accesso bloccato a una risorsa di un'applicazione venga liberato. Questo metodo è utile per l'analisi delle applicazioni multithread.|-   [Collecting Thread and Process Concurrency Data](../profiling/collecting-thread-and-process-concurrency-data.md) (Raccolta di dati di concorrenza di thread e processi)|  
  
 È possibile raccogliere dati di memoria .NET usando i metodi di campionamento o strumentazione. Il tipo di dati viene selezionato in **Profilatura della memoria .NET**.  
  
|||  
|-|-|  
|**Raccogliere le informazioni sull'allocazione dell'oggetto .NET**. Per impostazione predefinita, i dati includono il numero e le dimensioni degli oggetti allocati. Selezionare o deselezionare questa casella di controllo per abilitare o disabilitare la raccolta di dati di memoria .NET.<br /><br /> **Raccogliere anche le informazioni sulla durata dell'oggetto .NET**. Selezionare questa casella di controllo per includere i dati sulle generazioni di Garbage Collection usate per recuperare gli oggetti di memoria.|-   [Raccolta di dati di durata e allocazione di memoria .NET](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|  
  
 Una pagina della sessione di profilatura viene visualizzata quando si comincia a profilare un'applicazione, dove è possibile sospendere, riprendere e interrompere la profilatura.  
  
 ![Pagina della sessione di profilatura](../profiling/media/prof-profilingsessionpage.png "PROF_ProfilingSessionPage")  
  
## <a name="setting-profiling-datra-file-options"></a>Impostazione delle opzioni dei file di dati di profilatura  
  
|||  
|-|-|  
|**Report**. Per impostazione predefinita, al file dei dati di profilatura (con estensione vsp) viene assegnato il nome dell'applicazione sottoposta a profilatura e il file viene posizionato nella cartella della soluzione o del progetto. Al nome viene aggiunta anche una stringa di data e viene anche aggiunto un numero incrementale ai file di dati che in caso contrario avrebbero nomi duplicati. Queste opzioni possono essere modificate.|-   [How to: Set Performance Data File Name Options](../profiling/how-to-set-performance-data-file-name-options.md) (Procedura: Impostare le opzioni relative ai nomi file dei dati di profilatura)|



