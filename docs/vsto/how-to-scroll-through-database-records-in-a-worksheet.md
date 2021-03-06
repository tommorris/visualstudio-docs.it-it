---
title: 'Procedura: scorrere i record di database in un foglio di lavoro'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7e9ffaffdefda98e3e074467fcd4df8cacce91b4
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672882"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>Procedura: scorrere i record di database in un foglio di lavoro
  La procedura seguente viene illustrato come utilizzare la finestra di progettazione per visualizzare un singolo campo da una tabella di database in un foglio di lavoro di Microsoft Office Excel, con i controlli che consentono all'utente di scorrere tutti i record.  
  
 È possibile usare la finestra di progettazione solo nei progetti a livello di documento. Tuttavia, è possibile aggiungere controlli e associarli ai dati a livello di codice in fase di esecuzione. Per altre informazioni, vedere [procedura dettagliata: data binding semplice in progetto di componente aggiuntivo VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md).  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="to-scroll-through-database-records-in-a-worksheet"></a>Per scorrere i record di database in un foglio di lavoro  
  
1.  Aprire un progetto di applicazione di Excel in Visual Studio.  
  
2.  Aprire il **Zdroje dat** finestra e creare un'origine dati dal database. Per altre informazioni, vedere [aggiungere le nuove connessioni](../data-tools/add-new-connections.md).  
  
3.  Espandere la tabella che contiene i dati che si desidera visualizzare e selezionare la colonna specifica.  
  
4.  Aprire l'elenco dei controlli e selezionare **NamedRange**.  
  
5.  Trascinare il <xref:Microsoft.Office.Tools.Excel.NamedRange> controllo nella cella in cui si desidera visualizzare i dati.  
  
6.  Dal **Windows Forms** scheda della finestra di **della casella degli strumenti**, aggiungere un <xref:System.Windows.Forms.BindingNavigator> al foglio di lavoro e impostare i controlli da usare. Per altre informazioni, vedere [Cenni preliminari sul controllo BindingNavigator &#40;Windows Forms&#41;](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms).  
  
## <a name="see-also"></a>Vedere anche  
 [Associare dati a controlli nelle soluzioni Office](../vsto/binding-data-to-controls-in-office-solutions.md)  
  
  