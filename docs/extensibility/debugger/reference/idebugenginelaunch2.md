---
title: IDebugEngineLaunch2 | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1abff9f393b34bbf5950c9e56b6f489f332840db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113247"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
Usato dal motore di debug (DE) per avviare e interrompere i programmi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Note per gli implementatori  
 Questa interfaccia è implementata da un DE personalizzato se dispone di requisiti speciali per avviare un processo che non può essere gestito interamente da una porta personalizzata. Ciò avviene in genere quando la Germania fa parte di un interprete e il processo in corso il debug è uno script: l'interprete deve essere avviato prima e quindi lo script viene caricato e avviato. Una porta in grado di avviare l'interprete, ma lo script può richiedere una gestione speciale (che dispone di un ruolo in cui la Germania). Questa interfaccia è implementata solo se esistono requisiti specifici per l'avvio di un programma che non può gestire una porta personalizzata.  
  
## <a name="notes-for-callers"></a>Note per i chiamanti  
 Questa interfaccia viene chiamata dal gestore di sessione di debug (SDM) se il SDM è possibile ottenere l'interfaccia dal [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) interfaccia (tramite QueryInterface). Se questa interfaccia può essere ottenuta il SDM sa che la Germania è previsti requisiti speciali e chiama questa interfaccia per avviare il programma anziché la porta di avviarlo.  
  
## <a name="methods-in-vtable-order"></a>Metodi nell'ordine Vtable  
 Nella tabella seguente sono illustrati i metodi di `IDebugEngineLaunch2`.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Avvia un processo tramite la Germania.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Esecuzione dei processi viene ripreso.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Determina se un processo può essere terminato.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Interrompe un processo.|  
  
## <a name="requirements"></a>Requisiti  
 Intestazione: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vedere anche  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)