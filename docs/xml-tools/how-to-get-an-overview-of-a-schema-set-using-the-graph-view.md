---
title: 'Procedura: ottenere una panoramica di un Set di schemi tramite la visualizzazione grafico in XML Schema della finestra di progettazione'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c0df4b0d-52ef-4a6c-9676-1d8311aad7c7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 004d40992e24f0df651d93b43761add1d2efa673
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2018
ms.locfileid: "39381420"
---
# <a name="how-to-get-an-overview-of-a-schema-set-using-the-graph-view"></a>Procedura: ottenere una panoramica di uno schema impostato tramite la visualizzazione grafico

In questo argomento viene descritto come utilizzare il [visualizzazione grafico](../xml-tools/graph-view.md) per ottenere una visualizzazione di alto livello dei nodi in un set di schemi e le relazioni tra i nodi.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>Per creare un nuovo file XSD e visualizzare l'elemento radice nella visualizzazione modello di contenuto

1.  Creare un nuovo file di XML Schema e salvare il file come *Relationships*.

2.  Scegliere il **usare l'Editor XML per visualizzare e modificare il file di XML Schema sottostante** collegamento nella visualizzazione iniziale.

3.  Copiare il codice di esempio di XML Schema da [dello schema XML di esempio: relazioni](../xml-tools/sample-xsd-file-relationships.md) e incollarlo per sostituire il codice che è stato aggiunto il nuovo file XSD per impostazione predefinita.

4.  Fare doppio clic in un punto qualsiasi dell'Editor XML e selezionare **Progettazione viste**.

5.  Selezionare la visualizzazione grafico dal **sulla barra degli strumenti XSD**.

6.  Selezionare **del Set di schemi** nodo il **XML Schema Explorer** e trascinare il nodo nell'area di progettazione della visualizzazione grafico. Dovrebbero essere visualizzati i nodi globali e le frecce che collegano i nodi tra cui intercorrono relazioni.

     ![Visualizzazione grafico](../xml-tools/media/relationshipingraphview.gif)

7.  Fare clic su qualsiasi nodo nell'area di progettazione e analizzare la barra di navigazione per vedere dove si trova il nodo selezionato nel set di schemi.

8.  Rick, fare clic su qualsiasi nodo dell'elemento nell'area di progettazione e seleziona **genera XML di esempio** per visualizzare il documento di istanza XML.