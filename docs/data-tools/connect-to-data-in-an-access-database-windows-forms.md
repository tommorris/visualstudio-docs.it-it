---
title: Connettersi ai dati in un database di Access (Windows Form)
ms.date: 09/15/2017
ms.topic: conceptual
helpviewer_keywords:
- databases, connecting to
- databases, Access
- data [Visual Studio], connecting
- connecting to data, from Access databases
- Access databases, connecting
ms.assetid: 4159e815-d430-4ad0-a234-e4125fcbef18
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: f1d0b5d2d0391d401394929e16d5bfc97aa6d555
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282639"
---
# <a name="connect-to-data-in-an-access-database-windows-forms"></a>Connettersi ai dati in un database di Access (Windows Form)
È possibile connettersi a un database Access (entrambi un *mdf* file o un' *accdb* file) con Visual Studio. Dopo aver definito la connessione, i dati vengono visualizzati nei **Zdroje dat** finestra. da cui è possibile trascinare tabelle o visualizzazioni nei form.

## <a name="prerequisites"></a>Prerequisiti
 Per usare queste procedure, è necessario un progetto di applicazione Windows Forms e un database di Access (*accdb* file) o da un database Access 2000-2003 (*mdb* file). Attenersi alla procedura che corrisponde al tipo di file utilizzato.

## <a name="creating-the-dataset-for-an-accdb-file"></a>Creazione di set di dati per un file con estensione accdb
 È possibile connettersi a database creati tramite Access 2013, Office 365, Access 2010 o Access 2007 tramite la procedura seguente.

#### <a name="to-create-the-dataset"></a>Per creare il dataset

1.  Aprire l'applicazione Windows Form a cui si desidera connettere i dati.

2.  Nel **View** dal menu **Other Windows** > **Zdroje dat**.

     ![Visualizza, Altre finestre, Origini dati](../data-tools/media/viewdatasources.png)

3.  Nella finestra **Origini dati** fare clic su **Aggiungi nuova origine dati**.

     Il **configurazione guidata origine dati** apre.

4.  Selezionare **Database** nel **scegliere un tipo di origine dati** pagina e quindi selezionare **Next**.

5.  Selezionare **set di dati** nel **scegliere un modello di Database** pagina e quindi selezionare **Next**.

6.  Nel **scegliere la connessione dati** pagina, selezionare **nuova connessione** per configurare una nuova connessione dati.

     Il **Aggiungi connessione** verrà visualizzata la finestra di dialogo.

7.  Selezionare il **Change** accanto alle **zdroj dat** casella di testo.

     Il **Modifica origine dati** verrà visualizzata la finestra di dialogo.

8.  Nell'elenco delle origini dati, scegliere  **\<altri\>**. Nel **provider di dati** elenco a discesa, selezionare **Provider di dati .NET Framework per OLE DB**, quindi scegliere **OK**.

9. Nel **Aggiungi connessione** finestra di dialogo **Office 12.0 Access Database Engine Provider Microsoft OLE DB** dal **Provider OLE DB** elenco a discesa.

     ![Provider OLE DB Microsoft Office 12.0 Access](../data-tools/media/dataoledbprovideroffice12access.png)

     > [!NOTE]
     >  Se non viene visualizzata **Microsoft Office 12.0 Access Database Engine Provider OLE DB** nell'elenco a discesa il provider OLE DB, si potrebbe essere necessario installare il [driver di Office system 2007: componenti di connettività dati](https://www.microsoft.com/download/confirmation.aspx?id=23734).

9. Nel **Server o nel nome file** casella di testo, specificare il percorso e il nome del file le *accdb* file che si desidera connettersi a e quindi selezionare **OK**. (Se il file di database ha un nome utente e password, specificarli e si seleziona **OK**.)

10. Selezionare **successivo** nel **scegliere la connessione dati** pagina.

     È possibile ricevere una finestra di dialogo indicante che il file di dati non è presente nel progetto corrente. Selezionare **Sì** o **No**.

11. Selezionare **successivo** nel **Salva stringa di connessione nel file di configurazione dell'applicazione** pagina.

12. Espandere la **tabelle** nodo il **Scegli oggetti di Database** pagina.

13. Selezionare le tabelle o viste desiderato nel set di dati e quindi selezionare **fine**.

     Il set di dati viene aggiunto al progetto e le tabelle e viste vengono visualizzati nei **Zdroje dat** finestra.

## <a name="create-the-dataset-for-an-mdb-file"></a>Creare il set di dati per un file con estensione mdb
 Creare il set di dati eseguendo il **configurazione guidata origine dati**.

#### <a name="to-create-the-dataset"></a>Per creare il dataset

1.  Aprire l'applicazione Windows Form a cui si desidera connettere i dati.

2.  Nel **View** dal menu **Other Windows** > **Zdroje dat**.

     ![Visualizza, Altre finestre, Origini dati](../data-tools/media/viewdatasources.png)

3.  Nella finestra **Origini dati** fare clic su **Aggiungi nuova origine dati**.

     Il **configurazione guidata origine dati** apre.

4.  Selezionare **Database** nel **scegliere un tipo di origine dati** pagina e quindi selezionare **Next**.

5.  Selezionare **set di dati** nel **scegliere un modello di Database** pagina e quindi selezionare **Next**.

6.  Nel **scegliere la connessione dati** pagina, selezionare **nuova connessione** per configurare una nuova connessione dati.

7.  Se l'origine dati non è **File di Database Microsoft Access (OLE DB)**, selezionare **Change** per aprire il **Modifica origine dati** nella finestra di dialogo e selezionare **Microsoft Accedere al File di Database**, quindi selezionare **OK**.

8.  Nel **nome file del Database**, specificare il percorso e nome del *mdb* file che si desidera connettersi a e quindi selezionare **OK**.

     ![Aggiunta della connessione al file di database di Access](../data-tools/media/dataaddconnectionaccessmdb.png)

9. Selezionare **successivo** nel **scegliere la connessione dati** pagina.

10. Selezionare **successivo** nel **Salva stringa di connessione nel file di configurazione dell'applicazione** pagina.

11. Espandere la **tabelle** nodo il **Scegli oggetti di Database** pagina.

12. Selezionare le tabelle o viste desiderato nel set di dati e quindi selezionare **fine**.

     Il set di dati viene aggiunto al progetto e le tabelle e viste vengono visualizzati nei **Zdroje dat** finestra.

## <a name="security"></a>Sicurezza
 L'archiviazione di informazioni riservate, ad esempio una password, può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [proteggono le informazioni di connessione](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="next-steps"></a>Passaggi successivi
 Il set di dati appena creato è ora disponibile nel **Zdroje dat** finestra. È ora possibile eseguire le attività seguenti:

-   Selezionare gli elementi nel **Zdroje dat** finestra e trascinarli nel form (vedere [controlla Binding Windows Forms ai dati in Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)).

-   Aprire l'origine dati nel **Progettazione Dataset** per aggiungere o modificare gli oggetti che costituiscono il set di dati.

-   Aggiungere logica di convalida per il <xref:System.Data.DataTable.ColumnChanging> oppure <xref:System.Data.DataTable.RowChanging> evento delle tabelle di dati nel set di dati (vedere [convalidare i dati nei set di dati](../data-tools/validate-data-in-datasets.md)).

## <a name="see-also"></a>Vedere anche

- [Aggiungere connessioni](../data-tools/add-new-connections.md)