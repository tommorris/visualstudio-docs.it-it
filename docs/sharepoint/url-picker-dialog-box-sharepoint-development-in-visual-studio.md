---
title: Finestra di dialogo Selezione URL (sviluppo per SharePoint in Visual Studio) | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e7820723c88fd76639fa47e5c97ad179a208fc18
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118867"
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>Finestra di dialogo Selezione URL (sviluppo per SharePoint in Visual Studio)
  Nella finestra di dialogo di selezione URL è possibile scegliere i file come file di pagina master o file di immagine posizionati nel progetto o nel server locale in cui è in esecuzione SharePoint.  
  
 Questa finestra di dialogo viene visualizzata se è possibile scegliere un file per impostare una proprietà. È possibile aprire questa finestra di dialogo facendo clic sui puntini di sospensione (![ellisse di ASP.NET Mobile Designer](../sharepoint/media/mwellipsis.gif "ellisse di ASP.NET Mobile Designer")) accanto alle varie proprietà nel **proprietà** finestra. Puntini di sospensione viene visualizzata anche come un IntelliSense dei messaggi di richiesta quando si assegnano valori a determinati attributi nel **origine** visualizzazione della finestra di progettazione.  
  
## <a name="uielement-list"></a>Elenco UIElement
 **Cartelle di progetto**  
 Viene visualizzato un elenco delle cartelle definite nel progetto o nel server locale in cui è in esecuzione SharePoint. Scegliere il pulsante di espansione per visualizzare le sottocartelle.  
  
 Espandere la **progetto** nodo per scegliere i file nel progetto. Deve essere visualizzato come selezionabili nella finestra di dialogo, i file del progetto devono soddisfare i criteri seguenti:  
  
-   Il file deve essere contenuto in una cartella mappata.  
  
-   Il file deve essere aggiunto al pacchetto della soluzione.  
  
-   Il file non può trovarsi in un altro progetto.  
  
 Se si desidera fare riferimento ai file che non soddisfano questi criteri, è necessario immettere manualmente il percorso del file.  
  
 Espandere la **Server** nodo per scegliere i file che si trovano nel server locale in cui è in esecuzione SharePoint. Deve essere visualizzato come selezionabili nella finestra di dialogo, questi file devono soddisfare i criteri seguenti:  
  
-   Il file deve trovarsi in uno dei seguenti cartelle mappate: **immagini**, **layout**, o **ControlTemplates**.  
  
-   Il file non può trovarsi nel database del contenuto di SharePoint.  
  
 Se si desidera fare riferimento ai file che non soddisfano questi criteri, è necessario immettere manualmente il percorso del file.  
  
 **Contenuto della cartella**  
 Consente di visualizzare un elenco di file contenuti nella cartella selezionata. Scegliere un file e quindi scegliere il **OK** pulsante per chiudere la finestra di dialogo e inviare la selezione al processo che lo ha chiamato.  
  
 **Tipo file**  
 Consente di scegliere da un elenco di file appropriati per l'attività in esecuzione.  
  
## <a name="see-also"></a>Vedere anche
 [Creare le pagine dell'applicazione per SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Creazione di web part per SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Creare controlli utente riutilizzabili per web part o pagine applicazione](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
  
