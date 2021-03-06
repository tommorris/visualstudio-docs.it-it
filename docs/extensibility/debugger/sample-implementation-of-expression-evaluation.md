---
title: Implementazione della valutazione dell'espressione di esempio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
- expression evaluation, examples
ms.assetid: 2a5f04b8-6c65-4232-bddd-9093653a22c4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aac8e120880ba33b1479bd43ae43f5449c9e97d1
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251111"
---
# <a name="sample-implementation-of-expression-evaluation"></a>Esempio di implementazione della valutazione dell'espressione
> [!IMPORTANT]
>  In Visual Studio 2015, questa modalità di implementazione analizzatori di espressioni è deprecata. Per informazioni sull'implementazione di analizzatori di espressioni CLR, vedere [analizzatori di espressioni CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) e [analizzatore di espressioni gestite esempio](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Per un **Watch** espressione della finestra, Visual Studio chiama [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) per produrre un' [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) oggetto. `IDebugExpressionContext2::ParseText` Crea un'istanza di un analizzatore di espressioni (EE) e chiama [analizzare](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) per ottenere un [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) oggetto.  
  
 Il `IDebugExpressionEvaluator::Parse` esegue le attività seguenti:  
  
1.  [Solo C++] Analizza l'espressione per cercare gli errori.  
  
2.  Crea un'istanza di una classe (chiamati `CParsedExpression` in questo esempio) che esegue il `IDebugParsedExpression` interfaccia e la archivia nella classe l'espressione da analizzare.  
  
3.  Restituisce il `IDebugParsedExpression` dell'interfaccia dal `CParsedExpression` oggetto.  
  
> [!NOTE]
>  Negli esempi che seguono e nell'esempio MyCEE, l'analizzatore di espressioni non separa il processo di analisi dalla valutazione.  
  
## <a name="managed-code"></a>Codice gestito  
 Il codice seguente viene illustrata un'implementazione di `IDebugExpressionEvaluator::Parse` nel codice gestito. Questa versione del metodo rinvia l'analisi e la [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) come valuta inoltre il codice per l'analisi nello stesso momento (vedere [valutare un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
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
Il codice seguente è un'implementazione di `IDebugExpressionEvaluator::Parse` nel codice non gestito. Questo metodo chiama una funzione helper `Parse`, analizzare l'espressione e verificare gli errori, ma questo metodo ignora il valore risultante. La versione di valutazione formale viene rinviata al giorno [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) in cui l'espressione viene analizzato quando viene valutata (vedere [valutare un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```cpp  
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
 [Valutare un'espressione di finestra Espressioni di controllo](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [Valutare un'espressione di controllo](../../extensibility/debugger/evaluating-a-watch-expression.md)