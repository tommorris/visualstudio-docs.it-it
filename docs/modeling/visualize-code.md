---
title: Visualizzare il codice
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5db66307ef9c0099e152e46c0aac761519881cd3
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34269089"
---
# <a name="visualize-code"></a>Visualizzare il codice

È possibile usare gli strumenti di visualizzazione e modellazione di Visual Studio per comprendere più facilmente il codice esistente e descrivere l'applicazione. In questo modo è possibile avere un'indicazione visiva dell'impatto che le modifiche potrebbero avere sul codice e valutare il lavoro e i rischi risultanti da tali modifiche. Ad esempio:

- Per comprendere le relazioni nel codice, eseguire visivamente il mapping di tali relazioni.

- Per descrivere l'architettura del sistema e mantenere la coerenza con la progettazione di codice, creare diagrammi di dipendenza e convalidare il codice rispetto a questi diagrammi.

- Per descrivere le strutture delle classi, creare diagrammi classi.

Questi strumenti facilitano anche la comunicazione con le persone coinvolte nel progetto.

Per individuare le versioni di Visual Studio che supportano le singole funzionalità, vedere [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="what-do-you-want-to-do"></a>Selezionare l'operazione da eseguire.

|||
|-|-|
|**Comprendere codice e le relative relazioni:**<br /><br /> Eseguire il mapping delle relazioni tra parti di codice specifiche.<br /><br /> Ottenere una panoramica delle relazioni nel codice per l'intera soluzione.|- [Mappare le dipendenze nelle soluzioni](../modeling/map-dependencies-across-your-solutions.md)<br />- [Usare le mappe codice per il debug delle applicazioni](../modeling/use-code-maps-to-debug-your-applications.md)<br />- [Trovare problemi potenziali usando gli analizzatore delle mappe codice](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />- [Mappare i metodi sullo stack di chiamate durante il debug](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|
|**Informazioni sulle strutture di classe:**<br /><br /> Visualizzare la struttura delle classi in un progetto mediante la creazione di diagrammi classi dal codice.|[Procedura: Aggiungere diagrammi classi ai progetti (Progettazione classi)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)|
|**Viene descritta la struttura di alto livello di sistema e convalidare il codice rispetto a questa progettazione:**<br /><br /> Vengono descritti la struttura di alto livello di sistema e le relative dipendenze desiderate tramite la creazione di diagrammi di dipendenza. Convalidare il codice rispetto a tale progettazione per garantire che le dipendenze nel codice rimangano coerenti con la progettazione.|- [Creare diagrammi dipendenza dal codice](../modeling/create-layer-diagrams-from-your-code.md)<br />- [Diagrammi di dipendenza: riferimento](../modeling/layer-diagrams-reference.md)<br />- [Diagrammi di dipendenza: linee guida](../modeling/layer-diagrams-guidelines.md)<br />- [Convalidare il codice con diagrammi di dipendenza](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="see-also"></a>Vedere anche

- [Scenario: modificare la progettazione mediante gli strumenti di visualizzazione e modellazione](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)
- [Analizzare e modellare l'architettura](../modeling/analyze-and-model-your-architecture.md)
- [Modellare l'architettura dell'app](../modeling/model-your-app-s-architecture.md)
- [Usare modelli nel processo di sviluppo](../modeling/use-models-in-your-development-process.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
