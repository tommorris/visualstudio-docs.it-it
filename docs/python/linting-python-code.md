---
title: Uso di PyLint per analizzare il codice Python
description: Come usare PyLint in Visual Studio per controllare i problemi nel codice Python.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fa037a9e674e6086fd3d558d621f9a7d7be616aa
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468741"
---
# <a name="use-pylint-to-check-python-code"></a>Usare PyLint per controllare il codice Python

[PyLint](https://www.pylint.org/), uno strumento molto diffuso che verifica la presenza di errori nel codice Python e promuove buone prassi di scrittura del codice per Python, è integrato in Visual Studio per i progetti Python.

## <a name="run-pylint"></a>Eseguire PyLint

È sufficiente fare clic con il pulsante destro del mouse su un progetto Python in **Esplora soluzioni** e scegliere **Python** > **Esegui PyLint**:

![Comando PyLint nel menu di scelta rapida per i progetti Python](media/code-pylint-command.png)

Se si usa questo comando, viene richiesto di installare PyLint nell'ambiente attivo, se non è già presente.

Gli avvisi e gli errori di PyLint vengono visualizzati nella finestra **Elenco errori**:

![Elenco errori di PyLint](media/code-pylint-error-list.png)

È possibile fare doppio clic su un errore per passare direttamente al codice sorgente che ha generato il problema.

> [!Tip]
> Vedere le [informazioni di riferimento sulle funzionalità di PyLint](https://pylint.readthedocs.io/en/latest/technical_reference/features.html) per un elenco dettagliato di tutti i messaggi di output di PyLint.

## <a name="set-pylint-command-line-options"></a>Impostare le opzioni della riga di comando di PyLint

La sezione dedicata alle [opzioni della riga di comando](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options) della documentazione PyLint illustra come controllare il comportamento di PyLint tramite un file di configurazione con estensione *pylintrc*. Questo file può essere inserito nella radice di un progetto Python in Visual Studio o in altre posizioni, a seconda di quanto si vuole estendere l'applicazione delle impostazioni. Per altri dettagli, vedere le [opzioni della riga di comando](https://pylint.readthedocs.io/en/latest/user_guide/run.html#command-line-options).

Ad esempio, per eliminare gli avvisi relativi a "DocString mancante" illustrati nella figura precedente con un file con estensione *pylintrc* in un progetto, seguire questa procedura:

1. Nella riga di comando passare alla radice del progetto, che contiene il file con estensione *pyproj*, ed eseguire il comando seguente per generare un file di configurazione commentato:

   ```command
   pylint --generate-rcfile > .pylintrc
   ```

1. In Esplora soluzioni di Visual Studio fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi** > **Elemento esistente**, passare al nuovo file con estensione *pylintrc*, selezionarlo e quindi scegliere **Aggiungi**.

1. Aprire il file per la modifica, che include diverse opzioni disponibili per l'uso. Per disabilitare un avviso, individuare la sezione `[MESSAGES CONTROL]` e quindi l'impostazione `disable` in tale sezione. È presente una lunga stringa di messaggi specifici, a cui è possibile aggiungere qualsiasi avviso. In questo esempio, aggiungere `,missing-docstring` (inclusa la virgola di delimitazione).

1. Salvare il file con estensione *pylintrc* ed eseguire di nuovo PyLint per verificare che gli avvisi siano soppressi.

> [!Tip]
> Per usare un file con estensione *pylintrc* da una condivisione di rete, creare una variabile di ambiente denominata `PYLINTRC` con il valore del nome file nella condivisione di rete con un percorso UNC o una lettera di unità mappata. Ad esempio `PYLINTRC=\\myshare\python\.pylintrc`.
