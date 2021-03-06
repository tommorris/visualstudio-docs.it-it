---
title: Contesto di valutazione di espressioni | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9a01d8fd9e1ac7a439898775bc8b4b0fc933650c
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232494"
---
# <a name="expression-evaluation-context"></a>Contesto di valutazione dell'espressione
Nelle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] debug, un' **contesto di valutazione dell'espressione**:  
  
-   Rappresenta un contesto per la valutazione dell'espressione. Un contesto di valutazione corrisponde in genere, per l'ambito lessicale in cui valutare le variabili, parametri, funzioni e metodi. Ad esempio, un contesto di valutazione di espressioni associato a uno stack frame fornirà il contesto per la valutazione delle variabili locali, parametri del metodo e i membri della classe (se applicabile).  
  
-   Si verifica quando un programma viene arrestata in corrispondenza di un punto di interruzione. L'espressione stessa è una struttura di data che rappresenta un'espressione analizzata che è pronta per l'associazione e la valutazione all'interno del contesto specificato.  
  
     In modo più dettagliato, le espressioni vengono create usando il [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) (metodo). Quando viene valutata un'espressione, viene generata una stringa stampabile che contiene il nome e il tipo di variabile o argomento e il relativo valore. Questa stringa viene visualizzata nella finestra Espressioni di controllo o nella finestra variabili locali dell'IDE.  
  
     Dato un `BSTR` e un' [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) interfaccia, è possibile creare un motore di debug (DE) un' [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) interfaccia tramite l'analisi di un'espressione. Dato un `IDebugExpression2` interfaccia, la Germania possa ottenere un valore tramite valutazione dell'espressione sincrone o asincrone. Questo valore, insieme al nome e tipo della variabile o argomento, viene inviato all'IDE per la visualizzazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di valutazione di espressioni](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Contesti del debugger](../../extensibility/debugger/debugger-contexts.md)