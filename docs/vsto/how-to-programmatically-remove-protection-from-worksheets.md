---
title: 'Procedura: rimuovere la protezione dai fogli di lavoro a livello di codice'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e15fd2f2d4a025155bbaa1d39dc5c38155b452e2
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "35673471"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>Procedura: rimuovere la protezione dai fogli di lavoro a livello di codice
  È possibile rimuovere la protezione a livello di codice da un foglio di lavoro di Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 L'esempio seguente usa la variabile `getPasswordFromUser`, che contiene una password ottenuta dall'utente.  
  
## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>Per rimuovere la protezione da un foglio di lavoro in una personalizzazione a livello di documento  
  
1.  Chiamare il <xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A> metodo del foglio di lavoro e passare la password, se necessario. Questo esempio presuppone l'utilizzo di un foglio di lavoro denominato `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]  
  
## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>Per rimuovere la protezione di un foglio di lavoro in un componente aggiuntivo VSTO  
  
1.  Chiamare il <xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A> metodo del foglio di lavoro attivo e passare la password, se necessario.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]  
  
## <a name="see-also"></a>Vedere anche  
 [Usare i fogli di lavoro](../vsto/working-with-worksheets.md)   
 [Procedura: proteggere i fogli di lavoro a livello di codice](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Procedura: proteggere a livello di codice le cartelle di lavoro](../vsto/how-to-programmatically-protect-workbooks.md)   
 [Procedura: nascondere i fogli di lavoro a livello di codice](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Accesso globale a oggetti nei progetti di Office](../vsto/global-access-to-objects-in-office-projects.md)  
  
  