---
title: Common Language Runtime e valutazione delle espressioni | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, and common language runtime
ms.assetid: b36c1eb5-1aaf-48a6-b287-ee7a273d2b1c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7db25e563e2728d30ade9f4c7f2dc6faf659721b
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204375"
---
# <a name="common-language-runtime-and-expression-evaluation"></a>Valutazione di Common language runtime ed espressione
> [!IMPORTANT]
>  In Visual Studio 2015, questa modalità di implementazione analizzatori di espressioni è deprecata. Per informazioni sull'implementazione di analizzatori di espressioni di Common Language Runtime, vedi [analizzatori di espressioni CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) e [esempio analizzatore di espressioni gestite](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Compilatori, ad esempio Visual Basic e c# (pronunciato C-sharp), destinate a Common Language Runtime (CLR), produrre linguaggio MSIL (Microsoft Intermediate), ovvero successive compilate in codice nativo. CLR fornisce un motore di debug (DE) per il debug del codice risulta. Se si prevede di integrare il linguaggio di programmazione proprietario nell'IDE di Visual Studio, è possibile scegliere di compilare in codice MSIL e pertanto non sarà necessario scrivere il proprio DE. Tuttavia, è necessario scrivere un analizzatore di espressioni (EE) che è in grado di valutazione di espressioni all'interno del contesto del linguaggio di programmazione.  
  
## <a name="discussion"></a>Discussione  
 Le espressioni del linguaggio computer vengono in genere analizzate per produrre un set di oggetti dati e un set di operatori usato per la manipolazione. L'espressione "A + B" può essere analizzata per applicare l'operatore di addizione (+) per i dati degli oggetti, ad esempio, "A" e "B", determinando in un altro oggetto dati. Set totale di oggetti dati, operatori e le relative associazioni sono spesso rappresentati in un programma come un albero, con gli operatori ai nodi dell'albero e gli oggetti dati nelle filiali. Un'espressione che è stato suddiviso in forma di struttura ad albero viene spesso definita una struttura ad albero analizzato.  
  
 Una volta che un'espressione è stata analizzata, viene chiamato un provider di simboli (SP) per valutare ogni oggetto dati. Se, ad esempio, "A" è definito in più di un metodo, la domanda "Quale A?" deve essere una risposta prima che è possibile ottenere il valore dell'oggetto. La risposta restituita dalla stored procedure è simile a "Il terzo elemento sullo stack frame quinto" o "A 50 byte oltre l'inizio della memoria statica allocato a questo metodo".  
  
 Oltre a produrre codice MSIL per il programma stesso, i compilatori CLR possono inoltre generare informazioni di debug molto descrittive che viene scritto in un DataBase di programma (*PDB*) file. Fino a quando un compilatore di linguaggio di tua proprietà produce informazioni di debug nello stesso formato i compilatori CLR, SP di CLR è in grado di identificare che del linguaggio denominato oggetti dati. Dopo aver individuato un oggetto dati con nome, l'analizzatore di Espressioni Usa un oggetto strumento di associazione per associare l'oggetto dati (o associare) nell'area di memoria che contiene il valore di tale oggetto. Il DE possa quindi ottenere o impostare un nuovo valore per l'oggetto dati.  
  
 Un compilatore proprietario può fornire informazioni di debug tramite la chiamata di CLR i `ISymbolWriter` interface (definito in .NET Framework nello spazio dei nomi `System.Diagnostics.SymbolStore`). La compilazione in codice MSIL e scrivendo le informazioni di debug tramite queste interfacce, è possibile usare un compilatore proprietario il CLR Germania e provider di servizi. Questo semplifica notevolmente l'integrazione di un linguaggio proprietario nell'IDE di Visual Studio.  
  
 Quando la Germania CLR chiama l'analizzatore di Espressioni proprietarie per valutare un'espressione, la Germania fornisce l'analizzatore di Espressioni con le interfacce per un Service Pack e un oggetto strumento di associazione. Di conseguenza, la scrittura di un mezzo del motore di debug basata su CLR è necessario solo implementare le interfacce dell'analizzatore di espressione appropriata. Common Language Runtime si occupa dell'associazione e il simbolo di gestione per l'utente.  
  
## <a name="see-also"></a>Vedere anche  
 [Scrivere un analizzatore di espressioni CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)