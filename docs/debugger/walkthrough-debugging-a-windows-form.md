---
title: 'Procedura dettagliata: Debug di un Form di Windows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- debugging managed code, Windows Forms
- debugging [Visual Studio], Windows Forms
- Attach to Process dialog box
- debugger, attaching to programs
- Attach to Process dialog box, walkthroughs
- Windows Forms, debugging
- debugging Windows Forms, walkthroughs
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fdd9dadc92143fabfaeea35d776b57b4b4c1748
ms.sourcegitcommit: 0cf1e63b6e0e6a0130668278489b21a6e5038084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2018
ms.locfileid: "39468530"
---
# <a name="walkthrough-debugging-a-windows-form"></a>Procedura dettagliata: debug di un Windows Form
Un modulo di Windows è una delle applicazioni gestite più comuni. Un modulo di Windows consente di creare un'applicazione di Windows standard. È possibile completare questa procedura dettagliata usando Visual Basic, c# o C++.  
  
 In primo luogo, è necessario chiudere eventuali soluzioni aperte.  
  
### <a name="to-prepare-for-this-walkthrough"></a>Operazioni preliminari per la procedura dettagliata  
  
-   Se già aperto una soluzione aperta, chiuderla. (Nelle **File** dal menu **Chiudi soluzione**.)  
  
## <a name="create-a-new-windows-form"></a>Creare un nuovo modulo di Windows  
 Successivamente, si creerà un nuovo modulo di Windows.  
  
#### <a name="to-create-the-windows-form-for-this-walkthrough"></a>Per creare il modulo di Windows per questa procedura dettagliata  
  
1.  Nel **File** menu, scegliere **New** e fare clic su **progetto**.  
  
     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2.  Nel riquadro di tipi di progetto, aprire il **Visual Basic**, **Visual c#**, o **Visual C++** nodo, quindi  
  
    1.  Per Visual Basic o Visual c#, selezionare **Desktop di Windows** > **App di Windows Form**.  
  
    2.  Per Visual C++, selezionare **alle applicazioni Desktop Windows**.  
  
3.  Nel **nome** casella, assegnare al progetto un nome univoco, ad esempio, Procedura_DebugSemplice.  
  
4.  Fare clic su **OK**.  
  
     Visual Studio crea un nuovo progetto e visualizza un nuovo form nella finestra di progettazione Windows Form. Per altre informazioni, vedere [finestra di progettazione Windows Form](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15).  
  
5.  Nel **View** dal menu **della casella degli strumenti**.  
  
     Verrà visualizzata la casella degli strumenti. Per altre informazioni, vedere [Casella degli strumenti](../ide/reference/toolbox.md).  
  
6.  Nella casella degli strumenti, fare clic sui **pulsante** controllo e trascinare il controllo all'area di progettazione Form. Rilasciare il pulsante sul form.  
  
7.  Nella casella degli strumenti, fare clic sui **casella di testo** controllo e trascinare il controllo all'area di progettazione Form. Eliminare il **casella di testo** nel form.  
  
8. Nell'area di progettazione di form, fare doppio clic sul pulsante.  
  
     Verrà visualizzata la tabella codici. Il cursore deve trovarsi in `button1_Click`.  
  
10. Nella funzione `button1_Click`., aggiungere il codice seguente:  
  
    ```vb  
    textBox1.Text = "Button was clicked!"
    ```  
  
    ```csharp 
    textBox1.Text = "Button was clicked!";
    ```  
  
    ```cpp  
    textBox1->Text = "Button was clicked!";  
    ```  
  
11. Scegliere **Compila soluzione** dal menu **Compila**.  
  
     Il progetto dovrebbe essere compilato senza errori.  
  
## <a name="debug-your-form"></a>Eseguire il debug del modulo  
 A questo punto, si è pronti per iniziare il debug.  
  
#### <a name="to-debug-the-windows-form-created-for-this-walkthrough"></a>Eseguire il debug di Windows Form creato per questa procedura dettagliata  
  
