---
title: Attività WriteCodeFragment | Microsoft Docs
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
- MSBuild, WriteCodeFragment task
- WriteCodeFragment task [MSBuild]
ms.assetid: 1d2514b4-5bef-43bb-bebe-496da8ef063c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6246c66299bb713c8b024feefa12eb883e2c0c76
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231093"
---
# <a name="writecodefragment-task"></a>Attività WriteCodeFragment
Genera un file di codice temporaneo usando il frammento di codice generato specificato. Non elimina il file.  
  
## <a name="parameters"></a>Parametri  
 Nella tabella che segue vengono descritti i parametri dell'attività `WriteCodeFragment` .  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|`AssemblyAttributes`|Parametro <xref:Microsoft.Build.Framework.ITaskItem>`[]` facoltativo.<br /><br /> Descrizione degli attributi da scrivere. Il valore dell'elemento `Include` è il nome completo del tipo dell'attributo, ad esempio, "System.AssemblyVersionAttribute".<br /><br /> Ogni tipo di metadati è la coppia nome-valore di un parametro, che deve essere di tipo `String`. Alcuni attributi consentono solo gli argomenti posizionali del costruttore. Tuttavia, è possibile usare tali argomenti in qualsiasi attributo. Per impostare gli attributi posizionali del costruttore, usare nomi di metadati simili a "_Parameter1","_Parameter2" e così via.<br /><br /> L'indice del parametro non può essere ignorato.|  
|`Language`|Parametro `String` obbligatorio.<br /><br /> Specifica il linguaggio del codice da generare.<br /><br /> `Language` può essere qualsiasi linguaggio per cui è disponibile un CodeDOM, ad esempio "C#" o "VisualBasic". Il file generato avrà l'estensione predefinita per tale linguaggio.|  
|`OutputDirectory`|Parametro <xref:Microsoft.Build.Framework.ITaskItem> facoltativo.<br /><br /> Specifica la cartella di destinazione per il codice generato, di solito la cartella intermedia.|  
|`OutputFile`|Parametro di ouput facoltativo <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Specifica il percorso del file generato. Se questo parametro viene impostato usando un nome di file, la cartella di destinazione viene anteposta al nome del file. Se viene impostato usando una radice, la cartella di destinazione viene ignorata.<br /><br /> Se questo parametro non viene impostato, il nome del file di output è la cartella di destinazione, un nome di file arbitrario e l'estensione del file predefinita per il linguaggio specificato.|  
  
## <a name="remarks"></a>Note  
 Oltre a usare i parametri elencati nella tabella, questa attività eredita i parametri dalla classe <xref:Microsoft.Build.Tasks.TaskExtension> che a sua volta eredita dalla classe <xref:Microsoft.Build.Utilities.Task>. Per un elenco di questi parametri aggiuntivi e le rispettive descrizioni, vedere [Classe di base TaskExtension](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Attività](../msbuild/msbuild-tasks.md)   
 [Riferimenti delle attività MSBuild](../msbuild/msbuild-task-reference.md)