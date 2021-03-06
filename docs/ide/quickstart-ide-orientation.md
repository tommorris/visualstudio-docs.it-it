---
title: Presentazione dell'IDE di Visual Studio
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbf969e6e9a37179621cad52243418a2d0536f1a
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2018
ms.locfileid: "42627071"
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>Guida introduttiva: Presentazione dell'IDE di Visual Studio

In questa introduzione della durata di 5-10 minuti all'ambiente di sviluppo integrato (IDE) di Visual Studio verranno presentati alcuni menu, finestre e altre funzionalità dell'interfaccia utente.

Se Visual Studio non è ancora installato, accedere alla pagina [Download di Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) per installarlo gratuitamente.

## <a name="start-page"></a>Pagina iniziale

Il primo elemento visualizzato dopo l'avvio di Visual Studio è molto probabilmente la **Pagina iniziale**. La **Pagina iniziale** è progettata come "centro di smistamento" per facilitare l'accesso ai comandi e ai file di progetto necessari più velocemente. Nella sezione **Recenti** sono visualizzati i progetti e le cartelle usati di recente. In **Nuovo progetto** è possibile fare clic su un collegamento per visualizzare la finestra di dialogo **Nuovo progetto** o in **Apri** è possibile aprire un progetto o una cartella di codice esistente. Sulla destra è visualizzato un feed di notizie aggiornate per sviluppatori.

![Pagina iniziale di Visual Studio](media/start-page.png)

Se si chiude la **Pagina iniziale** e si vuole visualizzarla di nuovo, è possibile riaprirla dal menu **File**.

![Menu File di Visual Studio](media/quickstart-IDE-file-menu-large.png)

## <a name="create-a-project"></a>Creare un progetto

Per continuare a esplorare le funzionalità di Visual Studio si procederà a creare un nuovo progetto.

1. Nella casella di ricerca sotto **Nuovo progetto** della **Pagina iniziale** digitare **console** per filtrare l'elenco dei tipi di progetto includendo solo quelli che contengono "console" nel nome.

   ![Cercare nei modelli di progetto nella Pagina iniziale di Visual Studio](media/start-page-search-templates.png)

   Visual Studio mette a disposizione diversi tipi di modelli di progetto che consentono di iniziare a scrivere codice rapidamente. Selezionare un modello di progetto C# **App console (.NET Framework)**. In alternativa, gli sviluppatori che usano Visual Basic, C++, Javascript o altri linguaggi possono creare liberamente un progetto in uno di questi linguaggi. L'interfaccia utente è simile per tutti i linguaggi di programmazione.

1. Nella finestra di dialogo **Nuovo progetto** visualizzata accettare il nome di progetto predefinito e scegliere **OK**.

   Il progetto viene creato e nella finestra **Editor** si apre un file denominato *Program.cs*. L'**Editor** mostra il contenuto dei file ed è la posizione in cui si esegue la maggior parte delle operazioni di scrittura del codice in Visual Studio.

   ![Editor di Visual Studio](media/editor.png)

## <a name="solution-explorer"></a>Esplora soluzioni

**Esplora soluzioni**, generalmente sul lato destro di Visual Studio, mostra una rappresentazione grafica della gerarchia di file e cartelle nella cartella del progetto, della soluzione o del codice. È possibile esplorare la gerarchia e passare a un file in **Esplora soluzioni**.

![Esplora soluzioni di Visual Studio](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>Menu

La barra dei menu nella parte superiore di Visual Studio raggruppa i comandi in categorie. Ad esempio, il menu **Progetto** contiene i comandi correlati al progetto in uso. Dal menu **Strumenti** è possibile personalizzare Visual Studio selezionando **Opzioni** oppure aggiungere funzionalità all'installazione selezionando **Ottieni strumenti e funzionalità**.

![Barra dei menu di Visual Studio](media/quickstart-IDE-menu-bar.png)

Aprire la finestra **Elenco errori** scegliendo **Elenco errori** dal menu **Visualizza**.

## <a name="error-list"></a>Elenco errori

Nell'**Elenco errori** sono visualizzati gli errori, gli avvisi e i messaggi riguardanti lo stato corrente del codice. Se il file o il progetto in uso contiene errori, ad esempio una parentesi o un punto e virgola mancante, verranno elencati in questa posizione.

![Elenco errori in Visual Studio](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>Output (finestra)

Nella finestra **Output** vengono visualizzati i messaggi di output generati dalla compilazione del progetto e dal provider di controllo del codice sorgente.

Ora si procederà alla compilazione del progetto per esaminare alcuni elementi di output della compilazione. Scegliere **Compila soluzione** dal menu **Compila**. La finestra di **Output** ottiene automaticamente lo stato attivo e visualizza un messaggio di completamento della compilazione.

![Finestra Output di Visual Studio](media/build-output-minimal.png)

## <a name="quick-launch"></a>Avvio veloce

La casella **Avvio veloce** è un modo rapido e semplice per eseguire pressoché qualsiasi operazione in Visual Studio. È possibile immettere testo correlato all'operazione che si vuole eseguire e verrà visualizzato un elenco di opzioni pertinenti. Ad esempio, si supponga di voler aumentare il livello di dettaglio dell'output di compilazione per visualizzare più informazioni sulle operazioni eseguite esattamente dalla compilazione. Ecco come si può fare:

1. Digitare **verbosity** nella casella **Avvio veloce**. Nei risultati visualizzati scegliere **Progetti e soluzioni -> Compila ed Esegui** nella categoria **Opzioni**.

   ![Avvio veloce in Visual Studio](media/quickstart-IDE-quick-launch.png)

   Si apre la pagina delle opzioni **Compila ed esegui** della finestra di dialogo **Opzioni**.

1. In **Livello di dettaglio output in compilazione progetto MSBuild** scegliere **Normale** e quindi fare clic su **OK**.

1. Compilare di nuovo il progetto facendo clic con il pulsante destro del mouse sul progetto **ConsoleApp1** in **Esplora soluzioni** e scegliendo **Ricompila** dal menu di scelta rapida.

   Questa volta la finestra di **Output** mostra una registrazione più dettagliata del processo di compilazione, inclusi i file copiati e la posizione in cui sono stati copiati.

   ![Output di compilazione dettagliato in Visual Studio](media/build-output-verbose.png)

## <a name="send-feedback-menu"></a>Menu Invia commenti e suggerimenti

Se si verificano problemi durante l'uso di Visual Studio o se si hanno suggerimenti su come migliorare il prodotto, è possibile usare il menu **Invia commenti e suggerimenti** nella parte superiore di Visual Studio, accanto alla casella **Avvio veloce**.

![Inviare commenti e suggerimenti in Visual Studio](media/quickstart-IDE-send-feedback.png)

## <a name="next-steps"></a>Passaggi successivi

Sono state presentate solo alcune delle funzionalità di Visual Studio per iniziare ad acquisire familiarità con l'interfaccia utente. Per esplorare ulteriormente:

> [!div class="nextstepaction"]
> [Informazioni sull'editor del codice](../ide/quickstart-editor.md)

> [!div class="nextstepaction"]
> [Guida introduttiva: progetti e soluzioni](../ide/quickstart-projects-solutions.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'IDE di Visual Studio](../ide/visual-studio-ide.md)
- [Altre funzionalità di Visual Studio 2017](../ide/advanced-feature-overview.md)
- [Modificare i colori del tema e del carattere](../ide/quickstart-personalize-the-ide.md)
