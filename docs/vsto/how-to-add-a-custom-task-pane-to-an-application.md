---
title: "Procedura: aggiungere un riquadro attività personalizzato a un'applicazione"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], adding to application
- custom task panes [Office development in Visual Studio], adding to application
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b8608fcc263be4750c38b6fe3f84967f40dd34ab
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548814"
---
# <a name="how-to-add-a-custom-task-pane-to-an-application"></a>Procedura: aggiungere un riquadro attività personalizzato a un'applicazione
  È possibile aggiungere un riquadro attività personalizzato alle applicazioni elencate sopra usando un componente aggiuntivo VSTO. Per altre informazioni, vedere [riquadri attività personalizzati](../vsto/custom-task-panes.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  I nomi o i percorsi visualizzati per alcuni elementi dell'interfaccia utente di Visual Studio nelle istruzioni seguenti potrebbero essere diversi nel computer in uso. La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi. Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="add-a-custom-task-pane-to-an-application"></a>Aggiungere un riquadro attività personalizzato a un'applicazione  
  
### <a name="to-add-a-custom-task-pane-to-an-application"></a>Per aggiungere un riquadro attività personalizzato a un'applicazione  
  
1.  Aprire o creare un progetto di componente aggiuntivo VSTO per una delle applicazioni elencate sopra. Per altre informazioni, vedere [procedura: progetti di Office Create in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Nel menu **Progetto** fare clic su **Aggiungi controllo utente**.  
  
3.  Nel **Aggiungi nuovo elemento** finestra di dialogo, modificare il nome del nuovo controllo utente per **MyUserControl**, quindi fare clic su **Aggiungi**.  
  
     Il controllo utente viene visualizzato nella finestra di progettazione.  
  
4.  Aggiungere uno o più controlli Windows Form dal **della casella degli strumenti** al controllo utente.  
  
5.  Aprire il **ThisAddIn.cs** o **ThisAddIn. vb** file di codice.  
  
6.  Aggiungere il codice seguente alla classe `ThisAddIn` . Questo codice dichiara le istanze di `MyUserControl` e <xref:Microsoft.Office.Tools.CustomTaskPane> come membri della classe `ThisAddIn` .  
  
     [!code-vb[Trin_TaskPaneBasic#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#1)]
     [!code-csharp[Trin_TaskPaneBasic#1](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#1)]  
  
7.  Aggiungere il codice seguente al gestore eventi `ThisAddIn_Startup`. Questo codice crea un nuovo oggetto <xref:Microsoft.Office.Tools.CustomTaskPane> aggiungendo l'oggetto `MyUserControl` alla raccolta `CustomTaskPanes`. Il codice visualizza anche il riquadro attività.  
  
     [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
     [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]  
  
    > [!NOTE]  
    >  Questo codice associa il riquadro attività alla finestra attiva nell'applicazione. Per alcune applicazioni, si potrebbe voler modificare il codice perché il riquadro attività venga visualizzato con altri documenti o elementi nell'applicazione. Per altre informazioni, vedere [riquadri attività personalizzati](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzazione dell'interfaccia utente di Office](../vsto/office-ui-customization.md)   
 [Riquadri attività personalizzati](../vsto/custom-task-panes.md)   
 [Procedura dettagliata: Automatizzare un'applicazione da un riquadro attività personalizzato](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)  
  
  