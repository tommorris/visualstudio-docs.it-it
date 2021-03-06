---
title: Abilitazione di un programma da sottoporre a debug | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad6e8e9cb8dd34e3cd084bde1eb94ff5774dd4ba
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204388"
---
# <a name="enable-a-program-to-be-debugged"></a>Abilitare un programma da sottoporre a debug
Prima che il motore di debug (DE) può eseguire il debug di un programma, è necessario avviare il DE o collegarlo a un programma esistente.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Ottenere una porta](../../extensibility/debugger/getting-a-port.md)  
 Viene illustrato come ottenere una porta come il primo passaggio per abilitare un programma da sottoporre a debug.  
  
 [Registrare il programma](../../extensibility/debugger/registering-the-program.md)  
 Viene illustrato il passaggio successivo di abilitazione di un programma da sottoporre a debug: registrandola con la porta. Una volta registrato, il programma di debug può essere eseguito tramite il processo di collegamento o il debug just-in-time (JIT).  
  
 [Collegare al programma](../../extensibility/debugger/attaching-to-the-program.md)  
 Viene illustrato il passaggio successivo: collegare il debugger al programma.  
  
 [Collegamento basato su avvio](../../extensibility/debugger/launch-based-attachment.md)  
 Descrive basato su avvio allegato a un programma, che risulta automatico all'avvio per il modello SDM.  
  
 [Inviare gli eventi richiesti](../../extensibility/debugger/sending-the-required-events.md)  
 Procedura per gli eventi necessari quando si crea un motore di debug (DE) e collegarlo a un programma.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Creazione di un motore di debug personalizzato](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Definisce un motore di debug (DE) e vengono descritti i servizi implementati tramite le interfacce DE e come possono causare il debugger per la transizione tra diverse modalità operative.