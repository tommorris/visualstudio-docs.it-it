---
title: Implementazione della valutazione dell'espressione di esempio | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
- expression evaluation, examples
ms.assetid: 2a5f04b8-6c65-4232-bddd-9093653a22c4
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f500245a00a3c176d19f85f15655c64a512b6ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47527633"
---
# <a name="sample-implementation-of-expression-evaluation"></a>Implementazione di esempio di valutazione delle espressioni
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [esempio di implementazione della valutazione dell'espressione](https://docs.microsoft.com/visualstudio/extensibility/debugger/sample-implementation-of-expression-evaluation).  
  
> [!IMPORTANT]
>  In Visual Studio 2015, questa modalità di implementazione analizzatori di espressioni è deprecata. Per informazioni sull'implementazione di analizzatori di espressioni di Common Language Runtime, vedi [analizzatori di espressioni CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) e [gestito esempio analizzatore di espressioni](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Per un **Watch** espressione della finestra, Visual Studio chiama [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) per produrre un' [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) oggetto. `IDebugExpressionContext2::ParseText` Crea un'istanza di un analizzatore di espressioni (EE) e chiama [analizzare](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) per ottenere un [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) oggetto.  
  
 Questa implementazione di `IDebugExpressionEvaluator::Parse` esegue le attività seguenti:  
  
1.  [Solo C++] Analizza l'espressione per cercare gli errori.  
  
2.  Crea un'istanza di una classe (chiamati `CParsedExpression` in questo esempio) che implementa il `IDebugParsedExpression` interfaccia e la archivia nella classe l'espressione da analizzare.  
  
3.  Restituisce il `IDebugParsedExpression` dell'interfaccia dal `CParsedExpression` oggetto.  
  
> [!NOTE]
>  Negli esempi che seguono e nell'esempio MyCEE, l'analizzatore di espressioni non separa il processo di analisi dalla valutazione.  
  
## <a name="managed-code"></a>Codice gestito  
 Si tratta di un'implementazione di `IDebugExpressionEvaluator::Parse` nel codice gestito. Si noti che questa versione del metodo rinvia l'analisi e la [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) come valuta inoltre il codice per l'analisi nello stesso momento (vedere [la valutazione di un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```csharp  
namespace EEMC  
{  
    public class CParsedExpression : IDebugParsedExpression  
    {  
        public HRESULT Parse(  
                string                 expression,   
                uint                   parseFlags,  
                uint                   radix,  
            out string                 errorMessage,   
            out uint                   errorPosition,   
            out IDebugParsedExpression parsedExpression)  
        {   
            errorMessage = "";  
            errorPosition = 0;  
  
            parsedExpression =  
                new CParsedExpression(parseFlags, radix, expression);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Codice non gestito  
 Si tratta di un'implementazione di `IDebugExpressionEvaluator::Parse` nel codice non gestito. Questo metodo chiama una funzione helper `Parse`, analizzare l'espressione e verificare gli errori, ma questo metodo ignora il valore risultante. La versione di valutazione formale viene rinviata al giorno [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) in cui l'espressione viene analizzato quando viene valutata (vedere [la valutazione di un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```cpp#  
STDMETHODIMP CExpressionEvaluator::Parse(  
        in    LPCOLESTR                 pszExpression,  
        in    PARSEFLAGS                flags,  
        in    UINT                      radix,  
        out   BSTR                     *pbstrErrorMessages,  
        inout UINT                     *perrorCount,  
        out   IDebugParsedExpression  **ppparsedExpression  
    )  
{  
    if (pbstrErrorMessages == NULL)  
        return E_INVALIDARG;  
    else  
        *pbstrErrormessages = 0;  
  
    if (pparsedExpression == NULL)  
        return E_INVALIDARG;  
    else  
        *pparsedExpression = 0;  
  
    if (perrorCount == NULL)  
        return E_INVALIDARG;  
  
    HRESULT hr;  
    // Look for errors in the expression but ignore results  
    hr = ::Parse( pszExpression, pbstrErrorMessages );  
    if (hr != S_OK)  
        return hr;  
  
    CParsedExpression* pparsedExpr = new CParsedExpression( radix, flags, pszExpression );  
    if (!pparsedExpr)  
        return E_OUTOFMEMORY;  
  
    hr = pparsedExpr->QueryInterface( IID_IDebugParsedExpression,  
                                      reinterpret_cast<void**>(ppparsedExpression) );  
    pparsedExpr->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Valutazione di un'espressione di finestra Espressioni di controllo](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [Valutazione di un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)

