---
title: "Procedura: memorizzare nella cache a livello di codice di un'origine dati in un documento di Office"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 89aef81c68b95947215142ddadf9081d49aa95b2
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256705"
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>Procedura: memorizzare nella cache a livello di codice di un'origine dati in un documento di Office
  È possibile aggiungere un oggetto dati a livello di codice alla cache dei dati in un documento chiamando il `StartCaching` metodo di un host di elemento, ad esempio un <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, o <xref:Microsoft.Office.Tools.Excel.Worksheet>. Rimuovere un oggetto dati dalla cache dei dati chiamando il `StopCaching` metodo di un elemento host.  
  
 Il `StartCaching` metodo e il `StopCaching` metodo sono entrambi privato, ma vengono visualizzati in IntelliSense.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Quando si usa la `StartCaching` metodo per aggiungere un oggetto dati per la cache dei dati, l'oggetto dati non deve essere dichiarato con la <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> attributo. Tuttavia, l'oggetto dati deve soddisfare determinati requisiti da aggiungere alla cache dei dati. Per altre informazioni, vedere [memorizzare nella Cache dati](../vsto/caching-data.md).  
  
## <a name="to-programmatically-cache-a-data-object"></a>Memorizzare nella cache a livello di codice di un oggetto dati  
  
1.  Dichiarare l'oggetto dati a livello di classe, non all'interno di un metodo. Questo esempio si presuppone che si sta dichiarando una <xref:System.Data.DataSet> denominato `dataSet1` che si desidera memorizzare nella cache a livello di codice.  
  
     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]  
  
2.  Creare un'istanza dell'oggetto dati e quindi chiamare il `StartCaching` metodo di istanza di documento o foglio di lavoro e passare il nome dell'oggetto dati.  
  
     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]  
  
## <a name="to-stop-caching-a-data-object"></a>Per arrestare la memorizzazione nella cache un oggetto dati  
  
1.  Chiamare il `StopCaching` metodo di istanza di documento o foglio di lavoro e passare il nome dell'oggetto dati. Questo esempio si presuppone di avere una <xref:System.Data.DataSet> denominato `dataSet1` che si desidera arrestare la memorizzazione nella cache.  
  
     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]  
  
    > [!NOTE]  
    >  Non chiamare `StopCaching` dal gestore dell'evento per il `Shutdown` eventi di un documento o foglio di lavoro. Entro l'ora di `Shutdown` viene generato l'evento, è troppo tardi per modificare la cache dei dati. Per altre informazioni sul `Shutdown` eventi, vedere [Events in Office Projects](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Dati della cache](../vsto/caching-data.md)   
 [Procedura: memorizzare nella Cache i dati per l'uso offline o in un server](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Procedura: memorizzare nella Cache i dati in un documento protetto da password](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [Accedere ai dati in documenti sul server](../vsto/accessing-data-in-documents-on-the-server.md)   
 [Salvare i dati](/visualstudio/data-tools/saving-data)  
  
  