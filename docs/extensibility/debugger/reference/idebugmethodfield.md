---
title: IDebugMethodField | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField
helpviewer_keywords:
- IDebugMethodField interface
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b42f37e0418ec354b522da102adaff3653cfc6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31118031"
---
# <a name="idebugmethodfield"></a>IDebugMethodField
Questa interfaccia viene descritto un metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
IDebugMethodField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Note per gli implementatori  
 Un provider di simboli implementa questa interfaccia sullo stesso oggetto che implementa il [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfaccia. Questa interfaccia è una specializzazione che viene presentato un metodo.  
  
## <a name="notes-for-callers"></a>Note per i chiamanti  
 Utilizzare [QueryInterface](/cpp/atl/queryinterface) per questa interfaccia da ottenere il [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfaccia se [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) restituisce `FIELD_TYPE_METHOD`. Inoltre, i metodi, [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md), [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md), e [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md), restituiscono tutti il `IDebugMethodField` interfaccia.  
  
## <a name="methods-in-vtable-order"></a>Metodi nell'ordine Vtable  
 Oltre ai metodi nel [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) e [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfacce, questa interfaccia implementa i metodi seguenti:  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|Crea un enumeratore per i parametri del metodo.|  
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|Ottiene il puntatore "this" dell'oggetto che contiene il metodo.|  
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|Crea un enumeratore per tutte le variabili locali del metodo.|  
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|Crea un enumeratore per le variabili locali selezionate del metodo.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|Determina se è stato definito un attributo personalizzato specifico.|  
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|Crea un enumeratore per le variabili locali statiche del metodo.|  
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|Ottiene il contenitore globale del metodo.|  
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|Crea un enumeratore per il tipo di ogni argomento è necessario chiamare il metodo.|  
  
## <a name="remarks"></a>Note  
 Un metodo può contenere parametri nonché le variabili locali.  
  
## <a name="requirements"></a>Requisiti  
 Intestazione: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce del Provider di simboli](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)