1.  Nella finestra di origine, fare clic sul margine sinistro nella stessa riga come il testo aggiunto:  
  
     ```vb  
    textBox1.Text = "Button was clicked!"
    ```  
  
    ```csharp 
    textBox1.Text = "Button was clicked!";
    ```  
  
    ```cpp  
    textBox1->Text = "Button was clicked!";  
    ``` 
  
     Verrà visualizzato un punto di colore rosso e il testo sulla riga verrà evidenziato in rosso. Il punto di colore rosso rappresenta un punto di interruzione. Per altre informazioni, vedere [i punti di interruzione](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583). Quando verrà raggiunto questo punto nel codice, l'esecuzione dell'applicazione nel debugger verrà interrotta. Sarà quindi possibile visualizzare lo stato dell'applicazione ed eseguirne il debug.  
  
    > [!NOTE]
    >  È anche possibile fare doppio clic su qualsiasi riga di codice, scegliere **punto di interruzione**, quindi fare clic su **Inserisci punto di interruzione** per aggiungere un punto di interruzione sulla riga.  
  
2.  ON la **Debug** menu, scegliere **avviare**.  
  
     Il modulo di Windows viene avviata l'esecuzione.  
  
3.  Nel modulo di Windows fare clic sul pulsante che è stato aggiunto.  
  
     In Visual Studio, verrà visualizzata la riga in cui è impostato il punto di interruzione sulla tabella codici. Tale riga dovrebbe essere evidenziata in giallo. A questo punto è possibile visualizzare le variabili dell'applicazione e controllarne l'esecuzione. L'applicazione è stata arrestata l'esecuzione, in attesa di un'azione da parte dell'utente.  
  
4.  Nel **Debug** menu, scegliere **Windows**, quindi **Watch**e fare clic su **espressione di controllo1**.  
  
5.  Nel **espressione di controllo1** finestra, fare clic su una riga vuota. Nel **Name** colonna, digitare `textBox1.Text` (se si usa Visual Basic o Visual c#) o `textBox1->Text` (se si usa C++), quindi premere INVIO.  
  
     Il **espressione di controllo1** finestra verrà visualizzato il valore di questa variabile tra virgolette come:  
  
    `""`  
 
6.  Nel **Debug** menu, scegliere **Esegui istruzione**.  
  
     Il valore di textBox1.Text viene modificato nel **espressione di controllo1** finestra per:  
  
    `Button was clicked!`  
  
7.  Nel **Debug** menu, scegliere **continua** per riprendere il debug del programma.  
  
8.  Nel modulo di Windows fare clic sul pulsante.  
  
     Visual Studio interrompe l'esecuzione anche in questo caso.  
  
9. Fare clic sul punto rosso che rappresenta il punto di interruzione.  
  
     Ciò consente di rimuovere il punto di interruzione dal codice.  
  
10. Nel **Debug** menu, scegliere **arresta debug**.  
  
## <a name="attach-to-your-windows-form-application-for-debugging"></a>Collegamento all'applicazione Windows Form per il debug  
 È possibile connettere il debugger di [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] a un processo in esecuzione. Se si usa una versione Express Edition, questa funzionalità non è supportata.  
  
#### <a name="to-attach-to-the-windows-form-application-for-debugging"></a>Per connettersi all'applicazione Windows Form per il debug  
  
1.  Nel progetto creato in precedenza, fare clic sul margine sinistro per impostare nuovamente un punto di interruzione in corrispondenza della riga aggiunta:  
  
     ```vb  
    textBox1.Text = "Button was clicked!"
    ```  
  
    ```csharp 
    textBox1.Text = "Button was clicked!";
    ```  
  
    ```cpp  
    textBox1->Text = "Button was clicked!";   
  
2.  On the **Debug** menu, select **Start Without Debugging**.  
  
     The Windows Form starts running under Windows, just as if you had double-clicked its executable. The debugger is not attached.  
  
3.  On the **Debug** menu, select **Attach to Process**. (This command is also available on the **Tools** menu.)  
  
     The **Attach to Process** dialog box appears.  
  
4.  In the **Available Processes** pane, find the process name (Walkthrough_SimpleDebug.exe) in the **Process** column and click it.  
  
5.  Click the **Attach** button.  
  
6.  In your Windows Form, click the one and only button.  
  
     The debugger breaks execution of the Windows Form at the breakpoint.  
  
## See Also  
 [Debugging Managed Code](../debugger/debugging-managed-code.md)   
 [Debugger Security](../debugger/debugger-security.md)