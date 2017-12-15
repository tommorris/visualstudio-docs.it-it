---
title: Working with Python in Visual Studio, Step 1 (Uso di Python in Visual Studio, Passaggio 1) | Microsoft Docs
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: d6c5cd4395ea0251027edbc94019637b72a630a8
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2017
---
# <a name="working-with-python-in-visual-studio"></a>Uso di Python in Visual Studio

Python è un linguaggio di programmazione molto diffuso affidabile, flessibile, facile da imparare, il cui uso è gratuito in tutti i sistemi operativi e supportato sia da un'attiva community di sviluppatori che da numerose librerie gratuite. Il linguaggio supporta tutte le modalità di sviluppo, tra cui applicazioni Web, servizi Web, app desktop, script e calcolo scientifico. Viene usato in molte università, nonché da scienziati, sviluppatori professionisti e non professionisti.

Visual Studio offre un supporto dei linguaggi di prima classe per Python. Completare le fasi dell'esercitazione indicate di seguito:

- [Passaggio 0: Installazione](vs-tutorial-01-00.md)
- [Passaggio 1: Creazione di un progetto di Python (questo argomento)](#step-1-create-a-new-python-project)
- [Passaggio 2: Scrittura ed esecuzione di codice per visualizzare Visual Studio IntelliSense al lavoro](vs-tutorial-01-02.md)
- [Passaggio 3: Creare altro codice nella finestra interattiva REPL](vs-tutorial-01-03.md)
- [Passaggio4: Eseguire un programma nel debugger di Visual Studio.](vs-tutorial-01-04.md)
- [Passaggio 5: Installazione di pacchetti e gestione di ambienti Python](vs-tutorial-01-05.md)
- [Passaggio 6: Uso di Git](vs-tutorial-01-06.md)

## <a name="prerequisites"></a>Prerequisiti

- Visual Studio 2017 con carico di lavoro di Python installato. Per le istruzioni, vedere il [passaggio 0](vs-tutorial-01-00.md).

## <a name="step-1-create-a-new-python-project"></a>Passaggio 1: Creare un nuovo progetto Python

Per *progetto* si intende la modalità con cui Visual Studio gestisce tutti i file inclusi nella creazione di una singola applicazione, come codice sorgente, risorse, configurazioni e così via. Un progetto formalizza e gestisce la relazione tra i file del progetto, nonché le risorse esterne che vengono condivise tra più progetti. Di conseguenza, il progetto consente all'applicazione di espandersi e crescere facilmente rispetto alla semplice gestione delle relazioni di un progetto in cartelle ad hoc, script, file di testo e a livello di idee.

In questa esercitazione si inizia con un semplice progetto che contiene un singolo file di codice vuoto.

1. In Visual Studio selezionare **File > Nuovo progetto** (Ctrl+Shift+N) che visualizza la finestra di dialogo **Nuovo progetto**. Qui è possibile esplorare i modelli tra i diversi linguaggi, quindi selezionarne uno per il progetto e specificare dove inserire i file Visual Studio.

1. Per visualizzare i progetti Visual Studio, selezionare **Modelli > Altri linguaggi > Python** a sinistra oppure cercare "Python". La ricerca è un ottimo modo per trovare un modello quando non si ricorda la posizione nell'albero dei linguaggi.

    ![Finestra di dialogo Nuovo progetto con visualizzati i progetti Python](media/vs-getting-started-python-01-new-project.png)

1. Il supporto per Python in Visual Studio include vari modelli di progetto, incluse applicazioni Web che usano i framework Bottle, Flask e Django insieme a Servizi cloud di Azure. Per gli scopi di questa procedura dettagliata, tuttavia, si inizierà con un progetto vuoto. 

1. Selezionare il modello **Applicazione Python**, specificare un nome per il progetto e selezionare **OK**. 

1. Dopo qualche secondo, Visual Studio visualizza la struttura del progetto nella finestra **Esplora soluzioni** (1). Il file di codice predefinito è aperto nell'editor (2). La finestra relativa alle proprietà (3) offre anche la possibilità di visualizzare informazioni aggiuntive per qualsiasi elemento selezionato in Esplora soluzioni, tra cui la posizione esatta su disco.
 
    ![Esplora soluzioni con un progetto Python](media/vs-getting-started-python-02-windows.png)
 
1. Prendersi alcuni minuti per acquisire familiarità con Esplora soluzioni, il luogo in cui cercare file e cartelle nel progetto.
    
    ![L'espansione di Esplora soluzioni consente di visualizzare le varie funzionalità](media/vs-getting-started-python-03-solution-explorer.png)

    (1) In grassetto viene visualizzato il progetto con il nome assegnato in precedenza nella finestra di dialogo Nuovo progetto. Sul disco questo progetto è rappresentato da un file `.pyproj` nella cartella del progetto.

    (2) Al primo livello è presente una *soluzione* che, per impostazione predefinita, ha lo stesso nome del progetto. Una soluzione, rappresentata da un file `.sln` su disco, è un contenitore per uno o più progetti correlati. Ad esempio, se si scrive un'estensione C++ per l'applicazione Python, il progetto C++ può risiedere nella stessa soluzione. La soluzione può contenere anche un progetto per un servizio web, insieme ai progetti per i programmi di test dedicati. 

    (3) Nel progetto si possono vedere i file di origine, in questo caso un solo file `.py`. La selezione di un file consente di visualizzare le proprietà nella Finestra Proprietà. Facendo doppio clic su un file, questo verrà aperto nel modo più appropriato.

    (4) Il nodo **Ambienti Python** è visualizzabile anche dal progetto. Attraverso l'espansione è possibile visualizzare gli interpreti Python disponibili. Espandere un nodo dell'interprete per visualizzare le librerie installate in tale ambiente (5).

    Fare doppio clic su qualsiasi nodo o elemento in Esplora soluzioni per accedere a un menu di comandi validi. Ad esempio, il comando **Rinomina** consente di modificare il nome di un nodo o di un elemento, inclusi il progetto e la soluzione.
    
## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Scrittura ed esecuzione del codice](vs-tutorial-01-02.md)

## <a name="going-deeper"></a>Approfondimenti

- [Python Projects in Visual Studio (Progetti Python in Visual Studio)](python-projects.md)
- [Informazioni sul linguaggio Python in python.org](https://www.python.org)
- [Python per utenti meno esperti](https://www.python.org/about/gettingstarted/) (python.org)
- [Corsi gratuiti per Python in Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Top Python Questions (Domande principali su Python) alla Microsoft Virtual Academy](https://aka.ms/mva-top-python-questions)