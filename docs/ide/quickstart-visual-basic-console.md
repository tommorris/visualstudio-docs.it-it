---
title: 'Guida introduttiva: Creare un''app console in Visual Studio con Visual Basic | Microsoft Docs'
ms.custom: 
ms.date: 12/05/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs: vb
ms.openlocfilehash: 57441895ccff8bf32b59d6306ca4ae618382d356
ms.sourcegitcommit: 38097344f3ff74ba7b03bcfa45910015ca6bc2be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2017
---
# <a name="quickstart-create-a-console-app-in-visual-studio-with-visual-basic"></a>Guida introduttiva: Creare un'app console in Visual Studio con Visual Basic
In questa introduzione di 5-10 minuti all'ambiente di sviluppo integrato (IDE) di Visual Studio si creerà una semplice applicazione di Visual Basic che viene eseguita nella console.

Se non è ancora stato installato Visual Studio, accedere alla pagina [Download di Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) per installarlo gratuitamente.

## <a name="create-a-project"></a>Creare un progetto
In primo luogo si creerà un progetto di applicazione Visual Basic. Il tipo di progetto include fin dall'inizio tutti i file modello necessari.

1. Aprire Visual Studio 2017.

2. Nella barra dei menu in alto scegliere **File** > **Nuovo** > **Progetto**.

3. Nel riquadro sinistro della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi selezionare **.NET Core**. Nel riquadro centrale scegliere **Console App (.NET Core)** (App console (.NET Core)). Quindi assegnare al progetto il nome *HelloWorld*.

   ![Carico di lavoro Sviluppo multipiattaforma .NET Core nel programma di installazione di Visual Studio](../ide/media/new-project-vb-dotnet-helloworld-console-app.png)

     Se non viene visualizzato il modello di progetto **Console App (.NET Core)** (App console (.NET Core)), fare clic sul collegamento **Apri il programma di installazione di Visual Studio** nel riquadro sinistro della finestra di dialogo **Nuovo progetto**.

   ![Fare clic sul collegamento Apri il programma di installazione di Visual Studio nella finestra di dialogo Nuovo progetto](../ide/media/vb-open-visual-studio-installer.png)

     Verrà avviato il Programma di installazione di Visual Studio. Scegliere il carico di lavoro **Sviluppo multipiattaforma .NET Core**, quindi scegliere **Modifica**.

     ![Carico di lavoro Sviluppo multipiattaforma .NET Core nel programma di installazione di Visual Studio](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>Creare l'applicazione
Dopo la selezione del modello di progetto Visual Basic e l'assegnazione di un nome al progetto, in Visual Studio viene creata una semplice applicazione "Hello World". Viene chiamato il metodo [Console.WriteLine(System.String)](https://docs.microsoft.com/en-us/dotnet/api/system.console.writeline?view=netframework-4.7.1#System_Console_WriteLine_System_String) per visualizzare la stringa letterale "Hello World!" nella finestra della console.

![Visualizzare il codice Hello World predefinito dal modello](../ide/media/vb-console-helloworld-template.png)

Se si fa clic sul pulsante **HelloWorld** nell'IDE è possibile eseguire il programma in modalità debug.

  ![Fare clic sul pulsante HelloWorld per eseguire il programma in modalità debug](../ide/media/vb-console-hello-world-button.png)

Se si esegue questa operazione, la finestra della console resta visibile per un istante, quindi viene chiusa. Ciò accade perché il metodo `Main` termina dopo l'esecuzione dell'unica istruzione, quindi l'applicazione termina.

### <a name="add-some-code"></a>Aggiungere codice
Ora si aggiungerà del codice per sospendere l'applicazione e richiedere l'input dell'utente.

1. Immediatamente dopo la chiamata al metodo [Console.WriteLine(System.String)](https://docs.microsoft.com/en-us/dotnet/api/system.console.writeline?view=netframework-4.7.1#System_Console_WriteLine_System_String) aggiungere il codice seguente:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Questo codice sospende l'esecuzione del programma fino a quando non si preme un tasto.

2. Nella barra dei menu selezionare **Compila** > **Compila soluzione**.

   Il programma viene compilato in un linguaggio intermedio (IL) che viene successivamente convertito in codice binario da un compilatore JIT (Just-In-Time).

## <a name="run-the-application"></a>Esecuzione dell'applicazione
1. Fare clic sul pulsante **HelloWorld** nella barra degli strumenti.

   ![Fare clic sul pulsante HelloWorld per eseguire il programma dalla barra degli strumenti](../ide/media/vb-console-hello-world-button.png)

2. Premere un tasto qualsiasi per chiudere la finestra della console.

   ![Finestra della console che visualizza Hello World e Premere un tasto qualsiasi per continuare](../ide/media/vb-console-hello-world-press-any-key.png)

La guida introduttiva è stata completata. Ci auguriamo che sia stata utile per l'apprendimento dell'uso di Visual Basic e dell'IDE di Visual Studio. Per approfondire ancora le conoscenze, continuare con un'esercitazione nella sezione **Esercitazioni** del sommario.

## <a name="see-also"></a>Vedere anche
* [Guida introduttiva: Creare un'app Windows Forms "Hello World" in Visual Studio con Visual Basic](quickstart-visual-basic-winforms.md)
* [Learn more about Visual Basic IntelliSense](visual-basic-specific-intellisense.md) (Altre informazioni su Visual Basic IntelliSense)