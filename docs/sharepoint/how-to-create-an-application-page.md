---
title: "Procedura: creare una pagina dell'applicazione | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eefbb12584cdff2bb32b9d4406c916969ec435c4
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118861"
---
# <a name="how-to-create-an-application-page"></a>Procedura: creare una pagina applicazione
  È possibile creare una pagina Web ASP.NET per uno o più siti di SharePoint. In SharePoint, queste pagine sono dette pagine dell'applicazione. A differenza di una pagina del sito, una pagina dell'applicazione contiene codice che viene eseguito dietro la pagina. Per altre informazioni, vedere [creare le pagine dell'applicazione per SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
### <a name="to-create-an-application-page"></a>Per creare una pagina dell'applicazione  
  
1.  In Visual Studio aprire o creare un progetto SharePoint.  
  
     Per altre informazioni, vedere [SharePoint modelli di elemento di progetto e progetto](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  Scegliere il nodo di progetto in **Esplora soluzioni**.  
  
3.  Nella barra dei menu scegliere **Progetto** > **Aggiungi nuovo elemento**.  
  
4.  Nel **Aggiungi nuovo elemento** finestra di dialogo espandere il **SharePoint** nodo e quindi scegliere il **2010** elemento.  
  
5.  Nell'elenco dei modelli di SharePoint, scegliere **pagina dell'applicazione**.  
  
6.  Nel **Name** casella, specificare un nome per la pagina dell'applicazione e quindi scegliere il **Add** pulsante.  
  
     Visual Studio aggiunge diversi file e cartelle nel progetto. Per altre informazioni su questi file, vedere [creare le pagine dell'applicazione per SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
     Nel **origine** visualizzazione della finestra di progettazione in Visual Web Developer, il file della pagina ASP.NET è disponibile. È possibile progettare la pagina aggiungendo i controlli dal **casella degli strumenti** e inserendoli nei segnaposti del contenuto. Per altre informazioni, vedere [visualizzazione origine, progettazione pagina Web](http://msdn.microsoft.com/en-us/5911396b-fe51-4150-9ff1-b085f812862f).  
  
7.  Se si desidera gestire gli eventi di controllo, aggiungere il codice al file di codice per la pagina applicazione.  
  
     Il file di codice viene visualizzato se si espande il nodo per il file della pagina ASP.NET e ha un *cs* oppure *vb* estensione, a seconda del linguaggio del progetto. Per un esempio end-to-end di come creare una pagina applicazione, vedere [procedura dettagliata: creare una pagina dell'applicazione SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md).  
  
## <a name="see-also"></a>Vedere anche
 [Creare le pagine dell'applicazione per SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Procedura dettagliata: Creare una pagina dell'applicazione SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
