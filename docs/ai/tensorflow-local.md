---
title: Eseguire il training di un modello TensorFlow in locale
description: Eseguire un modello TensorFlow in locale in Visual Studio Tools for AI
keywords: ai, visual studio, tensorflow, locale
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: quickstart
ms.devlang: python
ms.service: multiple
ms.technology: vs-ai-tools
ms.workload:
- multiple
ms.openlocfilehash: d8c8c5e06b5d7345a5234e4c4adb04283528f301
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379521"
---
# <a name="train-a-tensorflow-model-locally"></a>Eseguire il training di un modello TensorFlow in locale

Questa guida introduttiva descrive come eseguire il training di un modello TensorFlow con il set di dati [MNIST](http://yann.lecun.com/exdb/mnist/) in locale in Visual Studio Tools for AI.
Il database MNIST include un set di training di 60.000 esempi e un set di test di 10.000 esempi di cifre scritte a mano.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, assicurarsi di aver installato quanto segue:

### <a name="google-tensorflow"></a>Google TensorFlow

Eseguire il comando seguente in un terminale.
```cmd
C:\>pip.exe install tensorflow
```

### <a name="numpy-and-scipy"></a>NumPy e SciPy
Installare [NumPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy) e [SciPy](https://www.lfd.uci.edu/~gohlke/pythonlibs/#scipy).

### <a name="download-sample-code"></a>Scaricare il codice di esempio
Scaricare questo [repository di GitHub](https://github.com/Microsoft/samples-for-ai) contenente esempi per iniziare ad approfondire TensorFlow, CNTK, Theano e altro.

## <a name="open-solution-and-train-model"></a>Aprire la soluzione ed eseguirne il training del modello

- Avviare Visual Studio e selezionare **File > Apri > Progetto/Soluzione**.

- Selezionare la cartella **TensorflowExamples** dal repository degli esempi scaricato e aprire il file **TensorflowExamples.sln**.

![Apertura del progetto](media\tensorflow-local\open-project.png)

![Apertura della soluzione](media\tensorflow-local\open-solution.png)

- Trovare il progetto MNIST in **Esplora soluzioni**, fare clic con il pulsante destro del mouse e scegliere **Imposta come progetto di avvio**.

- Fare clic su **Avvia**.

- L'output viene stampato nella console.

![Output di esempio dalla console](media\tensorflow-local\console-output.png)

> [!div class="nextstepaction"]
> [Eseguire il training di un modello TensorFlow nel cloud](tensorflow-vm.md)