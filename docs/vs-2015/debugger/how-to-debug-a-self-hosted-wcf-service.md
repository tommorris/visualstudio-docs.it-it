---
title: 'Procedura: eseguire il Debug di un servizio WCF Self-Hosted | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1e87af205a88e84942eb4958876c2030a175065
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47540551"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Procedura: eseguire il debug di un servizio WCF indipendente
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [procedura: eseguire il Debug di un servizio WCF Self-Hosted](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-a-self-hosted-wcf-service).  
  
Oggetto *servizio indipendente* è un servizio WCF che non viene eseguito in IIS, l'Host del servizio WCF o [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Development Server. Il modo più semplice per eseguire il debug di un servizio WCF indipendente consiste nel configurare [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] per avviare client e server quando si sceglie **Avvia debug** sul **Debug** menu.  
  
 Se il servizio WCF è Self-hosting interno o un processo che non può essere avviato in questo modo, ad esempio servizio NT, è possibile utilizzare questo metodo. In alternativa, è possibile eseguire una delle operazioni seguenti:  
  
-   Collegare manualmente il debugger al processo di hosting. Per altre informazioni, vedere [connettersi a processi in esecuzione](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     oppure  
  
-   Avviare il debug di client e quindi eseguire una chiamata al servizio. Ciò richiede l'abilitazione del debug nel file app. config. Per altre informazioni, [limitazioni del debug di WCF](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Per avviare l'host sia il client da Visual Studio  
  
1.  Creare un [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] soluzione contenente progetti sia il client e server.  
  
2.  Configurare la soluzione per avviare i processi client e server quando si sceglie **avviare** nel **Debug** menu.  
  
    1.  Nelle **Esplora soluzioni**, fare clic sul nome della soluzione.  
  
    2.  Fare clic su **Imposta progetti di avvio**.  
  
    3.  Nel **soluzione \<nome > proprietà** nella finestra di dialogo **progetti di avvio multipli**.  
  
    4.  Nel **progetti di avvio multipli** griglia, nella riga che corrisponde al progetto server, fare clic su **azione** e scegliere **avviare**.  
  
    5.  Nella riga che corrisponde al progetto client, fare clic su **azione** e scegliere **avviare**.  
  
    6.  Fare clic su **OK**.  
  
## <a name="see-also"></a>Vedere anche  
 [Debug dei servizi WCF](../debugger/debugging-wcf-services.md)   
 [Limitazioni del debug di WCF](../debugger/limitations-on-wcf-debugging.md)   
 [Procedura: Eseguire istruzioni nei servizi WCF](../debugger/how-to-step-into-wcf-services.md)



