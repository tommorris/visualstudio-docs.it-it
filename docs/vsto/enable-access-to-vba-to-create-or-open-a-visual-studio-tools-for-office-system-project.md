---
title: Abilitare l'accesso a VBA per creare o aprire un Visual Studio Tools per Microsoft Office system project
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office system project
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f17c4e1481e7f33034e16d1e60a285b25c6f8230
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448991"
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>Abilitare l'accesso a VBA per creare o aprire un Visual Studio Tools per Microsoft Office system project

Prima di poter creare o aprire un Visual Studio Tools per Microsoft Office system project, è necessario abilitare esplicitamente l'accesso a Visual Basic Applications (VBA) sistema del progetto in Microsoft Office.

 Progetti di sviluppo di Microsoft Office richiedono l'accesso a Visual Basic il sistema di progetto Applications (VBA) in Microsoft Office Word e Microsoft Office Excel, anche se i progetti non utilizzano Visual Basic per le applicazioni. Il supporto in fase di progettazione dei controlli sia nei progetti di Visual Basic che in quelli di Visual C# dipende infatti dal sistema di progetto di Visual Basic, Applications Edition.

 Alcuni virus macro per Microsoft Office provano ad automatizzare il sistema di progetto di Visual Basic, Applications Edition per propagarsi. Abilitando l'accesso al sistema di progetto di Visual Basic, Applications Edition, si rimuove una protezione utile contro la diffusione dei virus macro. Rimangono tuttavia attivi i normali livelli di sicurezza delle macro, che, assieme all'elenco degli autori attendibili impostati per le applicazioni di Office, determineranno l'esecuzione delle macro nel computer.

> [!NOTE]
> Tale condizione si applica solo al computer di sviluppo. Computer degli utenti finali non è necessario abilitare questa opzione per eseguire soluzioni Office.

 È importante notare che la disabilitazione dell'accesso al sistema di progetto di Visual Basic, Applications Edition non comporta da sola la protezione dai virus, ma consente semplicemente di interrompere la diffusione di alcuni virus ad altri documenti se il computer viene infettato da un virus macro. Per impostazione predefinita, l'opzione è disabilitata per fornire un ulteriore livello di sicurezza per il computer, ma la sua abilitazione non rende il computer maggiormente soggetto ai virus se si seguono le procedure di sicurezza consigliate.

 La migliore protezione contro Office virus macro consiste nell'eseguire Office a un livello di sicurezza elevato o molto elevato, nel ritenere attendibili solo le macro provenienti da origini verificate, e per rimanere aggiornati con patch di sicurezza e programmi antivirus.

 Per ulteriori informazioni sulla protezione del PC da virus e codice dannoso, vedere [ http://www.microsoft.com/protect ](http://www.microsoft.com/protect).

 È possibile abilitare o disabilitare l'opzione **considera attendibile l'accesso al progetto Visual Basic** manualmente.

 È possibile ripristinare l'installazione di Office se vengono visualizzati errori VBA o COM.

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>Per abilitare o disabilitare l'accesso a Visual Basic (progetti)

1. Scegliere la scheda **File** .

2. Fare clic su **Opzioni**.

3. Fare clic su **centro**, quindi fare clic su **impostazioni Centro protezione**.

4. Nel **centro**, fare clic su **impostazioni Macro**.

5. Selezionare o deselezionare **considera attendibile l'accesso al modello a oggetti VBA progetto** per abilitare o disabilitare l'accesso ai progetti di Visual Basic.

6. Fare clic su **OK**.

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>Per abilitare o disabilitare l'accesso ai progetti di Visual Basic con Microsoft Office system 2007

1. Nel **strumenti** dal menu di Word o Excel, scegliere **Macro**e quindi fare clic su **sicurezza**.

2. Nel **protezione** finestra di dialogo, fare clic sul **autori attendibili** scheda.

3. Selezionare per abilitare o deselezionarla per disabilitarla **considera attendibile l'accesso al progetto Visual Basic**.

4. Fare clic su **OK**.

## <a name="to-set-your-office-macro-security-level"></a>Per impostare il livello di sicurezza delle macro di Office

1. Scegliere la scheda **File** .

2. Fare clic su **Opzioni**.

3. Fare clic su **centro**, quindi fare clic su **impostazioni Centro protezione**.

4. Nel **centro**, fare clic su **impostazioni Macro**.

5. Nel **impostazioni Macro** , selezionare l'impostazione desiderata.

6. Fare clic su **OK**.

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>Per impostare il livello di protezione (macro) di Office con Microsoft Office system 2007

1. Nel **strumenti** dal menu di Word o Excel, scegliere **Macro**e quindi fare clic su **sicurezza**.

2. Nel **livello di sicurezza** scheda, selezionare l'impostazione desiderata.

    Il **livello di sicurezza** scheda contiene informazioni dettagliate su ogni livello. Per altre informazioni, vedere l'argomento "Livelli di sicurezza delle macro" nella Guida di Office.

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>Per installare VBA con Microsoft Office System 2007

1. Nel Pannello di controllo, eseguire **Aggiungi / Rimuovi programmi** oppure **programmi e funzionalità**.

2. Selezionare Microsoft Office nel **programmi attualmente installati** elenco.

3. Fare clic su **Cambia**.

4. Selezionare **Aggiungi / Rimuovi funzionalità**, quindi fare clic su **continua**.

5. Selezionare **Scegli personalizzazione avanzata applicazioni**, quindi fare clic su **successivo**.

6. Espandere **Caratteristiche condivise di Office** nel **scegliere le opzioni di aggiornamento per applicazioni e strumenti** elenco.

7. Aprire il menu di riepilogo a discesa accanto a **Visual Basic for Applications**, quindi fare clic su **esecuzione dal Computer locale**.

8. Scegliere **Continua**.

9. Fare clic su **Chiudi**.

## <a name="to-repair-your-installation-of-office"></a>Per ripristinare l'installazione di Office

1. Nel Pannello di controllo, eseguire **Aggiungi / Rimuovi programmi** oppure **programmi e funzionalità**.

2. Selezionare la versione di Office nel **programmi attualmente installati** elenco.

3. Fare clic su **Cambia**.

4. Selezionare **Reinstalla o Ripristina**, quindi fare clic su **successivo**.

5. Selezionare **rileva e correggere errori nell'installazione di Office**, quindi fare clic su **installare**.

## <a name="see-also"></a>Vedere anche

 [Proteggere le soluzioni Office](../vsto/securing-office-solutions.md)