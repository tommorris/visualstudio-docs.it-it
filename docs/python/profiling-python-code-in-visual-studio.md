---
title: Misurazione delle prestazioni del codice Python
description: Come usare il profiler di Visual Studio per controllare le prestazioni del codice Python quando si usano interpreti basati su CPython.
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
ms.openlocfilehash: feafc7d53e8d450bc980b6d842e9c2a5f0ade2e4
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468816"
---
# <a name="profile-python-code"></a>Profilare il codice Python

È possibile eseguire la profilatura di un'applicazione Python quando si usano interpreti basati su CPython. (Vedere [Matrice delle funzionalità - Profilatura](overview-of-python-tools-for-visual-studio.md#matrix-profiling) per informazioni sulla disponibilità di questa funzionalità per le diverse versioni di Visual Studio.)

## <a name="profiling-for-cpython-based-interpreters"></a>Profilatura per interpreti basati su CPython

Per avviare la profilatura, si usa il comando di menu **Analizza** > **Avvia profilatura Python**, che consente di aprire una finestra di dialogo di configurazione:

![Finestra di dialogo di configurazione della profilatura](media/profiling-start.png)

Quando si fa clic su **OK**, viene eseguito il profiler e si apre un report di prestazioni che illustra in che modo viene impiegato il tempo nell'applicazione:

![Report di prestazioni del profiler](media/profiling-results.png)

|   |   |
|---|---|
| ![icona della telecamera](../install/media/video-icon.png "Guardare un video") | [Guardare un video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567) per una dimostrazione della profilatura di Python (3m 00s).|

> [!Note]
> Al momento, Visual Studio supporta solo questo livello di profilatura dell'applicazione completa, ma Microsoft sarà certamente lieta di ricevere commenti e suggerimenti sulle funzionalità future. Usare il [pulsante **Invia commenti sul prodotto**](#feedback) nella parte inferiore della pagina.

## <a name="profiling-for-ironpython"></a>Profilatura per IronPython

Dal momento che IronPython non è un interprete basato su CPython, la funzionalità di profilatura illustrata sopra non funziona.

Usare invece il profiler di Visual Studio .NET avviando direttamente *ipy.exe* come applicazione di destinazione e usando gli argomenti appropriati per eseguire lo script di avvio. Includere `-X:Debug` nella riga di comando per assicurarsi che sia possibile eseguire il debug e la profilatura per tutto il codice Python. Questo argomento genera un report di prestazioni che include il tempo impiegato sia nel runtime di IronPython che nel codice. Per identificare il codice, vengono usati nomi modificati.

In alternativa, IronPython presenta alcune funzionalità di profilatura incorporate, per le quali però non esiste ancora alcun visualizzatore adeguato. Per informazioni sulle opzioni disponibili, vedere [An IronPython Profiler](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (Profiler per IronPython) nei blog di MSDN.