---
title: Spostare un tipo in un file corrispondente - Refactoring (C#) | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 4b7b9b1ba52bed5d2bdf042db0149d799c489a7d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2018
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>Spostare un tipo in un file corrispondente in C# #

**Cosa:** consente di spostare il tipo selezionato in un file distinto con lo stesso nome.

**Quando:** sono presenti più classi, struct, interfacce e così via nello stesso file e si vuole separarli.

**Perché:** l'inserimento di più tipi nello stesso file può rendere difficile l'individuazione di questi tipi.  Con lo spostamento dei tipi in file con lo stesso nome, il codice diventa più leggibile e la navigazione più semplice.

**Come:**

1. Evidenziare o posizionare il cursore del testo all'interno del nome del tipo da spostare:

   ![Codice evidenziato](media/movetype-highlight-cs.png)

1. Eseguire quindi una delle operazioni seguenti:
   * **Tastiera**
     * Premere **CTRL+.** per attivare il menu **Azioni rapide e refactoring** e selezionare **Sposta il tipo in *NomeTipo*.cs** dal popup della finestra di anteprima, dove *NomeTipo* è il nome del tipo selezionato.
   * **Mouse**
     * Fare clic con il pulsante destro del mouse sul codice e scegliere il menu **Azioni rapide e refactoring**, quindi selezionare **Sposta il tipo in *NomeTipo*.cs** dal popup della finestra di anteprima, dove *NomeTipo* è il nome del tipo selezionato.

   Il tipo verrà immediatamente spostato in un nuovo file con tale nome all'interno della soluzione.

   ![Risultato inline](media/movetype-result-cs.png)

## <a name="see-also"></a>Vedere anche

[Refactoring](../refactoring-in-visual-studio.md)