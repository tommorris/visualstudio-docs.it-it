---
title: Associare controlli WPF ai dati in Visual Studio - parte 1 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: e05a1e0c-5082-479d-bbc9-d395b0bc6580
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 87991e778a045aa86bca91ff737d528a55b0079f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281235"
---
# <a name="bind-wpf-controls-to-data-in-visual-studio"></a>Associare controlli WPF ai dati in Visual Studio

È possibile visualizzare i dati per gli utenti dell'applicazione mediante l'associazione dei dati ai controlli [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)]. Per creare questi controlli con associazione a dati, è possibile trascinare elementi dal **Zdroje dat** finestra nel [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)] in Visual Studio. In questo argomento vengono descritte alcune delle più comuni attività, strumenti e classi che è possibile utilizzare per creare applicazioni [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] associate a dati.

Per informazioni generali su come creare controlli associati a dati in Visual Studio, vedere [associare controlli ai dati in Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Per altre informazioni sulle [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] i dati di associazione, vedere [Cenni preliminari sull'associazione dati](/dotnet/framework/wpf/data/data-binding-overview).

## <a name="tasks-involved-in-binding-wpf-controls-to-data"></a>Attività coinvolte nell'associazione di controlli WPF ai dati

Nella tabella seguente sono elencate le attività che possono essere eseguite trascinando elementi dal **Zdroje dat** finestra di [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)].

|Attività|Altre informazioni|
|----------|----------------------|
|Creare nuovi controlli associati a dati.<br /><br /> Associare controlli esistenti a dati.|[Associare controlli WPF a un set di dati](../data-tools/bind-wpf-controls-to-a-dataset.md)|
|Creare controlli che visualizzano i dati correlati in una relazione padre-figlio: quando l'utente seleziona un record di dati padre in un controllo, un altro controllo visualizza i dati figlio correlati per il record selezionato.|[Visualizzare dati correlati in applicazioni WPF](../data-tools/display-related-data-in-wpf-applications.md)|
|Creare un *tabella di ricerca* che visualizza le informazioni da una tabella in base al valore di un campo di chiave esterna in un'altra tabella.|[Creare tabelle di ricerca in applicazioni WPF](../data-tools/create-lookup-tables-in-wpf-applications.md)|
|Associare un controllo a un'immagine di un database.|[Associare controlli alle immagini di un database](../data-tools/bind-controls-to-pictures-from-a-database.md)|

## <a name="valid-drop-targets"></a>Obiettivi di rilascio validi

È possibile trascinare gli elementi di **Zdroje dat** finestra solo per le destinazioni di rilascio validi nel [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)]. Esistono due tipi principali di obiettivi di rilascio validi: contenitori e controlli. Un contenitore è un elemento dell'interfaccia utente che in genere contiene i controlli. Una griglia e una finestra, ad esempio, sono contenitori.

## <a name="generated-xaml-and-code"></a>XAML e il codice generato

Quando si trascina un elemento dal **Zdroje dat** finestra per il [!INCLUDE[wpfdesigner_current_short](../data-tools/includes/wpfdesigner_current_short_md.md)], Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che definisce un nuovo controllo associato a dati (o associa un controllo esistente all'origine dati). Per alcune origini dati, Visual Studio genera il codice nel file code-behind che inserisce i dati nell'origine dati.

La tabella seguente elenca i [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] e il codice generato da Visual Studio per ogni tipo di origine dati nel **Zdroje dat** finestra.

|Origine dati|Generazione di XAML per l'associazione di un controllo all'origine dati|Generazione di codice per l'inserimento dei dati nell'origine dati|
|-----------------|-----------------------------------------------------------|--------------------------------------------------------|
|Set di dati|Yes|Yes|
|[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)]|Yes|Yes|
|Service|Yes|No|
|Object|Yes|No|

### <a name="datasets"></a>Dataset

Quando si trascina una tabella o una colonna dal **Zdroje dat** finestra di progettazione, Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che esegue le operazioni seguenti:

-   Aggiunge il dataset e un nuovo oggetto <xref:System.Windows.Data.CollectionViewSource> alle risorse del contenitore in cui è stato trascinato l'elemento. <xref:System.Windows.Data.CollectionViewSource> è un oggetto che può essere utilizzato per esplorare e visualizzare i dati nel dataset.

-   Crea un'associazione dati per un controllo. Se si trascina l'elemento in un controllo esistente della finestra di progettazione, XAML associa il controllo all'elemento. Se si trascina l'elemento in un contenitore, il XAML crea il controllo che è stato selezionato per l'elemento trascinato e associa il controllo all'elemento. Il controllo viene creato all'interno di un nuovo oggetto <xref:System.Windows.Controls.Grid>.

Visual Studio apporta inoltre le modifiche seguenti al file code-behind:

-   Crea un gestore dell'evento <xref:System.Windows.FrameworkElement.Loaded> per l'elemento [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] contenente il controllo. Il gestore dell'evento inserisce i dati nella tabella, recupera l'oggetto <xref:System.Windows.Data.CollectionViewSource> dalle risorse del contenitore, quindi imposta come elemento corrente il primo elemento di dati. Se un <xref:System.Windows.FrameworkElement.Loaded> gestore eventi esiste già, Visual Studio aggiunge questo codice al gestore dell'evento esistente.

