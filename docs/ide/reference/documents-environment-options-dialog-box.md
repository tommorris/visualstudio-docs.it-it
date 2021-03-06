---
title: Documenti, Ambiente, finestra di dialogo Opzioni
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.Environment.Documents
- VS.ToolsOptionsPages.Environment.Documents
- VS.ToolsOptionsPag.Environment.Documents
helpviewer_keywords:
- Documents Environment Options dialog box
- defaults, directories
- error messages, customizing
- files [Visual Studio], default options
- files [Visual Basic], auto-loading modified
- windows, customizing environment
- in-memory editing
- folders [Visual Studio], specifying where Open File goes
- Open File dialog box
- windows, enabling re-use of current
- notifications, files changed
- files [Visual Studio], displaying in Solution Explorer
- default directories
- read-only files, editing
- Options dialog box, showing Miscellaneous Files
- directories [Visual Studio], IDE environment options
- Options dialog box, Documents page
- warnings, files changed
- Solution Explorer, displaying files in
ms.assetid: 4e3ccf1b-cd68-4db6-9470-710c911b47fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceccf3c051e3c85fa4b8e64ecbc33c388e9a884f
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178179"
---
# <a name="documents-environment-options-dialog-box"></a>Documenti, Ambiente, finestra di dialogo Opzioni
Usare la finestra di dialogo **Opzioni** per controllare la visualizzazione dei documenti nell'ambiente di sviluppo integrato (IDE) e gestire le modifiche esterne apportate a documenti e file. Per accedere a questa finestra di dialogo fare clic su **Opzioni** dal menu **Strumenti** e selezionare **Documenti** nel nodo **Ambiente**. Se l'opzione **Documenti** non viene visualizzata nell'elenco, selezionare **Mostra tutte le impostazioni** nella finestra di dialogo **Opzioni**.

> [!NOTE]
> Le opzioni disponibili nelle finestre di dialogo e i nomi e i percorsi dei comandi di menu visualizzati potrebbero non corrispondere a quelli descritti nella Guida a seconda dell'edizione o delle impostazioni attive. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).


 **Riutilizza la finestra del documento corrente, se salvato** Quando l'opzione viene selezionata, il documento corrente viene chiuso se è stato salvato e nella stessa finestra viene aperto un nuovo documento. Se non è stato salvato, il documento corrente rimane aperto e il nuovo documento viene aperto in una finestra separata. Quando l'opzione non viene selezionata, i nuovi documenti vengono sempre aperti in finestre separate.

 È consigliabile abilitare questa opzione se non si eseguono spesso operazioni di taglia e incolla di più documenti e si vuole ridurre il numero di documenti e finestre aperti nello spazio di lavoro.

 **Rileva quando il file viene modificato al di fuori dell'ambiente** Quando l'opzione viene selezionata, viene inviato immediatamente un messaggio per notificare che sono state apportate modifiche al file aperto da un editor all'esterno dell'IDE. Il messaggio consente di ricaricare il file dall'archiviazione.

 **Carica modifiche automaticamente, se salvate** Quando viene selezionata l'opzione **Rileva quando il file viene modificato al di fuori dell'ambiente** e un file aperto nell'IDE viene modificato all'esterno dell'IDE, per impostazione predefinita viene generato un messaggio di avviso. Se questa opzione viene abilitata, non vengono visualizzati avvisi e il documento viene ricaricato nell'IDE per acquisire le modifiche esterne.

 **Consenti modifica dei file di sola lettura, avvisa al tentativo di salvataggio** Quando questa opzione è abilitata è possibile aprire e modificare un file di sola lettura. Al termine dell'operazione, usare il comando **Salva con nome** per salvare il file con un nuovo nome se si vuole salvare un record delle modifiche.

 **Apri file utilizzando la directory del documento attivo** Quando l'opzione viene selezionata, nella finestra di dialogo **Apri file** viene visualizzata la directory del documento attivo. Quando l'opzione viene deselezionata, nella finestra di dialogo **Apri file** viene visualizzata la directory usata l'ultima volta per aprire un file.

 **Verifica coerenza terminazioni riga al caricamento** Selezionare questa opzione in modo che l'editor analizzi le terminazioni di riga in un file e visualizzi una finestra di messaggio se vengono rilevate incoerenze nella formattazione delle terminazioni.

 **Visualizza avviso se l'annullamento globale avrà effetto sui file modificati** Selezionare questa opzione per visualizzare una finestra di messaggio quando il comando **Annullamento globale** esegue il rollback delle modifiche di refactoring apportate ai file che sono stati modificati dopo l'operazione di refactoring. Il ripristino dello stato pre-refactoring di un file può comportare l'annullamento delle modifiche successive apportate al file.

 **Mostra file esterni in Esplora soluzioni** Selezionare questa opzione per visualizzare il nodo **File esterni** in **Esplora soluzioni**. I file esterni sono file non associati a un progetto o a una soluzione, che possono tuttavia essere visualizzati in **Esplora soluzioni** per comodità.

> [!NOTE]
> Selezionare questa opzione per abilitare il comando **Visualizza nel browser** nel menu **File** per i documenti Web non inclusi nell'applicazione Web attiva.

 **\<** *n* **> elementi salvati nel progetto di file esterni** Specifica il numero di file da salvare in modo permanente nella cartella **File esterni** di **Esplora soluzioni**. Questi file vengono elencati anche se non sono più aperti in un editor. È possibile specificare un numero intero qualsiasi compreso tra 0 e 256. Il numero predefinito è 0.

 Ad esempio, se si imposta questa opzione su 5 e i file esterni aperti sono 10, quando si chiudono tutti i 10 file, i primi 5 verranno ancora visualizzati nella cartella **File esterni**.

 **Salva documenti come Unicode quando i dati non possono essere salvati nella tabella codici** Se si seleziona questa opzione, i file contenenti informazioni non compatibili con la tabella codici selezionata saranno salvati in formato Unicode per impostazione predefinita.

## <a name="see-also"></a>Vedere anche

- [Finestra di dialogo Opzioni ambiente](../../ide/reference/environment-options-dialog-box.md)
- [File esterni](../../ide/reference/miscellaneous-files.md)
- [Ricerca e sostituzione di testo](../../ide/finding-and-replacing-text.md)