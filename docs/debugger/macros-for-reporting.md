---
title: Macro per la creazione di report | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.macros
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- macros, CRT reporting macros
- macros, debugging with
- _RPTFn macro
- CRT, reporting macros
- debugging [CRT], reporting macros
- _RPTn macro
ms.assetid: f2085314-a3a8-4caf-a5a4-2af9ad5aad05
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57b254323fac5d670cd44399cd8d22c9530c4510
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056602"
---
# <a name="macros-for-reporting"></a>Macro per la creazione di rapporti
Per eseguire il debug, è possibile usare la **RPTn** e **RPTFn** macro, definite in CRTDBG. H, per sostituire l'uso di `printf` istruzioni. Non devi inclose nella **#ifdef**s, poiché essi vengono automaticamente eliminate nel rilascio quando compilare **debug** non è definito.  
  
|Macro|Descrizione|  
|-----------|-----------------|  
|**_RPT0**, **_RPT1**, **_RPT2**, **_RPT3**, **_RPT4**|Genera una stringa di messaggio e da zero a quattro argomenti. Da _rpt1 a **_RPT4**, la stringa di messaggio funge da stringa di formattazione stile printf per gli argomenti.|  
|**_RPTF0**, **_RPTF1**, **_RPTF2**, **_RPTF4**|Uguale allo **RPTn**, ma queste macro generano anche il numero di riga e il nome del file in cui si trova la macro.|  
  
 Si consideri l'esempio seguente:  
  
```cpp
#ifdef _DEBUG  
    if ( someVar > MAX_SOMEVAR )  
        printf( "OVERFLOW! In NameOfThisFunc( ),  
               someVar=%d, otherVar=%d.\n",  
               someVar, otherVar );  
#endif  
```  
  
 Questo codice genera i valori della `someVar` e `otherVar` al **stdout**. È possibile utilizzare la chiamata di `_RPTF2` che segue per restituire questi stessi valori nonché il nome file e il numero di riga:  
  
```cpp
if (someVar > MAX_SOMEVAR) _RPTF2(_CRT_WARN, "In NameOfThisFunc( ), someVar= %d, otherVar= %d\n", someVar, otherVar );  
```  
  
È possibile che una particolare applicazione necessiti di report di debug che non forniscono le macro fornite con la libreria di runtime C. In questi casi, è possibile scrivere una macro progettata appositamente per rispondere alle proprie esigenze. In uno dei file di intestazione, ad esempio, è possibile includere codice simile al seguente per definire una macro denominata **ALERT_IF2**:  
  
```cpp
#ifndef _DEBUG                  /* For RELEASE builds */  
#define  ALERT_IF2(expr, msg, arg1, arg2)  do {} while (0)  
#else                           /* For DEBUG builds   */  
#define  ALERT_IF2(expr, msg, arg1, arg2) \  
    do { \  
        if ((expr) && \  
            (1 == _CrtDbgReport(_CRT_ERROR, \  
                __FILE__, __LINE__, msg, arg1, arg2))) \  
            _CrtDbgBreak( ); \  
    } while (0)  
#endif  
```  
  
 Una chiamata a **ALERT_IF2** è stato possibile eseguire tutte le funzioni delle **printf** codice:  
  
```cpp
ALERT_IF2(someVar > MAX_SOMEVAR, "OVERFLOW! In NameOfThisFunc( ),   
someVar=%d, otherVar=%d.\n", someVar, otherVar );  
```  
  
 È possibile modificare facilmente una macro personalizzata per segnalare più o meno informazioni a destinazioni diverse. Questo approccio è particolarmente utile man mano che cambiano le esigenze di debug.  
  
## <a name="see-also"></a>Vedere anche  
 [Tecniche di debug CRT](../debugger/crt-debugging-techniques.md)
