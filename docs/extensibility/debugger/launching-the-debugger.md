---
title: L'avvio del Debugger | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], launching the debugger
- debugger [Debugging SDK], launching
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1b1cc4a75a17ea686ef5c5c5c75e21f1c5f74de8
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231116"
---
# <a name="launch-the-debugger"></a>Avviare il debugger
L'avvio del debugger richiede l'invio di sequenza corretta di metodi ed eventi con i relativi attributi appropriati.  
  
## <a name="sequences-of-methods-and-events"></a>Sequenze di metodi ed eventi  
  
1.  Gestore di sessione di debug (SDM) viene chiamato, scegliendo la **eseguire il Debug** menu e quindi selezionando **avviare**. Per altre informazioni, vedere [avviare un programma](../../extensibility/debugger/launching-a-program.md).  
  
2.  Le chiamate SDM [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) (metodo).  
  
3.  In base al modello di processo (DE) del motore di debug, il `IDebugProgramNodeAttach2::OnAttach` metodo restituisce uno dei metodi seguenti, che determina ciò che accade.  
  
     Se `S_FALSE` restituito, il motore di debug (DE) deve essere caricato in fase di macchina virtuale.  
  
     oppure  
  
     Se `S_OK` restituito, la Germania deve essere caricato in-process del messaggio SDM. Il modello SDM esegue quindi le attività seguenti:  
  
    1.  Le chiamate [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) per ottenere le informazioni del motore della DE.  
  
    2.  CO-crea il DE.  
  
    3.  Le chiamate [collegare](../../extensibility/debugger/reference/idebugengine2-attach.md).  
  
4.  L'invio di DE un' [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) per il modello SDM con un `EVENT_SYNC` attributo.  
  
5.  L'invio di DE un' [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) per il modello SDM con un `EVENT_SYNC` attributo.  
  
6.  L'invio di DE un' [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) per il modello SDM con un `EVENT_SYNC` attributo.  
  
7.  L'invio di DE un' [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) per il modello SDM con un `EVENT_SYNC` attributo.  
  
8.  L'invio di DE un' [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) per il modello SDM con un `EVENT_SYNC` attributo.  
  
## <a name="see-also"></a>Vedere anche  
 [La chiamata a eventi del debugger](../../extensibility/debugger/calling-debugger-events.md)   
 [Avvio di un programma](../../extensibility/debugger/launching-a-program.md)