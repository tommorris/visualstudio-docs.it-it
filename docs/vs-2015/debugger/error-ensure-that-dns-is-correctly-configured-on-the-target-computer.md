---
title: 'Errore: Verificare che DNS sia configurato correttamente nel Computer di destinazione | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2d364caf-73af-4186-bf9b-af186331cbe8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f0be44e07a42b132f00b476aa7cf4148720933a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47525506"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Errore: verificare che il DNS sia configurato correttamente nel computer di destinazione.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [errori: verificare che il DNS sia configurato correttamente nel Computer di destinazione](https://docs.microsoft.com/visualstudio/debugger/error-ensure-that-dns-is-correctly-configured-on-the-target-computer).  
  
Quando si tenta di eseguire il debug remoto, potrebbe essere visualizzato il seguente messaggio di errore:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 Questo errore si verifica quando il computer di destinazione non è in grado di risolvere il nome del computer host del debugger Visual Studio. Verificare le impostazioni DNS del computer di destinazione.  
  
-   Per informazioni sulla visualizzazione della configurazione del DNS in Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 o Windows Server 2008 R2, eseguire questa operazione: sul **avviare** menu, scegliere **Guida e supporto tecnico** e quindi cercare **delle impostazioni di modifica TCP/IP**.  
  
-   Per altre informazioni, visitare [sito web Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) e cercare **le impostazioni di modifica TCP/IP**.  
  
 Se è possibile risolvere il problema DNS, è possibile provare a eseguire il debugger remoto con un account diverso. L'errore si verifica quando è in esecuzione il debugger remoto con l'account del sistema locale o l'account del servizio di rete. Se si esegue il debugger remoto con un altro account, è possibile usare l'autenticazione NTLM, che non richiede il DNS. . Per istruzioni, vedere [errori: servizio di Visual Studio Remote Debugger nel computer di destinazione non può connettersi al computer](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).



