---
title: "Procedura: il componente aggiuntivo Mostra errori dell'interfaccia utente"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dd6da0c83d0dee835169a0a8068af8d75facbbd4
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672735"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>Procedura: il componente aggiuntivo Mostra errori dell'interfaccia utente
  Per impostazione predefinita, se un componente aggiuntivo VSTO tenta di modificare l'interfaccia utente Microsoft Office (UI) e ha esito negativo, non viene visualizzato alcun messaggio di errore. È però possibile configurare le applicazioni di Microsoft Office in modo da visualizzare messaggi per gli errori correlati all'interfaccia utente. È possibile usare questi messaggi per determinare perché non viene visualizzata una barra multifunzione personalizzata, oppure perché viene visualizzata una barra multifunzione ma senza controlli.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="to-show-vsto-add-in-user-interface-errors"></a>Per visualizzare gli errori dell'interfaccia utente dei componenti aggiuntivi VSTO  
  
1.  Avviare l'applicazione.  
  
2.  Scegliere la scheda **File** .  
  
3.  Fare clic su **Opzioni**.  
  
4.  Nel riquadro delle categorie fare clic su **Avanzate**.  
  
5.  Nel riquadro dei dettagli selezionare **Mostra errori dell'interfaccia utente dei componenti aggiuntivi**, quindi fare clic su **OK**.  
  
    > [!NOTE]  
    >  Per Outlook, la casella di controllo **Mostra errori dell'interfaccia utente dei componenti aggiuntivi** si trova nella sezione **Sviluppo** del riquadro dei dettagli. Per altre applicazioni, la casella di controllo si trova nella sezione **Generale** del riquadro dei dettagli.  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzazione dell'interfaccia utente di Office](../vsto/office-ui-customization.md)   
 [Creare aree del modulo di Outlook](../vsto/creating-outlook-form-regions.md)   
 [Panoramica della barra multifunzione](../vsto/ribbon-overview.md)   
 [Panoramica del riquadro azioni](../vsto/actions-pane-overview.md)  
  
  