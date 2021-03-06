---
title: Riferimento API per SDK di modellazione per Visual Studio
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7db208bf19f0a2433d4c85af7710a0f5ac70562e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947859"
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Riferimento API per SDK di modellazione per Visual Studio

Il Visual Studio SDK di visualizzazione e modellazione fornisce la piattaforma in cui vengono compilati gli strumenti di linguaggi specifici di dominio (DSL).

In questa sezione contiene materiale di riferimento per gli spazi dei nomi che presentano nomi che iniziano con "Microsoft.VisualStudio.Modeling".

|Spazio dei nomi|Content|
|---------------|-------------|
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|Classi, ad esempio ModelElement, ovvero la classe di base di tutte le classi di dominio che definiscono in un linguaggio DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|Classi che fanno parte di una definizione DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|Gli strumenti di misurazione Visualizzatore archivio e le prestazioni del modello.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|Classi, ad esempio ShapeElement, ovvero la classe di base di tutte le forme definite in un linguaggio DSL.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|Metodi di azione e la selezione.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|L'API della finestra di progettazione definizione DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|Classi interne della finestra di progettazione definizione DSL.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|Attributi che consentono di estendere la finestra di progettazione DSL con comandi, movimenti e convalida.|
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|Metodi di estensione per l'oggetto ModelElement che implementano l'estendibilità DSL.|
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|Attributi di estendibilità|
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|Consente di rendere le parti di un modello di sola lettura.|
|<xref:Microsoft.VisualStudio.Modeling.Integration?displayProperty=fullName>|L'API Modelbus, che consente di integrare modelli diversi.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker?displayProperty=fullName>|Nella finestra di dialogo che consente agli utenti di esplorare i modelli e gli elementi per creare riferimenti Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting?displayProperty=fullName>|Il servizio di selezione.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell?displayProperty=fullName>|Framework di adapter ModelBus di Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Integration.Shell.Picker?displayProperty=fullName>|La finestra di dialogo di selezione che consente agli utenti di esplorare i modelli e gli elementi per creare riferimenti Modelbus.|
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|L'interfaccia tra DSL e Visual Studio.|
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|Consente di definire i comandi di menu di scelta rapida (contestuale).|
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|Consente di definire vincoli di convalida.|

## <a name="see-also"></a>Vedere anche

- [Personalizzazione della trasformazione del testo T4](../modeling/customizing-t4-text-transformation.md)
