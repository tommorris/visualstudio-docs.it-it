---
title: Enumerazione PROFILER_HEAP_OBJECT_FLAGS | Documenti Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0f517743-cc4a-4911-add3-a43680071a1f
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 96e05d67bedcf03c97edc1015c80b212b6021562
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2017
ms.locfileid: "24734131"
---
# <a name="profilerheapobjectflags-enumeration"></a>Enumerazione PROFILER_HEAP_OBJECT_FLAGS
Flag che rappresentano informazioni di base sull'oggetto heap. Utilizzato nel [struttura PROFILER_HEAP_OBJECT](../../winscript/reference/profiler-heap-object-structure.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_FLAGS_NEW_OBJECT            = 0x00000001,    PROFILER_HEAP_OBJECT_FLAGS_IS_ROOT               = 0x00000002,    PROFILER_HEAP_OBJECT_FLAGS_SITE_CLOSED           = 0x00000004,    PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL              = 0x00000008,    PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL_UNKNOWN      = 0x00000010,    PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL_DISPATCH     = 0x00000020,    PROFILER_HEAP_OBJECT_FLAGS_SIZE_APPROXIMATE      = 0x00000040,    PROFILER_HEAP_OBJECT_FLAGS_SIZE_UNAVAILABLE      = 0x00000080,    PROFILER_HEAP_OBJECT_FLAGS_NEW_STATE_UNAVAILABLE = 0x00000100,    PROFILER_HEAP_OBJECT_FLAGS_WINRT_INSTANCE        = 0x00000200,    PROFILER_HEAP_OBJECT_FLAGS_WINRT_RUNTIMECLASS    = 0x00000400,    PROFILER_HEAP_OBJECT_FLAGS_WINRT_DELEGATE        = 0x00000800,    PROFILER_HEAP_OBJECT_FLAGS_WINRT_NAMESPACE       = 0x00001000,} PROFILER_HEAP_OBJECT_FLAGS;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Valore|Descrizione|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_FLAGS_NEW_OBJECT|0x00000001|Questo oggetto heap è stato allocato dopo la precedente richiesta di enumerazione dell'heap. [Tipo PROFILER_HEAP_OBJECT_ID](../../winscript/reference/profiler-heap-object-id-type.md) valori possono essere riutilizzati se l'oggetto è stato raccolto.|  
|PROFILER_HEAP_OBJECT_FLAGS_IS_ROOT|0x00000002|Questo oggetto heap è un oggetto radice dell'oggetto grafico.|  
|PROFILER_HEAP_OBJECT_FLAGS_SITE_CLOSED|0x00000004|Questo oggetto heap proviene da un sito di script che è stata chiusa.|  
|PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL|0x00000008|Questo oggetto heap è stato allocato all'esterno di heap di garbage collection JavaScript.|  
|PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL_UNKNOWN|0x00000010|Questo oggetto heap è stato allocato di fuori dell'heap di garbage collection e implementa IUnknown.|  
|PROFILER_HEAP_OBJECT_FLAGS_EXTERNAL_DISPATCH|0x00000020|Questo oggetto heap è stato allocato all'esterno di heap di garbage collection e implementa l'interfaccia IDISPATCH.|  
|PROFILER_HEAP_OBJECT_FLAGS_SIZE_APPROXIMATE|0x00000040|Le dimensioni di questo oggetto heap sono approssimative.|  
|PROFILER_HEAP_OBJECT_FLAGS_SIZE_UNAVAILABLE|x00000080|Le dimensioni di questo oggetto heap non sono disponibile.|  
|PROFILER_HEAP_OBJECT_FLAGS_WINRT_INSTANCE|0x00000200|L'oggetto dell'heap è un'istanza di Windows Runtime.|  
|PROFILER_HEAP_OBJECT_FLAGS_WINRT_RUNTIMECLASS|0x00000400|L'oggetto dell'heap è una classe di runtime di Windows Runtime.|  
|PROFILER_HEAP_OBJECT_FLAGS_WINRT_DELEGATE|0x00000800|L'oggetto dell'heap è un delegato di Windows Runtime.|  
|PROFILER_HEAP_OBJECT_FLAGS_WINRT_NAMESPACE|0x00001000|L'oggetto dell'heap è nello spazio dei nomi di Windows Runtime.|