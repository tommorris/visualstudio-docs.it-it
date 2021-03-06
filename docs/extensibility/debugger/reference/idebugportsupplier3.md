---
title: IDebugPortSupplier3 | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier3
helpviewer_keywords:
- IDebugPortSupplier3 interface
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d5a35e212c98d6e62b667c4305d8ae4874feb3aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116997"
---
# <a name="idebugportsupplier3"></a>IDebugPortSupplier3
Questa interfaccia consente a un chiamante di determinare se un fornitore di porta può mantenere porte (mediante la scrittura su disco) tra le chiamate del debugger e quindi ottenere un elenco di tali porte mantenuti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## <a name="notes-for-implementers"></a>Note per gli implementatori  
 Un fornitore di porta personalizzato implementa questa interfaccia per supportare la persistenza o il salvataggio delle informazioni sulla porta su disco. Questa interfaccia deve essere implementata per l'oggetto stesso come il [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) interfaccia.  
  
## <a name="notes-for-callers"></a>Note per i chiamanti  
 Chiamare [QueryInterface](/cpp/atl/queryinterface) sul `IDebugPortSupplier2` interfaccia per ottenere questa interfaccia.  
  
## <a name="methods-in-vtable-order"></a>Metodi nell'ordine Vtable  
 Oltre ai metodi ereditati dal [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) , questa interfaccia supporta i seguenti:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|Restituisce se il fornitore della porta può rendere persistente porte (mediante la scrittura su disco) tra le chiamate del debugger.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|Restituisce un oggetto che può essere utilizzato per enumerare tramite tutte le porte che sono stati scritti su disco per il fornitore della porta.|  
  
## <a name="remarks"></a>Note  
 Se un fornitore di porta può rendere persistente porte tra chiamate, deve implementare questa interfaccia. Porte devono essere caricate quando viene creata un'istanza, il fornitore della porta e scritto su disco quando il fornitore della porta viene eliminato definitivamente.  
  
 In genere, un motore di debug non interagisce con un fornitore di porta e non disporrà di alcuna utilità per l'interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 Intestazione: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di base](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)