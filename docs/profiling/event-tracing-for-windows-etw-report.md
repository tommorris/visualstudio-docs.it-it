---
title: Report Traccia eventi per Windows (ETW) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 22307143f0044c6a3816534add9fe285ce8a9fd4
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764456"
---
# <a name="event-tracing-for-windows-etw-report"></a>Report Traccia eventi per Windows (ETW)
Il report Traccia eventi per Windows (ETW) indica gli eventi ETW registrati in una sessione di prestazioni degli strumenti di profilatura di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. I dati ETW vengono raccolti in un file binario con estensione *etl*.  
  
> [!NOTE]
>  Non è possibile visualizzare i report ETW nell'interfaccia di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Per informazioni su come raccogliere dati ETW usando gli strumenti di profilatura dall'interfaccia di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], vedere [Procedura: Raccogliere dati ETW (Event Tracing for Windows)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Per informazioni su come raccogliere dati ETW usando gli strumenti della riga di comando di [VSPerfCmd](../profiling/vsperfcmd.md), vedere [Eventi](../profiling/events-vsperfcmd.md).  
  
-   Per generare il report ETW, usare il comando **VSReport/Summary:ETW**. Per altre informazioni, vedere [VSPerfReport](../profiling/vsperfreport.md).  
  
|Colonna|Descrizione|  
|------------|-----------------|  
|**Timestamp**|Identifica il momento in cui si è verificato l'evento.|  
|**ID processo**|Identifica il processo che ha generato l'evento.|  
|**ID thread**|Identifica il thread che ha generato l'evento.|  
|**Descrizione**|Identifica il provider di eventi.|  
|**Type**|Identifica il tipo di evento.|  
|**Proprietà**|Le proprietà dell'evento. Ogni evento è una coppia nome-valore separata da virgola e racchiusa tra parentesi.|