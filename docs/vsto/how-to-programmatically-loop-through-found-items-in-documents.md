---
title: 'Procedura: scorrere gli elementi trovati nei documenti a livello di codice in ciclo'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- loops, through found items in documents
- documents [Office development in Visual Studio], searching
- text [Office development in Visual Studio], searching in documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0ff9a85319ac35e051b41ff65ab5b027dc226f44
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "35672871"
---
# <a name="how-to-programmatically-loop-through-found-items-in-documents"></a>Procedura: scorrere gli elementi trovati nei documenti a livello di codice in ciclo
  Nella classe <xref:Microsoft.Office.Interop.Word.Find> è presente una proprietà <xref:Microsoft.Office.Interop.Word.Find.Found%2A> , che restituisce **true** ogni volta che viene trovato un elemento di cui è stata effettuata la ricerca. Per scorrere in ciclo tutte le istanze trovate in un oggetto <xref:Microsoft.Office.Interop.Word.Range> , è possibile usare il metodo <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> .  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="to-loop-through-found-items"></a>Per scorrere in ciclo gli elementi trovati  
  
1.  Dichiarare un oggetto <xref:Microsoft.Office.Interop.Word.Range> .  
  
     L'esempio di codice seguente può essere usato in una personalizzazione a livello di documento.  
  
     [!code-vb[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomation#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#79)]  
  
     L'esempio di codice seguente può essere usato in un componente aggiuntivo VSTO. L'esempio usa il documento attivo.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#79)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#79](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#79)]  
  
2.  Usare la proprietà <xref:Microsoft.Office.Interop.Word.Find.Found%2A> in un ciclo per ricercare tutte le occorrenze della stringa nel documento e incrementare di un'unità una variabile di tipo Integer ogni volta che viene trovata la stringa.  
  
     [!code-vb[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#80)]
     [!code-csharp[Trin_VstcoreWordAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#80)]  
  
3.  Visualizza il numero di occorrenze trovate della stringa in una finestra di messaggio.  
  
     [!code-vb[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#81)]
     [!code-csharp[Trin_VstcoreWordAutomation#81](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#81)]  
  
 Gli esempi seguenti illustrano il metodo completo.  
  
## <a name="document-level-customization-example"></a>Esempio di personalizzazione a livello di documento  
  
### <a name="to-loop-through-items-in-a-document-level-customization"></a>Per scorrere in ciclo gli elementi di una personalizzazione a livello di documento  
  
1.  L'esempio seguente mostra il codice completo per una personalizzazione a livello di documento. Per usare questo codice, eseguirlo dalla classe `ThisDocument` nel progetto.  
  
     [!code-vb[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomation#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#78)]  
  
## <a name="vsto-add-in-example"></a>Esempio di componente aggiuntivo VSTO  
  
### <a name="to-loop-through-items-in-a-vsto-add-in"></a>Per riprodurre a ciclo gli elementi in un componente aggiuntivo VSTO  
  
1.  L'esempio seguente mostra il codice completo per un componente aggiuntivo VSTO. Per usare questo codice, eseguirlo dalla classe `ThisAddIn` nel progetto.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#78)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#78](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#78)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: cercare e sostituire rext nei documenti a livello di codice](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Procedura: impostare a livello di codice le opzioni di ricerca in Word](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [Procedura: definire e selezionare intervalli nei documenti a livello di codice](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Procedura: ripristino a livello di codice le selezioni dopo le ricerche](../vsto/how-to-programmatically-restore-selections-after-searches.md)   
 [Parametri facoltativi nelle soluzioni Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  