---
title: "Procedura: usare il Visualizzatore dell'albero WPF | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a478eae1e576ba2556d48f6527f6c9e2dab4ef6
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902163"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Procedura: Usare il visualizzatore dell'albero di WPF
È possibile utilizzare il visualizzatore dell'albero di WPF per esplorare la struttura ad albero visuale di un oggetto WPF e visualizzare le proprietà di dipendenza WPF per gli oggetti contenuti in tale albero. Per altre informazioni sulle strutture ad albero visuali, vedere [strutture ad albero in WPF](/dotnet/framework/wpf/advanced/trees-in-wpf). Per altre informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](/dotnet/framework/wpf/advanced/dependency-properties-overview).  
  
 Quando si apre il Visualizzatore dell'albero di WPF, si vedranno due riquadri: il **struttura ad albero visuale** a sinistra e il **delle proprietà della** _nome_**:**  _Tipo_ riquadro a destra. Selezionare un oggetto qualsiasi nel **struttura ad albero visuale** riquadro e il **delle proprietà di** _nome_**:**_tipo_ riquadro è aggiornati automaticamente per mostrare le proprietà di quell'oggetto.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>Per aprire il visualizzatore dell'albero di WPF  
  
1.  In un suggerimento dati, **Watch** finestra **Auto** finestra, oppure **variabili locali** finestra accanto al nome di un oggetto WPF, fare clic sulla freccia accanto all'icona della lente di ingrandimento.  
  
     Verrà visualizzato un elenco di visualizzatori.  
  
2.  Fare clic su **Visualizzatore dell'albero di WPF**.  
  
### <a name="to-search-the-visual-tree"></a>Per eseguire ricerche nella struttura ad albero visuale  
  
-   Nel **struttura ad albero visuale** riquadro, digitare la stringa da cercare nel **ricerca** casella.  
  
     Il visualizzatore dell'albero di WPF troverà immediatamente il primo oggetto nella struttura ad albero visuale che corrisponde alla stringa digitata. Digitare più caratteri per trovare una corrispondenza più accurata.  
  
    -   Per passare alla corrispondenza successiva all'interno di struttura ad albero visuale, fare clic su **successivo**.  
  
    -   Per tornare alla corrispondenza precedente, fare clic su **Prev**.  
  
    -   Per cancellare i criteri di ricerca, fare clic su **cancellare**.  
  
### <a name="to-search-the-properties-list"></a>Per eseguire ricerche nell'elenco di proprietà  
  
-   Nel **delle proprietà di** _nome_**:**_tipo_ riquadro, digitare la stringa da cercare nel **filtrare**finestra.  
  
     Il visualizzatore dell'albero di WPF troverà immediatamente le proprietà che corrispondono alla stringa digitata; nell'elenco sono visualizzate soltanto le proprietà corrispondenti alla stringa digitata. Digitare più caratteri per trovare una corrispondenza più accurata.  
  
    -   Per cancellare i criteri di ricerca, fare clic su **cancellare**.  
  
### <a name="to-close-the-visualizer"></a>Per chiudere il visualizzatore  
  
-   Scegliere il **Chiudi** icona nell'angolo superiore destro della finestra di dialogo.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di visualizzatori personalizzati](../debugger/create-custom-visualizers-of-data.md)   
 [Strutture ad albero in WPF](/dotnet/framework/wpf/advanced/trees-in-wpf)   
 [Panoramica sulle proprietà di dipendenza](/dotnet/framework/wpf/advanced/dependency-properties-overview)
