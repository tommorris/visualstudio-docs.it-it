---
title: Problemi di sicurezza | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6cd4d07721f202169ca0689882ac1a41045a4d61
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252323"
---
# <a name="security-issues"></a>Problemi di sicurezza
Per eseguire il debug di un programma che Usa Visual Studio, le sole autorizzazioni necessite sono uguali a quelle necessarie a eseguire il programma di uno sviluppatore. Sono inclusi il debug remoto per la maggior parte delle situazioni. Alcune situazioni, che includono altri servizi, ad esempio il servizio di informazioni Internet, potrebbero richiedere un livello superiore di autorizzazioni.  
  
 Mentre è in esecuzione Visual Studio, il gestore di debug di processi (PDM) tiene traccia dei processi di debug nel computer locale. In modalità remota, un programma denominato *msvsmon.exe* viene avviata dallo sviluppatore per gestire il debug remoto e rendere disponibile il PDM. (*msvsmon.exe* non è un servizio e deve essere avviata manualmente per abilitare il debug remoto su tale macchina.) Quando Visual Studio (o *msvsmon.exe*) è non in esecuzione, processi non vengono rilevati per il debug.  
  
 Uno sviluppatore può eseguire il debug di programmi che vengono avviati senza autorizzazioni speciali. Lo sviluppatore può anche eseguire il debug di processi avviati da un altro utente, se tale altra persona è un membro dello stesso gruppo di sicurezza. E, per abilitare il debug remoto, è necessario solo copiare i file necessari nel computer remoto e avviare *msvsmon.exe*. Per altre informazioni, vedere [debug remoto](../../debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Attività di debug](../../extensibility/debugger/debugging-tasks.md)   
 [Gestione debug del processo](../../extensibility/debugger/process-debug-manager.md)   
 [Debug remoto](../../debugger/remote-debugging.md)
