---
title: 'Procedura: riempire a livello di codice automaticamente gli intervalli con dati modificati in modo incrementale'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a4fff7eb59ff2fe5e17ddf500bf546502492634d
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256403"
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Procedura: riempire a livello di codice automaticamente gli intervalli con dati modificati in modo incrementale
  Il <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metodo del <xref:Microsoft.Office.Interop.Excel.Range> consente di inserire automaticamente un intervallo in un foglio di lavoro con i valori. In genere, il <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metodo viene usato per archiviare in modo incrementale aumentando o diminuendo i valori in un intervallo. È possibile specificare il comportamento, fornendo una costante facoltativa dal <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> enumerazione.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Quando si usa, è necessario specificare due intervalli <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   L'intervallo che chiama il <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metodo, che specifica il punto di partenza del riempimento e contiene un valore iniziale.  
  
-   L'intervallo che si desidera compilare, passato come parametro per il <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> (metodo). Questo intervallo di destinazione deve includere l'intervallo che contiene il valore iniziale.  
  
    > [!NOTE]  
    >  Non è possibile passare un <xref:Microsoft.Office.Tools.Excel.NamedRange> invece di controllare il <xref:Microsoft.Office.Interop.Excel.Range>. Per altre informazioni, vedere [limitazioni a livello di codice degli elementi host e controlli host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 La prima cella dell'intervallo che si desidera compilare deve contenere un valore iniziale.  
  
 Nell'esempio si presuppone che si compila tre aree:  
  
-   La colonna B consiste nell'includere cinque giorni lavorativi. Il valore iniziale, digitare **lunedì** nella cella B1.  
  
-   La colonna C consiste nell'includere cinque mesi. Il valore iniziale, digitare **gennaio** nella cella C1.  
  
-   La colonna D consiste nell'includere una serie di numeri, con incrementi di due per ogni riga. Per i valori iniziali, digitare **4** nella cella D1 e **6** nella cella D2.  
  
## <a name="see-also"></a>Vedere anche  
 [Lavorare con intervalli](../vsto/working-with-ranges.md)   
 [Procedura: fare riferimento a livello di programmazione agli intervalli di foglio di lavoro nel codice](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Procedura: a livello di programmazione applicare stili agli intervalli in cartelle di lavoro](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [Procedura: eseguire calcoli in Excel](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [Cenni preliminari sui controlli host e gli elementi host](../vsto/host-items-and-host-controls-overview.md)   
 [Parametri facoltativi nelle soluzioni Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  