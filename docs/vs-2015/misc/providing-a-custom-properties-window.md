---
title: Specifica di una finestra delle proprietà personalizzate | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- property browsers, providing
- Properties window, providing your own
ms.assetid: 408dcdef-8ef9-4644-97d2-f311cd35824f
caps.latest.revision: 12
manager: douge
ms.openlocfilehash: 88ba48a4cf04d0ad5efb59939c57f021926dfd2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47518619"
---
# <a name="providing-a-custom-properties-window"></a>Specifica di una finestra Proprietà personalizzate
È possibile specificare il proprio **delle proprietà** finestra per un sistema di progetto specificato, anziché il **proprietà** finestra fornita dal [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ambiente di sviluppo integrato (IDE). Lo scenario più frequentemente si è verificato è quando si familiarità implementa l'oggetto individuato nella cornice della finestra.  
  
 Nel caso in cui si non implementa l'oggetto individuato nella cornice della finestra, ma è ancora possibile accedere a esso con altri mezzi, esistono diversi modi per accedere la <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> interfaccia come elencato nella procedura precedente in questa pagina.  
  
### <a name="to-provide-your-properties-window"></a>Per fornire la finestra proprietà  
  
1.  Definire un GUID che rappresenta il **proprietà** implementazione della finestra.  
  
2.  Nel <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implementazione, usare il <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> dichiarare il servizio di **proprietà** finestra come un servizio per l'ambiente di Visual Studio.  
  
### <a name="to-call-your-properties-window"></a>Per chiamare la finestra proprietà  
  
1.  Chiamare il metodo <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A>.  
  
2.  `QueryService` per <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> dal <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> passato il <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane.SetSite%2A> (metodo).  
  
3.  Ottenere <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx> da <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> servizio.  
  
4.  Chiamare <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx.OnElementValueChange%2A> con il primo parametro impostato su `SEID_PropertyBrowserSID` (ricavare il <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> enumerazione) e il terzo parametro, `varValue`, che rappresenta un formato di stringa del GUID che rappresenta il **proprietà** finestra. Effettuare la chiamata una sola volta al momento della prima creazione delle **proprietà** finestra documento. Dopo la chiamata ciò **proprietà** finestra è associata la cornice della finestra.  
  
### <a name="to-obtain-the-window-frame-object-when-you-are-not-the-implementer"></a>Per ottenere l'oggetto cornice di finestra quando non si è il responsabile dell'implementazione  
  
-   È possibile `QueryService` per <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx> servizio <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> con il parametro `propid` impostato su <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>.  
  
-   È possibile ottenere la finestra del documento attivo chiamando <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> tramite SVsMonitorSelection servizio. Impostare il parametro `elementid` al `SEID_WindowFrame`, eseguito dal <xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID> enumerazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Estensione delle proprietà](../extensibility/internals/extending-properties.md)   
 [Campi e interfacce della finestra Proprietà](../extensibility/internals/properties-window-fields-and-interfaces.md)