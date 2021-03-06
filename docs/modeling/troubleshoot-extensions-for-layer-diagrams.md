---
title: Risolvere i problemi relativi a estensioni per diagrammi di dipendenza
ms.date: 11/04/2016
ms.topic: troubleshooting
helpviewer_keywords:
- dependency diagrams, extension errors
- dependency diagrams, troubleshooting extensions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: b56ccd587df4a830eab5bee000cafcc02b0031e8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31949371"
---
# <a name="troubleshoot-extensions-for-dependency-diagrams"></a>Risolvere i problemi relativi a estensioni per diagrammi di dipendenza

Questo argomento risolve alcuni problemi che possono verificarsi quando si creano estensioni del modello di livello.

## <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-dependency-diagrams-in-the-experimental-instance-of-includevsprvscode-qualityincludesvsprvsmdmd"></a>È possibile premere F5 per eseguire il debug estensione my, my comandi, i gestori di movimento, estensioni di convalida o le proprietà personalizzate non vengono visualizzati nei diagrammi di dipendenza nell'istanza sperimentale di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]

1.  Aprire la soluzione di estensione nell'istanza sperimentale di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]e scegliere il **compilare** menu, fare clic su **Ricompila soluzione**.

2.  Premere **F5** o **CTRL + F5** per avviare l'istanza sperimentale di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Aprire un diagramma di dipendenze e testare l'estensione.

 Continuare con la procedura descritta di seguito, se necessario.

## <a name="an-old-version-of-my-extension-runs"></a>Viene seguita una versione precedente dell'estensione.

1.  Assicurarsi che non sia in esecuzione un'istanza sperimentale di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

2.  Eliminare la cartella seguente: %LocalAppData%\Microsoft\VisualStudio\\\ComponentModelCache [versione]

    > [!NOTE]
    > % LocalAppData % è in genere *DriveName*: \Users\\*UserName*\AppData\Local.

 Continuare con la procedura descritta di seguito, se necessario.

## <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>Viene visualizzata una versione precedente dei risultati di convalida o il metodo di convalida non viene chiamato.

1.  Nell'istanza sperimentale di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]via di **compilare** menu, fare clic su **Pulisci soluzione**. In questo modo vengono cancellati i risultati delle precedenti analisi di convalida memorizzati nella cache.

2.  Assicurarsi che i livelli nel modello siano associati a elementi di codice e che nel modello sia presente almeno un collegamento di dipendenza. La convalida non viene richiamata se non sono presenti elementi da convalidare.

3.  I punti di interruzione normali potrebbero non funzionare in un metodo di convalida, perché è in esecuzione in un processo distinto. È necessario inserire una chiamata a `System.Diagnostics.Debugger.Launch()` se si vuole eseguire il metodo un'istruzione alla volta.

4.  In **vsixmanifest** nel progetto di convalida livello, assicurarsi di aver aggiunto sia un **componente MEF** elemento e un **tipo di estensione personalizzato** elemento sotto **Contenuto**.

## <a name="see-also"></a>Vedere anche

- [Estendere i diagrammi delle dipendenze](../modeling/extend-layer-diagrams.md)
