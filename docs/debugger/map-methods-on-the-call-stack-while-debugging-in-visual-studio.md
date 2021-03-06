---
title: Creare una mappa visiva dello stack di chiamate | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6156be294c9b64c26a7488aef3f0c92d1f4ccffd
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296061"
---
# <a name="create-a-visual-map-of-the-call-stack-while-debugging-in-visual-studio-enterprise"></a>Creare una mappa visiva dello stack di chiamate durante il debug in Visual Studio Enterprise
Creare una mappa codici per tracciare visivamente lo stack di chiamate durante il debug. È possibile inserire note sulla mappa per tenere traccia dell'attività del codice e in tal modo concentrarsi sull'individuazione di bug.

 Sono necessari:

-   [Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

-   Codice che è possibile eseguire il debug, ad esempio Visual c#, Visual Basic, C++, JavaScript o X + +

Ecco un rapido controllo di una mappa del codice:

 ![Debug con stack di chiamate in mappe codici](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")

 Vedere:

-   [Video: Debug visivo con integrazione del debugger della mappa codici (Channel 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

-   [Eseguire il mapping dello stack di chiamate](#MapStack)

-   [Aggiungere appunti sul codice](#MakeNotes)

-   [Aggiornare la mappa con lo stack di chiamate successivo](#UpdateMap)

-   [Aggiungere il codice correlato alla mappa](#AddRelatedCode)

-   [Individuare bug usando la mappa](#FindBugs)

-   [DOMANDE E RISPOSTE](#QA)

 Per informazioni dettagliate dei comandi e le azioni è possibile usare quando si lavora con le mappe codici, vedere [cercare e ridisporre le mappe codice](../modeling/browse-and-rearrange-code-maps.md).

##  <a name="MapStack"></a> Eseguire il mapping dello stack di chiamate

1.  Avviare il debug. (Tastiera: **F5**)

2.  Dopo che l'app passa alla modalità di interruzione o si esegue una funzione, scegli **mappa codice**. (Tastiera: **Ctrl** + **MAIUSC** + **`**)

     ![Scegliere la mappa codici per avviare nello stack di chiamate di mapping](../debugger/media/debuggermap_choosecodemap.png "DebuggerMap_ChooseCodeMap")

     Lo stack di chiamate corrente verrà visualizzato in arancione in una nuova mappa del codice:

     ![Vedere stack di chiamate nella mappa del codice](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

     La mappa si aggiornerà automaticamente durante il debug. Visualizzare [aggiornare la mappa con lo stack di chiamate successivo](#UpdateMap).

##  <a name="MakeNotes"></a> Aggiungere appunti sul codice
 Aggiungere commenti per tenere traccia di ciò che avviene nel codice. Per aggiungere una nuova riga in un commento, premere **MAIUSC + INVIO**.

 ![Aggiungere un commento allo stack di chiamate nella mappa codici](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")

##  <a name="UpdateMap"></a> Aggiornare la mappa con lo stack di chiamate successivo
 Eseguire l'app fino al punto di interruzione successivo o eseguire una funzione. La mappa aggiungerà un nuovo stack di chiamate.

 ![Aggiornare la mappa codice con stack di chiamate successivo](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")

##  <a name="AddRelatedCode"></a> Aggiungere il codice correlato alla mappa
 Ora hai una mappa - che cosa successivamente? Se si lavora con Visual c# o Visual Basic, aggiungere elementi, ad esempio campi, proprietà e altri metodi, per tenere traccia di ciò che avviene nel codice.

 Fare doppio clic su un metodo per visualizzarne la definizione del codice o usare il menu di scelta rapida del metodo. (Tastiera: selezionare il metodo nella mappa e premere **F12**)

 ![Passare alla definizione di codice per un metodo nella mappa del codice](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

 Aggiungere gli elementi di cui si vuole tenere traccia nella mappa.

 ![Visualizzare i campi di un metodo nella mappa del codice dello stack di chiamate](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")

> [!NOTE]
>  Per impostazione predefinita, quando si aggiungono gli elementi alla mappa si aggiungono anche i nodi di gruppo padre, ad esempio la classe, spazio dei nomi e l'assembly. Sebbene questo sia utile, è possibile mantenere la mappa semplice disattivando questa funzionalità usando il **Includi padri** pulsante sulla barra degli strumenti della mappa o premendo **CTRL** quando si aggiungono elementi.

 ![Campi correlati a un metodo nella mappa del codice dello stack di chiamate](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")

 Di seguito è possibile visualizzare i metodi in cui vengono usati gli stessi campi. Gli elementi aggiunti più di recente sono indicati in verde.

 Continuare a compilare la mappa per visualizzare altro codice.

 ![Vedere i metodi che usano un campo: mappa del codice dello stack di chiamate](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")

 ![I metodi che usano un campo nella mappa del codice dello stack di chiamate](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")

##  <a name="FindBugs"></a> Individuare bug usando la mappa
 Visualizzando il codice, sarà possibile rilevare i bug più rapidamente. Si supponga, ad esempio, che si sta esaminando un bug in un programma di disegno. Quando si disegna una linea e si tenta di annullare l'operazione, non accadrà nulla finché non si disegnerà un'altra riga.

 Pertanto, impostare punti di interruzione nei metodi `clear`, `undo` e `Repaint`, avviare il debug e compilare una mappa come quella indicata di seguito:

 ![Aggiungere un altro stack di chiamate alla mappa codici](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 Tutte le azioni dell'utente nella mappa chiamano `Repaint`, tranne `undo`. Ciò potrebbe spiegare il motivo `undo` non funziona nell'immediato.

 Dopo aver corretto il bug e continuato a eseguire il programma, la mappa aggiungerà la nuova chiamata da `undo` in `Repaint`:

 ![Aggiungere nuovo metodo chiamata allo stack di chiamate nella mappa del codice](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

##  <a name="QA"></a> Domande e risposte

-   **Non tutte le chiamate vengono visualizzate sulla mappa. Perché?**

     Per impostazione predefinita, nella mappa viene visualizzato solo il proprio codice. Per visualizzare il codice esterno, attivarlo nella **Stack di chiamate** finestra:

     ![Visualizzare il codice esterno tramite la finestra Stack di chiamate](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")

     oppure disattivare **Abilita Just My Code** nelle opzioni di debug di Visual Studio:

     ![Mostra codice esterno tramite una finestra di dialogo Opzioni](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")

-   **La modifica della mappa influisce il codice?**

     La modifica della mappa non influenza sul codice in alcun modo. È possibile rinominare, spostare o rimuovere qualsiasi elemento nella mappa.

-   **Che cosa significa questo messaggio: "il diagramma potrebbe essere basato su una versione precedente del codice"?**

     È possibile che il codice sia stato modificato dopo l'ultimo aggiornamento della mappa. Ad esempio, nel codice potrebbe non essere più disponibile una chiamata alla mappa. Chiudere il messaggio, quindi provare a ricompilare la soluzione prima di aggiornare di nuovo la mappa.

-   **Come si controlla il layout della mappa?**

     Aprire il **Layout** menu sulla barra degli strumenti della mappa:

    -   Modificare il layout predefinito.

    -   Per arrestare automaticamente la ridisposizione della mappa, disattivare **Layout automatico durante il debug**.

    -   Per ridisporre la mappa il meno possibile quando si aggiungono elementi, disattivare **Layout incrementale**.

-   **È possibile condividere la mappa con altri utenti?**

     È possibile esportare la mappa, inviarla ad altri se è installato Microsoft Outlook o salvarla nella soluzione in modo che sia possibile archiviarla nel controllo della versione di Team Foundation.

     ![Mappa del codice dello stack chiamate condivisione con altri utenti](../debugger/media/debuggermap_sharewithothers.png "DebuggerMap_ShareWithOthers")

-   **Come si interrompono la mappa di aggiungere automaticamente nuovi stack di chiamate?**

     Scegli ![pulsante &#45; Mostra stack di chiamate nella mappa del codice automaticamente](../debugger/media/debuggermap_automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") sulla barra degli strumenti della mappa. Per aggiungere manualmente lo stack di chiamate corrente alla mappa, premere **Ctrl** + **MAIUSC** + **`**.

     La mappa continuerà a evidenziare gli stack di chiamate esistenti sulla mappa durante il debug.

-   **Le icone degli elementi e le frecce significato**

     Per ottenere altre informazioni su un elemento, spostare il puntatore del mouse su di esso ed esaminare la descrizione comando. È anche possibile esaminare i **legenda** per informazioni su cosa significa che ogni icona.

     ![Cosa significano le icone nella mappa del codice dello stack di chiamate? ] (../debugger/media/debuggermap_showlegend.png "DebuggerMap_ShowLegend")

 Vedere:

-   [Eseguire il mapping dello stack di chiamate](#MapStack)

-   [Aggiungere appunti sul codice](#MakeNotes)

-   [Aggiornare la mappa con lo stack di chiamate successivo](#UpdateMap)

-   [Aggiungere il codice correlato alla mappa](#AddRelatedCode)

-   [Individuare bug usando la mappa](#FindBugs)

## <a name="see-also"></a>Vedere anche
 [Eseguire il mapping delle dipendenze nelle soluzioni](../modeling/map-dependencies-across-your-solutions.md) [usare le mappe codice per il debug delle applicazioni](../modeling/use-code-maps-to-debug-your-applications.md) [trovare problemi potenziali usando codice di eseguire il mapping di analizzatori](../modeling/find-potential-problems-using-code-map-analyzers.md) [cercare e ridisporre le mappe codice](../modeling/browse-and-rearrange-code-maps.md)