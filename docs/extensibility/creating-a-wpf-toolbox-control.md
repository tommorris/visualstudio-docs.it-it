---
title: Creazione di un controllo della casella degli strumenti WPF | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- toolbox control
- toolbox
- wpf
ms.assetid: 9cc34db9-b0d1-4951-a02f-7537fbbb51ad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 43734720a4e86f9f1e214285df1873b39b67fa01
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500332"
---
# <a name="create-a-wpf-toolbox-control"></a>Creare un controllo della casella degli strumenti WPF
Il modello di controllo della casella degli strumenti WPF (Windows Presentation Framework) consente di creare controlli WPF che vengono aggiunti automaticamente per il **casella degli strumenti** quando l'estensione viene installata. Questo argomento illustra come usare il modello per creare un **casella degli strumenti** controllo che è possibile distribuire ad altri utenti.  
  
 A partire da Visual Studio 2015, non installare Visual Studio SDK dall'area download. È incluso come funzionalità facoltativa nel programma di installazione di Visual Studio. È anche possibile installare il SDK di Visual Studio in un secondo momento. Per altre informazioni, vedere [installare Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="create-a-wpf-toolbox-control"></a>Creare un controllo della casella degli strumenti WPF  
  
### <a name="create-an-extension-with-a-wpf-toolbox-control"></a>Creare un'estensione con un controllo della casella degli strumenti WPF  
  
1.  Creare un progetto VSIX denominato `MyToolboxControl`. È possibile trovare il modello di progetto VSIX nel **nuovo progetto** nella finestra di dialogo **Visual c#** > **estendibilità**.  
  
2.  Quando si apre il progetto, aggiungere un **controllo della casella degli strumenti WPF** modello di elemento denominato `MyToolboxControl`. Nel **Esplora soluzioni**, fare doppio clic sul nodo del progetto e selezionare **Add** > **nuovo elemento**. Nel **Aggiungi nuovo elemento** finestra di dialogo passa alla **Visual c#** > **Extensibility** e selezionare **controllo della casella degli strumenti WPF**. Nel **Name** campo nella parte inferiore della finestra, modificare il nome di file di comando da *MyToolboxControl.cs*.  
  
     La soluzione ora contiene un controllo utente, un `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> che aggiunge il controllo per il **della casella degli strumenti**e un **Microsoft.VisualStudio.ToolboxControl** voce di risorsa nel manifesto VSIX per  distribuzione.  
  
#### <a name="to-create-the-control-ui"></a>Creare l'interfaccia utente del controllo  
  
1.  Aprire *MyToolboxControl.xaml* nella finestra di progettazione.  
  
     La finestra di progettazione Mostra un' <xref:System.Windows.Controls.Grid> controllo contenente un <xref:System.Windows.Controls.Button> controllo.  
  
2.  Definire il layout di griglia. Quando si seleziona il <xref:System.Windows.Controls.Grid> controllare, sui bordi superiore e sinistro della griglia vengono visualizzate le barre di controllo blu. È possibile aggiungere righe e colonne nella griglia facendo clic sulle barre.  
  
3.  Aggiungere i controlli figlio nella griglia. È possibile posizionare un controllo figlio trascinandolo dal **della casella degli strumenti** a una sezione della griglia, oppure tramite l'impostazione relativa `Grid.Row` e `Grid.Column` gli attributi nel XAML. L'esempio seguente aggiunge due etichette nella parte superiore della griglia e un pulsante sulla seconda riga.  
  
    ```xaml  
    <Grid>  
        <Label Grid.Row="0" Grid.Column="0" Name="label1" />  
        <Label Grid.Row="0" Grid.Column="1" Name="label2" />  
        <Button Name="button1" Click="button1_Click" Grid.Row="1" Grid.ColumnSpan="2" />  
    </Grid>  
    ```  
  
## <a name="renaming-the-control"></a>Ridenominazione del controllo  
 Per impostazione predefinita, il controllo verrà visualizzato nei **casella degli strumenti** come **MyToolboxControl** in un gruppo denominato **MyToolboxControl.MyToolboxControl**. È possibile modificare questi nomi nel *MyToolboxControl.xaml.cs* file.  
  
1.  Aprire *MyToolboxControl.xaml.cs* nella visualizzazione codice.  
  
2.  Trovare il `MyToolboxControl` classe e rinominarla in TestControl. (Il modo più rapido per eseguire questa operazione consiste nel rinominare la classe, quindi selezionare **Rinomina** dal menu di scelta rapida e completare i passaggi. (Per ulteriori informazioni sul **rinominare** comando, vedere [rinominare refactoring (c#)](../ide/reference/rename.md).)
  
3.  Andare alla `ProvideToolboxControl` dell'attributo e modificare il valore del primo parametro a **Test**. Si tratta del nome del gruppo che contiene il controllo nel **casella degli strumenti**.  
  
     Il codice risultante dovrebbe essere simile al seguente:  
  
    ```csharp  
    [ProvideToolboxControl("Test", true)]  
    public partial class TestControl : UserControl  
    {  
        public TestControl()  
        {  
            InitializeComponent();  
        }  
    }  
    ```  
  
## <a name="build-test-and-deployment"></a>Compilazione, Test e distribuzione  
 Quando si esegue il debug del progetto, è necessario trovare il controllo installato nella **casella degli strumenti** dell'istanza sperimentale di Visual Studio.  
  
### <a name="to-build-and-test-the-control"></a>Per compilare e testare il controllo  
  
1.  Ricompilare il progetto e avviare il debug.  
  
2.  Nella nuova istanza di Visual Studio creare un progetto di applicazione WPF. Verificare che sia aperta la finestra di progettazione XAML.  
  
3.  Individuare il controllo nella **casella degli strumenti** e trascinarlo nell'area di progettazione.  
  
4.  Avviare il debug dell'applicazione WPF.  
  
5.  Verificare che venga visualizzato il controllo.  
  
### <a name="to-deploy-the-control"></a>Per distribuire il controllo  
  
1.  Dopo aver compilato il progetto testato, è possibile trovare il *VSIX* del file nei * \bin\debug\* cartella del progetto.  
  
2.  È possibile installarlo in un computer locale facendo doppio clic il *VSIX* file e seguire la procedura di installazione. Per disinstallare il controllo, andare a **degli strumenti** > **estensioni e aggiornamenti** e cercare l'estensione di controllo, quindi fare clic su **Disinstalla**.  
  
3.  Caricare il *VSIX* file in una rete o a un sito Web.  
  
     Se si carica il file per il [Visual Studio gallery](http://go.microsoft.com/fwlink/?LinkID=123847) sito Web, gli altri utenti possono usare **Tools** > **estensioni e aggiornamenti** in Visual Studio per trovare il controllo online e installarlo.