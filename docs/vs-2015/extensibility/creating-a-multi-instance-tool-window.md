---
title: Creazione di una finestra degli strumenti a istanza multipla | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca70aa6024f083cfff7de1e2ef687371eca44c8a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47527608"
---
# <a name="creating-a-multi-instance-tool-window"></a>Creazione di una finestra degli strumenti a istanze multiple
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [creazione di una finestra degli strumenti a più istanze](https://docs.microsoft.com/visualstudio/extensibility/creating-a-multi-instance-tool-window).  
  
È possibile programmare una finestra degli strumenti in modo che più istanze, sono possibile aprire contemporaneamente. Per impostazione predefinita, finestre degli strumenti possono avere una sola istanza aprire.  
  
 Quando si usa una finestra degli strumenti a istanza multipla, è possibile mostrare diverse fonti correlate di informazioni nello stesso momento. Ad esempio, è possibile inserire un multilinea <xref:System.Windows.Forms.TextBox> controllare in una finestra degli strumenti a istanza multipla, in modo che siano disponibili contemporaneamente diversi frammenti di codice durante una sessione di programmazione. Inoltre, ad esempio, è possibile inserire un <xref:System.Windows.Forms.DataGrid> casella controllo e un elenco di riepilogo a discesa in una finestra degli strumenti a istanza multipla, in modo che sia possibile rilevare numerose origini dati in tempo reale contemporaneamente.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Creazione di una finestra degli strumenti di base (a istanza singola)  
  
1.  Creare un progetto denominato **MultiInstanceToolWindow** usando il modello di progetto VSIX e aggiungere un modello di elemento di finestra degli strumenti personalizzata denominato **MIToolWindow**.  
  
    > [!NOTE]
    >  Per altre informazioni sulla creazione di un'estensione con una finestra degli strumenti, vedere [creazione di un'estensione con una finestra degli strumenti](../extensibility/creating-an-extension-with-a-tool-window.md).  
  
## <a name="making-a-tool-window-multi-instance"></a>Effettua multi-un'istanza di strumento  
  
1.  Aprire il **MIToolWindowPackage.cs** del file e trovare il `ProvideToolWindow` attributo. e `MultiInstances=true` parametro, come illustrato nell'esempio seguente.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  Nel file MIToolWindowCommand.cs, individuare il metodo ShowToolWindos(). In questo metodo, chiamare il <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> metodo e set relativo `create` flag `false` in modo che eseguirà l'iterazione attraverso le istanze di finestra degli strumenti esistenti finché non è disponibile un `id` viene trovato.  
  
3.  Per creare un'istanza di tool, chiamare il <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> metodo e set relativo `id` su un valore disponibile e la relativa `create` flag `true`.  
  
     Per impostazione predefinita, il valore della `id` parametro del <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> metodo è `0`. In questo modo una finestra degli strumenti a istanza singola. Per più di un'istanza deve essere ospitato, ogni istanza deve avere un proprio univoco `id`.  
  
4.  Chiamare il <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metodo sul <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> l'oggetto restituito dal <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> proprietà dell'istanza di finestra degli strumenti.  
  
5.  Per impostazione predefinita, il `ShowToolWindow` metodo creato dal modello di elemento di finestra degli strumenti crea una finestra degli strumenti a istanza singola. Nell'esempio seguente viene illustrato come modificare il `ShowToolWindow` metodo per creare più istanze.  
  
    ```csharp  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```

