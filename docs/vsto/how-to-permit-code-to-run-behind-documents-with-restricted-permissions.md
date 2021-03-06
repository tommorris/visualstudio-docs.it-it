---
title: "Procedura: consentire l'esecuzione dietro i documenti con autorizzazioni limitate codice"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Information Rights Management [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- IRM [Office development in Visual Studio]
- code [Office development in Visual Studio], running behind restricted documents
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3b02afb7008233c720feae179b4726f9958a44af
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2018
ms.locfileid: "35255286"
---
# <a name="how-to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Procedura: consentire l'esecuzione dietro i documenti con autorizzazioni limitate codice
  È possibile usare la funzionalità Information Rights Management (IRM) di Microsoft Office per limitare le autorizzazioni a un documento o cartella di lavoro. Per impostazione predefinita, il codice dietro a un documento con limitazioni di Microsoft Office Word o una cartella di lavoro di Microsoft Office Excel non è consentito per l'esecuzione. È possibile modificare l'impostazione predefinita, in modo che le estensioni di codice gestito possono accedere il modello a oggetti e la soluzione funzionerà.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 È necessario essere l'autore del documento o cartella di lavoro o avere accesso completo sia in grado di modificare le impostazioni di autorizzazione.  
  
## <a name="to-permit-code-to-run-behind-documents-with-restricted-permissions"></a>Per consentire l'esecuzione dietro i documenti con autorizzazioni limitate del codice  
  
1.  Aprire il documento o cartella di lavoro in Word o Excel.  
  
2.  Fare clic sul **File** scheda, scegliere **Prepare**, scegliere **limita le autorizzazioni**, quindi fare clic su **accesso limitato**.  
  
    > [!NOTE]  
    >  Al primo uso, viene chiesto di installare il client Windows Rights Management. Dopo aver installato il client, si potrebbe essere necessario ripetere questi passaggi.  
  
3.  Nel **l'autorizzazione** finestra di dialogo **Limita autorizzazioni per documento**e quindi fare clic su **altre opzioni**.  
  
4.  Sotto **autorizzazioni aggiuntive per gli utenti**, selezionare **accedere al contenuto a livello di programmazione**.  
  
 Word o Excel verrà consentono l'accesso a livello di codice per il modello a oggetti.  
  
## <a name="see-also"></a>Vedere anche  
 [Information rights management e panoramica sulle estensioni di codice gestito](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [Protezione dei documenti nelle soluzioni a livello di documento](../vsto/document-protection-in-document-level-solutions.md)   
 [Password di protezione nei documenti di Office](../vsto/password-protection-on-office-documents.md)   
 [Progettare e creare soluzioni Office](../vsto/designing-and-creating-office-solutions.md)   
 [Proteggere le soluzioni Office](../vsto/securing-office-solutions.md)   
 [Distribuire una soluzione Office](../vsto/deploying-an-office-solution.md)  
  
  