### <a name="entity-data-models"></a>Entity data Model

Quando si trascina un'entità o una proprietà dell'entità dal **Zdroje dat** finestra di progettazione, Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che esegue le operazioni seguenti:

-   Aggiunge un nuovo oggetto <xref:System.Windows.Data.CollectionViewSource> alle risorse del contenitore in cui è stato trascinato l'elemento. <xref:System.Windows.Data.CollectionViewSource> è un oggetto che può essere utilizzato per esplorare e visualizzare i dati nell'entità.

-   Crea un data binding per un controllo. Se si trascina l'elemento in un controllo esistente della finestra di progettazione, [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] associa il controllo all'elemento. Se si trascina l'elemento in un contenitore, il [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] crea il controllo che è stato selezionato per l'elemento trascinato e associa il controllo all'elemento. Il controllo viene creato all'interno di un nuovo oggetto <xref:System.Windows.Controls.Grid>.

Visual Studio apporta inoltre le modifiche seguenti al file code-behind:

-   Aggiunge un nuovo metodo che restituisce una query per l'entità trascinata nella finestra di progettazione (o per l'entità contenente la proprietà trascinata nella finestra di progettazione). Il nuovo metodo con il nome `Get<EntityName>Query`, dove `\<EntityName>` è il nome dell'entità.

-   Crea un gestore dell'evento <xref:System.Windows.FrameworkElement.Loaded> per l'elemento [!INCLUDE[TLA2#tla_ui](../data-tools/includes/tla2sharptla_ui_md.md)] contenente il controllo. Chiamate del gestore eventi di `Get<EntityName>Query` per inserire l'entità di dati, che consente di recuperare il <xref:System.Windows.Data.CollectionViewSource> da risorse del contenitore, quindi rende i primo elemento di dati dell'elemento corrente. Se un <xref:System.Windows.FrameworkElement.Loaded> gestore eventi esiste già, Visual Studio aggiunge questo codice al gestore dell'evento esistente.

### <a name="services"></a>Servizi

Quando si trascina un oggetto servizio o a una proprietà di **Zdroje dat** finestra di progettazione, Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che crea un controllo con associazione a dati (o associa un controllo esistente all'oggetto o una proprietà). Tuttavia, Visual Studio genera il codice che compila l'oggetto servizio del proxy con i dati. È necessario scrivere questo codice manualmente. Per un esempio che illustra come eseguire questa operazione, vedere [WPF di associare controlli a un servizio dati WCF](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md).

Visual Studio genera XAML che esegue le operazioni seguenti:

-   Aggiunge un nuovo oggetto <xref:System.Windows.Data.CollectionViewSource> alle risorse del contenitore in cui è stato trascinato l'elemento. <xref:System.Windows.Data.CollectionViewSource> è un oggetto che può essere utilizzato per esplorare e visualizzare i dati nell'oggetto restituito dal servizio.

-   Crea un data binding per un controllo. Se si trascina l'elemento in un controllo esistente della finestra di progettazione, [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] associa il controllo all'elemento. Se si trascina l'elemento in un contenitore, il [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] crea il controllo che è stato selezionato per l'elemento trascinato e associa il controllo all'elemento. Il controllo viene creato all'interno di un nuovo oggetto <xref:System.Windows.Controls.Grid>.

### <a name="objects"></a>Oggetti

Quando si trascina un oggetto o a una proprietà di **Zdroje dat** finestra di progettazione, Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che crea un controllo con associazione a dati (o associa un controllo esistente all'oggetto o una proprietà). Tuttavia, Visual Studio non genera codice per inserire l'oggetto dati. È necessario scrivere questo codice manualmente.

> [!NOTE]
>  Devono essere pubblico e delle classi personalizzate, per impostazione predefinita, dispone di un costruttore senza parametri. Sono classi can'tbe annidati che hanno un "punto" nella relativa sintassi. Per altre informazioni, vedere [XAML e classi personalizzate per WPF](/dotnet/framework/wpf/advanced/xaml-and-custom-classes-for-wpf).

Visual Studio genera [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] che esegue le operazioni seguenti:

-   Aggiunge un nuovo oggetto <xref:System.Windows.Data.CollectionViewSource> alle risorse del contenitore in cui è stato trascinato l'elemento. <xref:System.Windows.Data.CollectionViewSource> è un oggetto che può essere utilizzato per esplorare e visualizzare i dati nell'oggetto.

-   Crea un data binding per un controllo. Se si trascina l'elemento in un controllo esistente della finestra di progettazione, XAML associa il controllo all'elemento. Se si trascina l'elemento in un contenitore, il XAML crea il controllo che è stato selezionato per l'elemento trascinato e associa il controllo all'elemento. Il controllo viene creato all'interno di un nuovo oggetto <xref:System.Windows.Controls.Grid>.

## <a name="see-also"></a>Vedere anche

- [Associare controlli ai dati in Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)