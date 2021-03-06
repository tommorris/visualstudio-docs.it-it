---
title: Installare Dotfuscator Community Edition (CE)
ms.date: 06/22/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, protezione, edizione community, offuscamento, .NET, gratuito, Visual Studio 2017, installare
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator installer
- Dotfuscator setup
- install Dotfuscator
- installing Dotfuscator
- set up Dotfuscator
description: Informazioni su come installare la versione gratuita di Dotfuscator Community Edition inclusa in Visual Studio 2017.
ms.assetid: f2146651-e24a-4e24-ade8-8ddee8ff4e43
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: 13027c5d4fe4fc799f6514eb93bfc4ed93141613
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283220"
---
# <a name="install-dotfuscator-community-edition-ce"></a>Installare Dotfuscator Community Edition (CE)

Visual Studio 2017 introduce una nuova esperienza di installazione di basso impatto.
Di conseguenza, Dotfuscator Community Edition (Dotfuscator CE) non è installato automaticamente per impostazione predefinita.
È tuttavia facile installare Dotfuscator CE, anche se è già stato installato Visual Studio.

> [!NOTE]
> Oltre alle versioni di Dotfuscator CE incluse nelle versioni di Visual Studio, PreEmptive Solutions offre periodicamente anche versioni aggiornate sul proprio sito Web.
> Se si vuole scaricare la **versione più recente** direttamente anziché eseguire l'installazione da Visual Studio,  **[fare clic qui per passare alla pagina di download di Dotfuscator][download]**.

## <a name="within-visual-studio"></a>Da Visual Studio

È possibile installare Dotfuscator CE dall'IDE di Visual Studio:

1. Nella barra di ricerca dell'**Avvio veloce** (CTRL + Q) digitare `dotfuscator`. <br/> <br/> ![Avvio veloce](media/install_from_vs_12.png) <br/> <br/>
2. Nei risultati visualizzati nell'Avvio veloce, sotto l'intestazione *Installa*, selezionare **PreEmptive Protection - Dotfuscator (Individual Component)**.
  * Se invece sotto l'intestazione *Menu* viene visualizzato **Strumenti - PreEmptive Protection - Dotfuscator** vuol dire che Dotfuscator CE è già installato. Per informazioni dettagliate sull'uso, vedere la [pagina introduttiva della Guida dell'utente completa di Dotfuscator CE][get-started].
3. Viene visualizzata la finestra del programma di installazione di Visual Studio, preconfigurato per installare Dotfuscator CE.
  * Potrebbe essere necessario specificare credenziali di amministratore per continuare.
4. Chiudere tutte le istanze dell'IDE di Visual Studio. <br/> <br/> ![Fare clic su Installa](media/install_from_vs_345.png) <br/> <br/>
5. Fare clic su *Installa* nella finestra del programma di installazione di Visual Studio.

Al termine dell'installazione, è possibile iniziare a usare Dotfuscator CE. Per informazioni dettagliate, vedere la [pagina introduttiva della Guida dell'utente completa di Dotfuscator CE][get-started].

## <a name="during-visual-studio-installation"></a>Durante l'installazione di Visual Studio

Se non è ancora stato installato Visual Studio 2017, è possibile ottenere il programma di installazione dal [sito Web di Visual Studio][2017-install].
Durante l'esecuzione, verranno visualizzate le opzioni di installazione per l'edizione di Visual Studio selezionata.

![Opzioni di installazione](media/install_ui.png)

È possibile quindi installare Dotfuscator CE come componente singolo di Visual Studio 2017:

1. Selezionare la scheda **Singoli componenti**.
2. In *Strumenti per il codice*, verificare l'elemento *PreEmptive Protection - Dotfuscator*.<br/> <br/> ![Singoli componenti](media/install_individually_12.png) <br/> <br/>
3. Il pannello *Riepilogo* visualizza *PreEmptive Protection - Dotfuscator* sotto la sezione *Singoli componenti*. <br/> <br/> ![Riquadro Riepilogo](media/install_individually_3.png) <br/> <br/>
4. Configurare le altre impostazioni di installazione come appropriato per l'ambiente.
5. Quando si è pronti per installare Visual Studio, fare clic sul pulsante *Installa*.

Al termine dell'installazione, è possibile iniziare a usare Dotfuscator CE. Per informazioni dettagliate, vedere la [pagina introduttiva della Guida dell'utente completa di Dotfuscator CE][get-started].

## <a name="see-also"></a>Vedere anche

[This topic in the full Dotfuscator CE User Guide]: https://www.preemptive.com/dotfuscator/ce/docs/help/

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[2017-install]:  https://visualstudio.microsoft.com/downloads/#vs-2017
[get-started]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[download]:  https://www.preemptive.com/products/dotfuscator/downloads

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_install.html