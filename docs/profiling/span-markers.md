---
title: Marcatori span | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.markers.span
ms.assetid: 736b7765-9c71-44d7-85e5-79787d13d91c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6952408611bfdd59a3d488db2a7f34524588edf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2018
---
# <a name="span-markers"></a>Marcatori di span
Un marcatore span rappresenta una fase significativa di un'applicazione. Ad esempio, è possibile usare uno span per rappresentare un intervallo di tempo durante il quale viene elaborato un particolare elemento di lavoro. La sua lunghezza rappresenta la durata della fase dell'applicazione corrispondente. La figura mostra uno span nel visualizzatore di concorrenza:  
  
 ![Marcatore span nel visualizzatore di concorrenza](../profiling/media/cvmarkerspan.png "CVMarkerSpan")  
Marcatore span nel visualizzatore di concorrenza  
  
## <a name="span-category"></a>Categoria degli span  
 Un marcatore span viene visualizzato in uno dei cinque diversi colori seguenti, a seconda della categoria. I colori vengono ripetuti se sono presenti più di cinque categorie. La categoria può essere un numero intero qualsiasi. La figura mostra i cinque colori possibili:  
  
 ![Cinque span in categorie diverse](../profiling/media/cvmarkerspancategory.png "CVMarkerSpanCategory")  
Colori delle prime cinque categorie di span  
  
## <a name="span-aggregation-markers"></a>Marcatori di aggregazione di span  
 Talvolta gli indicatori span si presentano a così poca distanza tra loro nel visualizzatore di concorrenza da non poter essere rappresentati singolarmente. In questo caso, viene visualizzato un *marcatore di aggregazione di span* di colore grigio che rappresenta gli span sottostanti. Quando si posiziona il puntatore del mouse su una di queste icone, compare una descrizione comando che mostra il numero di span sottostanti rappresentati. Per visualizzare gli span, fare zoom avanti. Se viene fatto zoom avanti completamente e viene visualizzato ancora un marcatore di aggregazione di span, è possibile visualizzare i marcatori span sottostanti nel [rapporto Marcatori](../profiling/markers-report.md). La figura mostra un marcatore di aggregazione di span:  
  
 ![Marcatore di aggregazione di span nel visualizzatore di concorrenza](../profiling/media/cvmarkerspanaggregate.png "CVMarkerSpanAggregate")  
Marcatore di aggregazione di span  
  
## <a name="see-also"></a>Vedere anche  
 [Marcatori del visualizzatore di concorrenza](../profiling/concurrency-visualizer-markers.md)   
 [SDK del visualizzatore di concorrenza](../profiling/concurrency-visualizer-sdk.md)