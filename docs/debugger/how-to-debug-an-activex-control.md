---
title: 'Procedura: eseguire il Debug di un controllo ActiveX | Documenti Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.controls.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- testing [Visual Studio], test containers
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- data-bound controls, ActiveX
- test container
- containers, specifying for debug sessions
- ActiveX controls, debugging
- testing [Visual Studio], ActiveX controls
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8892d83bb92198b9e8f1b7df1293a06f27d27716
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474427"
---
# <a name="how-to-debug-an-activex-control"></a>Procedura: eseguire il debug di un controllo ActiveX
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere Importa/esporta impostazioni dal menu Strumenti. Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
 Per effettuare il debug di un controllo ActiveX, è necessario specificare un contenitore (eseguibile) in cui elaborare il controllo stesso.  
  
### <a name="to-specify-a-container-for-the-debug-session"></a>Per specificare un contenitore per la sessione di debug  
  
1.  Selezionare il progetto in Esplora soluzioni.  
  
2.  Dal **vista** menu, scegliere **pagine delle proprietà**.  
  
3.  Nel **pagine delle proprietà del progetto** la finestra di dialogo, aprire il **le proprietà di configurazione** cartella e selezionare **debug**.  
  
4.  Sotto il **debug** categoria, individuare il **comando** proprietà.  
  
5.  Specificare il percorso del contenitore. Ad esempio, C:\Programmi\Internet Explorer\IEXPLORE.EXE.  
  
6.  Se si specifica Internet Explorer come contenitore ed la modalità Active Desktop, digitare `/new` nel **gli argomenti del comando** casella.  
  
7.  Fare clic su **OK**.  
  
     Se non si specifica un contenitore di **pagine delle proprietà del progetto** nella finestra di dialogo è possibile specificare il contenitore quando si avvia il debug. Quando si seleziona un comando di esecuzione per avviare il debug, il [eseguibile per la finestra di dialogo di sessione di debug](../debugger/executable-for-debugging-session-dialog-box.md) viene visualizzato. Nella finestra di dialogo specificare il nome percorso del contenitore.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli ActiveX](/cpp/mfc/activex-controls)   
 [Test di proprietà ed eventi con Test Container](/cpp/mfc/testing-properties-and-events-with-test-container)   
 [COM e ActiveX di debug](../debugger/com-and-activex-debugging.md)   
 [Debug in Visual Studio](../debugger/index.md)  
 [Tour delle funzionalità del debugger](../debugger/debugger-feature-tour.md)