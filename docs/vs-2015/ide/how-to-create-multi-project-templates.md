---
title: 'Procedura: Creare modelli per più progetti | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio templates, creating multi-project templates
- project templates, creating multi-project templates
- multi-project templates
ms.assetid: 8c7f7065-137e-40ad-868d-37e007270efd
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ce7147df5b15dd6aaa639c27b2d2ffbc0b3d3152
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2018
ms.locfileid: "47518820"
---
# <a name="how-to-create-multi-project-templates"></a>Procedura: creare modelli basati su più progetti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [procedura: creare modelli multiprogetto](https://docs.microsoft.com/visualstudio/ide/how-to-create-multi-project-templates).  
  
I modelli multiprogetto fungono da contenitori per due o più progetti. Quando un progetto basato su un modello per più progetti viene creato nella finestra di dialogo **Nuovo progetto**, ogni progetto del modello viene aggiunto alla soluzione.  
  
 Un modello per più progetti deve includere gli elementi seguenti, compressi in un file con estensione zip:  
  
-   Un file radice con estensione vstemplate per l'intero modello per più progetti. Il file con estensione vstemplate contiene i metadati visualizzati dalla finestra di dialogo **Nuovo progetto** e specifica la posizione dei file con estensione vstemplate per i progetti del modello. Questo file deve trovarsi nella radice del file con estensione zip.  
  
-   Una o più cartelle che contengono i file necessari per un modello di progetto completo. Sono inclusi tutti i file di codice per il progetto e un file con estensione vstemplate per il progetto.  
  
 Ad esempio, il file con estensione zip di un modello per più progetti con due progetti può includere i file e le directory seguenti:  
  
 MultiProjectTemplate.vstemplate  
  
 \Project1\Project1.vstemplate  
  
 \Project1\Project1.vbproj  
  
 \Project1\Class.vb  
  
 \Project2\Project2.vstemplate  
  
 \Project2\Project2.vbproj  
  
 \Project2\Class.vb  
  
 Il file radice con estensione vstemplate per un modello per più progetti differisce da un modello per progetto singolo nei modi seguenti:  
  
-   L'attributo `Type` dell'elemento `VSTemplate` contiene il valore `ProjectGroup`. Ad esempio:  
  
    ```  
    <VSTemplate Version="2.0.0" Type="ProjectGroup"  
        xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    ```  
  
-   L'elemento `TemplateContent` contiene un elemento `ProjectCollection` che ha uno o più elementi `ProjectTemplateLink` che definiscono i percorsi dei file con estensione vstemplate dei progetti inclusi. Ad esempio:  
  
    ```  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink>  
                Project1\Project1.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink>  
                Project2\Project2.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
    ```  
  
 I modelli per più progetti si differenziano dai modelli normali anche nel comportamento. I modelli per più progetti presentano le caratteristiche specifiche seguenti:  
  
-   Non è possibile assegnare nomi ai singoli progetti di un modello per più progetti tramite la finestra di dialogo **Nuovo progetto**. Usare l'attributo `ProjectName` nell'elemento `ProjectTemplateLink` per specificare il nome di ogni progetto. Per altre informazioni, vedere il primo esempio della sezione seguente.  
  
-   I modelli per più progetti possono contenere progetti scritti in linguaggi diversi, ma l'intero modello può essere inserito in una sola categoria usando l'elemento `ProjectType`.  
  
### <a name="to-create-a-multi-project-template"></a>Per creare un modello per più progetti  
  
1.  Creare i progetti da includere nel modello per più progetti.  
  
2.  Creare i file con estensione vstemplate per ogni progetto. Per altre informazioni, vedere [Procedura: Creare modelli di progetto](../ide/how-to-create-project-templates.md).  
  
3.  Creare un file radice con estensione vstemplate per i metadati del modello per più progetti. Per altre informazioni, vedere il primo esempio della sezione seguente.  
  
4.  Selezionare i file e le cartelle da includere nel modello, fare clic con il pulsante destro del mouse sulla selezione, scegliere **Invia a** e quindi **Cartella compressa**. I file e le cartelle vengono compressi in un file con estensione zip.  
  
5.  Inserire il file di modello con estensione zip nella directory dei modelli di progetto [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Per impostazione predefinita, la directory è \Documenti\Visual Studio *Versione*\Templates\ProjectTemplates\\.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra un file radice con estensione vstemplate per più progetti. In questo esempio, il modello contiene due progetti `My Windows Application` e `My Class Library`. L'attributo `ProjectName` nell'elemento `ProjectTemplateLink` imposta il nome per [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] da assegnare a questo progetto. Se l'attributo `ProjectName` non esiste, per il nome del progetto verrà usato il nome del file .vstemplate.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="example"></a>Esempio  
 Questo esempio usa l'elemento `SolutionFolder` per dividere i progetti in due gruppi, `Math Classes` e `Graphics Classes`. Il modello contiene quattro progetti, due dei quali vengono inseriti in ogni cartella della soluzione.  
  
```  
<VSTemplate Version="2.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <SolutionFolder Name="Math Classes">  
                <ProjectTemplateLink ProjectName="MathClassLib1">  
                    MathClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="MathClassLib2">  
                    MathClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
            <SolutionFolder Name="Graphics Classes">  
                <ProjectTemplateLink ProjectName="GraphicsClassLib1">  
                    GraphicsClassLib1\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
                <ProjectTemplateLink ProjectName="GraphicsClassLib2">  
                    GraphicsClassLib2\MyTemplate.vstemplate  
                </ProjectTemplateLink>  
            </SolutionFolder>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di modelli di progetti e di elementi](../ide/creating-project-and-item-templates.md)   
 [Riferimenti allo schema dei modelli di Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Procedura: Creare modelli di progetto](../ide/how-to-create-project-templates.md)   
 [Riferimenti allo schema dei modelli di Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Elemento SolutionFolder (modelli di Visual Studio)](../extensibility/solutionfolder-element-visual-studio-templates.md)   
 [Elemento ProjectTemplateLink (modelli di Visual Studio)](../extensibility/projecttemplatelink-element-visual-studio-templates.md)



