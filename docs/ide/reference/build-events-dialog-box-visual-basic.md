---
title: Finestra di dialogo Eventi di compilazione (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesBuildEvents
helpviewer_keywords:
- build events
- build events, specifying
- pre-build events
- Build Events dialog box
- post-build events
ms.assetid: 3a81a7c7-39f9-47a8-ba5a-b351227f380e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 38ef3b173643c7bff0e1417ffc9ecfb431b06685
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31944135"
---
# <a name="build-events-dialog-box-visual-basic"></a>Finestra di dialogo Eventi di compilazione (Visual Basic)
Usare la finestra di dialogo **Eventi di compilazione** per specificare le istruzioni di configurazione della build. È anche possibile specificare le condizioni in cui vengono eseguiti tutti gli eventi di pre-compilazione o post-compilazione. Per altre informazioni, vedere [Procedura: Specificare gli eventi di compilazione (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md).

 **Riga di comando dell'evento di pre-compilazione**Specifica i comandi da eseguire prima dell'avvio della compilazione. Per immettere comandi lunghi, fare clic su **Modifica pre-compilazione** per visualizzare la [finestra di dialogo Riga di comando eventi pre-compilazione/post-compilazione](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md).

> [!NOTE]
> Gli eventi di pre-compilazione non vengono eseguiti se il progetto è aggiornato e non viene attivata alcuna compilazione.


 **Riga di comando dell'evento di post-compilazione**Specifica i comandi da eseguire dopo l'avvio della compilazione. Per immettere comandi lunghi, fare clic su **Modifica post-compilazione** per visualizzare la **finestra di dialogo Riga di comando eventi pre-compilazione/post-compilazione**.

> [!NOTE]
> Aggiungere un'istruzione `call` prima di tutti gli eventi di compilazione che eseguono file con estensione BAT. Ad esempio, `call C:\MyFile.bat` o `call C:\MyFile.bat call C:\MyFile2.bat`.


 **Eseguire l'evento di post-compilazione**Specifica le condizioni per l'esecuzione dell'evento di post-compilazione, come illustrato in questa tabella.

|Opzione|Risultato|
|------------|------------|
|**Sempre**|L'evento di post-compilazione verrà sempre eseguito, indipendentemente dall'esito della compilazione.|
|**A compilazione completata**|L'evento di post-compilazione verrà eseguito se la compilazione avrà esito positivo. L'evento verrà eseguito anche per un progetto aggiornato, purché la compilazione abbia esito positivo. Questa è l'impostazione predefinita.|
|**Quando la compilazione aggiorna l'output del progetto**|L'evento di post-compilazione verrà eseguito solo quando i file di output del compilatore (con estensione exe o dll) saranno diversi dal file di output del compilatore precedente. Un evento di post-compilazione non viene eseguito se un progetto è aggiornato.|

## <a name="see-also"></a>Vedere anche

- [Pagina Compilazione, Creazione progetti (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)
- [Procedura: Specificare gli eventi di compilazione (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Finestra di dialogo Riga di comando eventi pre-compilazione/post-compilazione](../../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)