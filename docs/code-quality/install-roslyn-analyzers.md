---
title: Installare gli analizzatori di Roslyn
ms.date: 08/03/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 5977275b352bf11914760d9cdf7ccada22caccc8
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "39512031"
---
# <a name="install-net-compiler-platform-analyzers"></a>Installare gli analizzatori .NET Compiler Platform

Visual Studio 2017 include un set di base di .NET Compiler Platform (*Roslyn*) gli analizzatori. Gli analizzatori sono sempre attivati. È possibile installare altri analizzatori come pacchetti NuGet o come estensioni di Visual Studio in *VSIX* file.

## <a name="to-install-nuget-analyzer-packages"></a>Per installare i pacchetti dell'analizzatore NuGet

1. Trovare il pacchetto dell'analizzatore che si desidera installare in www.nuget.org. Ad esempio, desideri [installare gli analizzatori Microsoft FxCop](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package) per controllare il codice per i problemi di sicurezza e prestazioni, tra gli altri.

1. Installare il pacchetto in Visual Studio, usando il [Console di gestione pacchetti](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) o nella [Package Manager UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > La pagina www.nuget.org per ogni pacchetto analyzer Mostra è il comando per incollare il **Console di gestione pacchetti**. È anche disponibile un pulsante utile per copiare il testo negli Appunti.
   >
   > ![Pagina di NuGet.org che mostra comando della Console di gestione pacchetti](media/nuget-install-command.png)

   Gli assembly dell'analizzatore sono installati e visualizzati **Esplora soluzioni** sotto **riferimenti** > **analizzatori**.

## <a name="to-install-vsix-analyzers"></a>Per installare gli analizzatori VSIX

1. In Visual Studio, selezionare **degli strumenti** > **estensioni e aggiornamenti**.

   Verrà visualizzata la finestra di dialogo **Estensioni e aggiornamenti**.

   > [!NOTE]
   > In alternativa, è possibile trovare e scaricare l'estensione di Analizzatore direttamente dal [Visual Studio Marketplace](https://marketplace.visualstudio.com).

1. Espandere **Online** nel riquadro a sinistra e quindi selezionare **Visual Studio Marketplace**.

1. Nella casella di ricerca, digitare il nome dell'estensione dell'analizzatore che si desidera installare. Ad esempio, desideri [installare gli analizzatori Microsoft FxCop](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix) per controllare il codice per i problemi di sicurezza e prestazioni, tra gli altri.

1. Selezionare **scaricare**.

   L'estensione viene scaricata.

1. Selezionare **OK** per chiudere la finestra di dialogo, quindi chiudere tutte le istanze di Visual Studio per avviare la **programma di installazione VSIX**.

   Il **programma di installazione VSIX** verrà visualizzata la finestra di dialogo.

   ![Programma di installazione VSIX per l'analisi codice Microsoft](media/vsix-installer-code-analysis.png)

1. Selezionare **Modify** per avviare l'installazione.

1. Dopo un minuto o due, il completamento dell'installazione. Selezionare **Chiudi**.

1. Aprire di nuovo Visual Studio.

Se si vuole verificare se l'estensione è installata, selezionare **degli strumenti** > **estensioni e aggiornamenti**. Nel **estensioni e aggiornamenti** finestra di dialogo, seleziona la **installato** categorie a sinistra e quindi cercare l'estensione in base al nome.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Usare gli analizzatori di Roslyn in Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli analizzatori di Roslyn in Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Installare gli analizzatori FxCop](../code-quality/install-fxcop-analyzers.md)