---
title: 'Procedura: proteggere a livello di codice le cartelle di lavoro'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, passwords
- documents [Office development in Visual Studio], document protection
- workbooks, unprotecting
- document protection, removing from workbooks
- document protection, adding to workbooks
- workbooks, protecting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8999bb1e30958897f9b7732ab393650320ec77b1
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "35671911"
---
# <a name="how-to-programmatically-protect-workbooks"></a>Procedura: proteggere a livello di codice le cartelle di lavoro
  È possibile proteggere una cartella di lavoro di Microsoft Office Excel in modo che gli utenti non possono aggiungere o eliminare fogli di lavoro e anche rimuovere la protezione della cartella di lavoro a livello di codice. È facoltativamente possibile specificare una password, indicare se si desidera proteggere (in modo che gli utenti non possono spostare i fogli) la struttura e indicare se si vuole windows della cartella di lavoro protetti.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 La protezione di una cartella di lavoro non impedisce agli utenti di modificare le celle. Per proteggere i dati, è necessario proteggere i fogli di lavoro. Per altre informazioni, vedere [procedura: proteggere i fogli di lavoro a livello di programmazione](../vsto/how-to-programmatically-protect-worksheets.md).  
  
 Gli esempi di codice seguente usano una variabile per contenere una password ottenuta dall'utente.  
  
## <a name="protect-a-workbook-that-is-part-of-a-document-level-customization"></a>Proteggere una cartella di lavoro che fa parte di una personalizzazione a livello di documento  
  
### <a name="to-protect-a-workbook"></a>Per proteggere una cartella di lavoro  
  
1.  Chiamare il <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> metodo della cartella di lavoro e includere una password. Per usare il codice seguente, eseguirlo `ThisWorkbook` classe, non in una classe del foglio.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#10)]
     [!code-vb[Trin_VstcoreExcelAutomation#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#10)]  
  
### <a name="to-unprotect-a-workbook"></a>Per rimuovere la protezione di una cartella di lavoro  
  
1.  Chiamare il <xref:Microsoft.Office.Tools.Excel.Workbook.Unprotect%2A> , passando una password se richiesto. Per usare il codice seguente, eseguirlo `ThisWorkbook` classe, non in una classe del foglio.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/ThisWorkbook.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/ThisWorkbook.vb#11)]  
  
## <a name="protect-a-workbook-by-using-an-application-level-add-in"></a>Proteggere una cartella di lavoro usando un componente aggiuntivo a livello di applicazione  
  
### <a name="to-protect-a-workbook"></a>Per proteggere una cartella di lavoro  
  
1.  Chiamare il <xref:Microsoft.Office.Interop.Excel._Workbook.Protect%2A> metodo della cartella di lavoro e includere una password. Questo esempio di codice Usa la cartella di lavoro attiva. Per usare questo esempio, eseguire il codice dalla classe `ThisAddIn` nel progetto.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#6)]  
  
### <a name="to-unprotect-a-workbook"></a>Per rimuovere la protezione di una cartella di lavoro  
  
1.  Chiamare il <xref:Microsoft.Office.Interop.Excel._Workbook.Unprotect%2A> metodo della cartella di lavoro attivo, passando una password, se necessario. Per usare questo esempio, eseguire il codice dalla classe `ThisAddIn` nel progetto.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 [Lavorare con le cartelle di lavoro](../vsto/working-with-workbooks.md)   
 [Procedura: proteggere i fogli di lavoro a livello di codice](../vsto/how-to-programmatically-protect-worksheets.md)   
 [Procedura: nascondere i fogli di lavoro a livello di codice](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Parametri facoltativi nelle soluzioni Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  