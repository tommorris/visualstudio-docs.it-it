---
title: Finestra di progettazione del flusso di lavoro - ClearCollection<T> ActivityDesigner
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2422f7165e3f00e4059bc593c129c7723daed2f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757896"
---
# <a name="clearcollectiont-activity-designer"></a>ClearCollection\<T > ActivityDesigner

Il **ClearCollection\<T >** ActivityDesigner viene utilizzato per creare e configurare un <xref:System.Activities.Statements.ClearCollection%601> attività.

## <a name="the-clearcollectiont-activity"></a>ClearCollection\<T > attività

L'attività <xref:System.Activities.Statements.ClearCollection%601> cancella tutti gli elementi di una raccolta specificata.

### <a name="using-the-clearcollectiont-activity-designer"></a>Usando ClearCollection\<T > ActivityDesigner

Il **ClearCollection\<T >** ActivityDesigner è reperibile nella **raccolta** categoria del **casella degli strumenti**, accessibile facendo clic di  **Casella degli strumenti** scheda della finestra di progettazione del flusso di lavoro. In alternativa, selezionare **della casella degli strumenti** dal **View** dal menu oppure premere **Ctrl**+**Alt** + **X**.

Il **ClearCollection\<T >** ActivityDesigner può essere trascinato dal **casella degli strumenti** e rilasciate sull'area di progettazione del flusso di lavoro ogni volta che vengono posizionate le attività, ad esempio all'interno di un' <xref:System.Activities.Statements.Sequence>. La finestra di progettazione di attività di rilascio crea un <xref:System.Activities.Statements.ClearCollection%601> attività con un valore predefinito <xref:System.Activities.Activity.DisplayName%2A> clearcollection < Int32\>. (Per impostazione predefinita, il *TypeArgument* viene **Int32**. TypeArgument può essere modificato nella griglia delle proprietà.) Il <xref:System.Activities.Activity.DisplayName%2A> possibile modificare il valore nell'intestazione del **ClearCollection < T\>**  ActivityDesigner o nel **DisplayName** finestra della griglia delle proprietà. Le altre proprietà devono essere modificate nella griglia delle proprietà.

### <a name="the-clearcollectiont-properties"></a>ClearCollection\<T > proprietà

Nella tabella seguente sono elencate le proprietà di <xref:System.Activities.Statements.ClearCollection%601> e ne viene descritta la modalità di utilizzo nella finestra di progettazione.

|Nome proprietà|Obbligatorio|Utilizzo|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Specifica il nome descrittivo facoltativo dell'attività <xref:System.Activities.Statements.ClearCollection%601>. Il valore predefinito è ClearCollection < Int32\>. Sebbene non sia obbligatorio specificare il valore di <xref:System.Activities.Activity.DisplayName%2A>, è consigliabile farlo.|
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|True|Specifica la raccolta di cui cancellare tutti gli elementi. Questa raccolta è di tipo **ICollection\<TypeArgument >.** Per specificare la raccolta, digitare un'espressione Visual Basic nella griglia delle proprietà.|
|*TypeArgument*|True|Specifica il tipo T degli elementi contenuti in <xref:System.Collections.Generic.ICollection%601>. Per impostazione predefinita, ciò *TypeArgument* è impostato su **Int32**. Per modificare il tipo, modificare il valore della *TypeArgument* nella casella combinata nella griglia delle proprietà.|

## <a name="see-also"></a>Vedere anche

- [Raccolta](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T >](../workflow-designer/addtocollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T >](../workflow-designer/removefromcollection-t-activity-designer.md)