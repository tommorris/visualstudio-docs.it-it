---
title: Debug di applicazioni in modalità mista | Microsoft Docs
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
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging, property evaluation
- Call Stack window
- mixed-mode debugging
- Call Stack window, mixed-mode debugging
- debugging managed code, mixed code
- mixed-mode debugging, call stack
ms.assetid: 60e34477-ae4e-48c7-9093-3e37f72e1bc3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 795b1bf9f2c3d2014e1fa2c4ccd25254a07a70a8
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283314"
---
# <a name="debugging-mixed-mode-applications"></a>Debug delle applicazioni in modalità mista
Un'applicazione in modalità mista combina codice nativo (C++) con codice gestito, ad esempio Visual Basic, Visual C# o C++ eseguito in Common Language Runtime. Il debug di applicazioni in modalità mista è ampiamente trasparente in [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] e non è molto diverso dal debug di un'applicazione in modalità singola. È tuttavia necessario fare alcune considerazioni specifiche.  
  
## <a name="enable-c-edit-and-continue-in-mixed-mode-debugging"></a>Abilitare la funzione di modifica e continuazione di C++ nel debug in modalità mista  

Per abilitare la funzionalità Modifica e continuazione per C++, vedere [come abilitare e disabilitare Modifica e continuazione](../debugger/how-to-enable-and-disable-edit-and-continue.md).

> [!NOTE]
> Per utilizzare Modifica e continuazione per C++ in Visual Studio 2013, è necessario ripristinare il motore di debug legacy. Visualizzare [passando alla modalità di compatibilità gestita in Visual Studio 2013](https://blogs.msdn.microsoft.com/devops/2013/10/16/switching-to-managed-compatibility-mode-in-visual-studio-2013/) sul blog di Microsoft Application Lifecycle Management.  
  
## <a name="property-evaluation-in-mixed-mode-applications"></a>Valutazione delle proprietà nelle applicazioni in modalità mista  
 In un'applicazione in modalità mista la valutazione delle proprietà tramite il debugger è un'operazione complessa. Di conseguenza, alcune operazioni di debug, ad esempio il debug passo a passo, possono risultare lente. Per altre informazioni, vedere [esecuzione di istruzioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ek13f001(v=vs.100)). Se nel debug in modalità mista le prestazioni non risultano soddisfacenti, disattivare la valutazione delle proprietà nelle finestre del debugger.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
#### <a name="to-turn-off-property-evaluation"></a>Per disattivare la valutazione delle proprietà  
  
1.  Scegliere **Opzioni** dal menu **Strumenti**.  
  
2.  Nel **le opzioni** finestra di dialogo, aprire il **debug** cartella e selezionare il **generale** categoria.  
  
3.  Cancella il **Abilita valutazione delle proprietà e altre chiamate di funzioni implicite** casella di controllo.  
  
 Poiché gli stack di chiamate native sono diversi dagli stack di chiamate gestite, il debugger non può sempre fornire lo stack di chiamate completate per il codice misto. Quando il codice nativo chiama il codice gestito, possono essere presenti alcune differenze. Per altre informazioni, vedere [codice misto e informazioni mancanti nella finestra Stack di chiamate](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Debug di codice gestito](../debugger/debugging-managed-code.md)