---
title: IDebugProgram2::EnumCodePaths | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::EnumCodePaths
helpviewer_keywords:
- IDebugProgram2::EnumCodePaths
ms.assetid: fb100c3c-9c29-4d63-bd1f-a3e531cb395f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56cc9580ec2e434066d1c0a3ce674a4111e433af
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122184"
---
# <a name="idebugprogram2enumcodepaths"></a>IDebugProgram2::EnumCodePaths
Recupera un elenco di percorsi del codice per una determinata posizione nel file di origine.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumCodePaths(   
   LPCOLESTR            pszHint,  
   IDebugCodeContext2*  pStart,  
   IDebugStackFrame2*   pFrame,  
   BOOL                 fSource,  
   IEnumCodePaths2**    ppEnum,  
   IDebugCodeContext2** ppSafety  
);  
```  
  
```csharp  
int EnumCodePaths(   
   string                 pszHint,  
   IDebugCodeContext2     pStart,  
   IDebugStackFrame2      pFrame,  
   Int                    fSource,  
   out IEnumCodePaths2    ppEnum,  
   out IDebugCodeContext2 ppSafety  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pszHint`  
 [in] La parola sotto il cursore nel **origine** o **Disassembly** vista nell'IDE.  
  
 `pStart`  
 [in] Un [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) oggetto che rappresenta il contesto del codice corrente.  
  
 `pFrame`  
 [in] Un [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) dell'oggetto che rappresenta lo stack frame associato al punto di interruzione corrente.  
  
 `fSource`  
 [in] Diverso da zero (`TRUE`) se nel **origine** visualizzazione o zero (`FALSE`) se nel **Disassembly** visualizzazione.  
  
 `ppEnum`  
 [out] Restituisce un [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md) oggetto contenente un elenco di percorsi del codice.  
  
 `ppSafety`  
 [out] Restituisce un [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) dell'oggetto che rappresenta un contesto di codice aggiuntivi da impostare come un punto di interruzione in caso di percorso di codice scelto viene ignorata. Ciò può verificarsi nel caso di un'espressione booleana esegue un corto circuita, ad esempio.  
  
## <a name="return-value"></a>Valore restituito  
 Se ha esito positivo, restituisce `S_OK`; in caso contrario, restituisce un codice di errore.  
  
## <a name="remarks"></a>Note  
 Un percorso di codice descrive il nome di un metodo o una funzione che è stato chiamato per ottenere il punto nell'esecuzione del programma corrente. Un elenco di percorsi di codice rappresenta lo stack di chiamate.  
  
## <a name="see-also"></a>Vedere anche  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)