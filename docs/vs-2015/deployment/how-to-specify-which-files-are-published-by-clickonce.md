---
title: 'Procedura: specificare i file da pubblicare mediante ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.File
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, file exclusion
- files, publishing via ClickOnce
ms.assetid: 579c134a-d50f-4e0c-8e05-2a4ff654896a
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: c56d378c8adee1801fb82fc4a2ed84e5b05c0aef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47519915"
---
# <a name="how-to-specify-which-files-are-published-by-clickonce"></a>Procedura: specificare i file da pubblicare mediante ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [procedura: specificare quale file da pubblicare mediante ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-specify-which-files-are-published-by-clickonce).  
  
Quando si pubblica un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] i file di applicazione, tutte le non di codice nel progetto vengono distribuiti insieme all'applicazione. In alcuni casi, si potrebbe non desidera che la pubblicazione di determinati file o che si desidera installare determinati file in base alle condizioni. Visual Studio offre le funzionalità per escludere i file, contrassegnarli come file di dati o prerequisiti e creare gruppi di file per l'installazione condizionale.  
  
 I file da un [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] dell'applicazione vengono gestiti nel **i file dell'applicazione** finestra di dialogo, accessibile dal **pubblica** pagina del **Progettazione progetti**.  
  
 Inizialmente, è presente un gruppo singolo file denominato **(obbligatorio)**. È possibile creare gruppi di file aggiuntivi e assegnare loro i file. Non è possibile modificare il **gruppo di Download** per i file necessari per l'esecuzione dell'applicazione. Ad esempio, .exe o i file dell'applicazione contrassegnata come file di dati devono appartenere al **(obbligatorio)** gruppo.  
  
 Lo stato della pubblicazione predefinita pari a un file viene contrassegnato con **(Auto)**. Ad esempio, .exe dell'applicazione ha lo stato di pubblicazione **Includi (Auto)** per impostazione predefinita.  
  
 I file con il **Build Action** impostata su **contenuto** sono designati come file dell'applicazione e verrà contrassegnato come incluso per impostazione predefinita. Possono essere inclusi, escluse o contrassegnati come file di dati. Le eccezioni sono i seguenti:  
  
-   I file di dati, ad esempio file XML e file di Database SQL (con estensione mdf e mdb) verranno contrassegnati come file di dati per impostazione predefinita.  
  
-   I riferimenti agli assembly (file con estensione dll) vengono designati come indicato di seguito quando si aggiunge il riferimento: se **Copia localmente** viene **False**, è contrassegnata per impostazione predefinita come assembly prerequisiti (**(dei prerequisiti Auto)**) che deve essere presente nella Global Assembly Cache prima di installare l'applicazione. Se **Copia localmente** viene **True**, l'assembly è contrassegnato per impostazione predefinita come un assembly dell'applicazione (**Includi (Auto)**) e verrà copiato nella cartella dell'applicazione al momento dell'installazione. Un riferimento COM verrà visualizzato nei **i file dell'applicazione** finestra di dialogo casella (come un file ocx) solo se relativo **Isolated** viene impostata su **True**. Per impostazione predefinita, verrà incluso.  
  
### <a name="to-add-files-to-the-application-files-dialog-box"></a>Per aggiungere file alla finestra di dialogo file applicazione  
  
1.  Selezionare un file di dati in **Esplora soluzioni**.  
  
2.  Nella finestra Proprietà modificare il **Build Action** proprietà per il **contenuto** valore.  
  
### <a name="to-exclude-files-from-clickonce-publishing"></a>Per escludere file dalla pubblicazione ClickOnce  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Scegliere il **pubblica** scheda.  
  
3.  Fare clic sul **i file dell'applicazione** per aprire il **i file dell'applicazione** nella finestra di dialogo.  
  
4.  Nel **i file dell'applicazione** finestra di dialogo, selezionare il file che si desidera escludere.  
  
5.  Nel **stato pubblicazione** campi, selezionare **escludere** nell'elenco a discesa.  
  
### <a name="to-mark-files-as-data-files"></a>Per contrassegnare i file come file di dati  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Scegliere il **pubblica** scheda.  
  
3.  Fare clic sul **i file dell'applicazione** per aprire il **i file dell'applicazione** nella finestra di dialogo.  
  
4.  Nel **i file dell'applicazione** finestra di dialogo, selezionare il file che si desidera contrassegnare come dati.  
  
5.  Nel **stato pubblicazione** campi, selezionare **File di dati** nell'elenco a discesa.  
  
### <a name="to-mark-files-as-prerequisites"></a>Per contrassegnare i file come prerequisiti  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Scegliere il **pubblica** scheda.  
  
3.  Fare clic sul **i file dell'applicazione** per aprire il **i file dell'applicazione** nella finestra di dialogo.  
  
4.  Nel **i file dell'applicazione** finestra di dialogo, selezionare l'assembly dell'applicazione (file con estensione dll) che si desidera contrassegnare come prerequisito. Si noti che l'applicazione deve contenere un riferimento all'assembly dell'applicazione affinché venga visualizzato nell'elenco.  
  
5.  Nel **stato pubblicazione** campi, selezionare **prerequisiti** nell'elenco a discesa.  
  
### <a name="to-add-a-new-file-group"></a>Per aggiungere un nuovo gruppo di file  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Scegliere il **pubblica** scheda.  
  
3.  Fare clic sul **i file dell'applicazione** per aprire il **i file dell'applicazione** nella finestra di dialogo.  
  
4.  Nel **i file dell'applicazione** finestra di dialogo, seleziona la **gruppo** field per un file che si desidera includere nel nuovo gruppo.  
  
    > [!NOTE]
    >  I file devono avere la **azione di compilazione** proprietà impostata su **contenuto** prima che vengano visualizzati i nomi dei file nei **i file dell'applicazione** nella finestra di dialogo.  
  
5.  Nel **gruppo di Download** campi, selezionare  **\<nuovo... >** nell'elenco a discesa.  
  
6.  Nel **nuovo gruppo** della finestra di dialogo immettere un nome per il gruppo e quindi fare clic su **OK**.  
  
### <a name="to-add-a-file-to-a-group"></a>Per aggiungere un file a un gruppo  
  
1.  Con un progetto selezionato in **Esplora soluzioni**, scegliere **Proprietà** dal menu **Progetto**.  
  
2.  Scegliere il **pubblica** scheda.  
  
3.  Fare clic sul **i file dell'applicazione** per aprire il **i file dell'applicazione** nella finestra di dialogo.  
  
4.  Nel **i file dell'applicazione** finestra di dialogo, seleziona la **gruppo** field per un file che si desidera includere nel nuovo gruppo.  
  
5.  Nel **gruppo di Download** campo, selezionare un gruppo di nell'elenco a discesa.  
  
    > [!NOTE]
    >  Non è possibile modificare il **gruppo di Download** per i file necessari per l'esecuzione dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Pubblicazione di applicazioni ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Procedura: Pubblicare un'applicazione ClickOnce mediante la Pubblicazione guidata](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



