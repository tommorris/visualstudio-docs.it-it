---
title: CODE_PATH | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CODE_PATH
helpviewer_keywords:
- CODE_PATH structure
ms.assetid: 2d4b2890-4c9d-47e1-83c0-df9c6436427f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f77ddf898732938f5a63c32ff26dd60e5a948e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47526283"
---
# <a name="codepath"></a>CODE_PATH
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [CODE_PATH](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/code-path).  
  
Descrive una chiamata di metodo o funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp#  
typedef struct tagCODE_PATH {   
   BSTR                bstrName;  
   IDebugCodeContext2* pCode;  
} CODE_PATH;  
```  
  
```csharp  
public struct CODE_PATH {  
   public string            bstrName;  
   public IDebugCodeContext pCode;  
}  
```  
  
## <a name="members"></a>Membri  
 bstrName  
 Il nome del percorso del codice.  
  
 pCode  
 Il [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) che identifica la posizione del codice per eseguire una funzione.  
  
## <a name="remarks"></a>Note  
 Questa struttura viene utilizzata per implementare l'esecuzione di una funzione. [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) restituisce tutte le chiamate dalla posizione corrente nel programma sottoposto a debug. Questa struttura rappresenta una chiamata di questo tipo.  
  
## <a name="requirements"></a>Requisiti  
 Intestazione: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture e unioni](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md)

