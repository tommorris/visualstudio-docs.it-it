---
title: Attività ResourcesGenerator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b72ce231b514250a40e9f3a4bf5ceb5aa2c69f8
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178891"
---
# <a name="resourcesgenerator-task"></a>Attività ResourcesGenerator
L'attività <xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> incorpora una o più risorse (con estensione *jpg*, *ico*, *bmp*, [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] in formato binario e altri tipi di estensione) in un file con estensione *resources*.  
  
## <a name="task-parameters"></a>Parametri dell'attività  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`OutputPath`|Parametro **String** obbligatorio.<br /><br /> Specifica il percorso della directory di output. Se il percorso non è assoluto, verrà trattato come percorso relativo alla directory di progetto radice.|  
|`OutputResourcesFile`|Parametro di output **ITaskItem[]** obbligatorio.<br /><br /> Specifica il percorso e il nome del file con estensione *resources* generato. Se il percorso non è assoluto, il file  *resources* verrà generato come percorso relativo alla directory di progetto radice.|  
|`ResourcesFiles`|Parametro **ITaskItem[]** obbligatorio.<br /><br /> Specifica una o più risorse da incorporare nel file con estensione *resources* generato.|  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come generare un file con estensione *resources* con una sola risorsa con estensione *bmp*. La risorsa con estensione *bmp* viene generata in una directory relativa alla directory radice del progetto.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di riferimento su MSBuild WPF](../msbuild/wpf-msbuild-reference.md)   
 [Riferimenti delle attività MSBuild](../msbuild/wpf-msbuild-task-reference.md)   
 [Informazioni di riferimento su MSBuild](../msbuild/msbuild-reference.md)   
 [Attività MSBuild](../msbuild/msbuild-task-reference.md)   
 [Creazione di un'applicazione WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)