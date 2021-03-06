---
title: Direttiva include T4
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: d9278d85349ede7ea5f44dce589d6737b64bc83e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952929"
---
# <a name="t4-include-directive"></a>Direttiva include T4

In un modello di testo di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], è possibile includere testo da un altro file tramite una direttiva `<#@include#>`. È possibile inserire le direttive `include` ovunque all'interno di un modello di testo prima del primo blocco della funzionalità di classe `<#+ ... #>`. I file inclusi possono contenere anche direttive `include` e altre direttive. Questo consente all'utente di condividere un codice del modello e un boilerplate tra modelli.

## <a name="using-include-directives"></a>Utilizzo delle direttive Include

```
<#@ include file="filePath" [once="true"] #>
```

-   `filePath` possono essere assoluti o relativi al file modello corrente.

     Inoltre, le estensioni specifiche di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] possono specificare le proprie directory per cercare i file di inclusione. Ad esempio, dopo aver installato il SDK di visualizzazione e modellazione (strumenti DSL), la cartella seguente viene aggiunto all'elenco di inclusione: `Program Files\Microsoft Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates`.

     Queste cartelle di inclusione aggiuntive potrebbero dipendere dall'estensione del file incluso. Ad esempio, la cartella di inclusione di Strumenti DSL è accessibile soltanto ai file inclusi con l'estensione `.tt`

-   `filePath` può includere le variabili di ambiente delimitate da "%". Ad esempio:

    ```
    <#@ include file="%HOMEPATH%\MyIncludeFile.t4" #>
    ```

-   Il nome di un file incluso non deve utilizzare l'estensione `".tt"`.

     È possibile utilizzare un'altra estensione, quale `".t4"` per i file inclusi. Questo avviene perché, quando si aggiunge un `.tt` file a un progetto, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] imposta automaticamente la **lo strumento personalizzato** proprietà `TextTemplatingFileGenerator`. Non è in genere consigliabile che i file inclusi vengano trasformati singolarmente.

     D'altra parte, occorre tener presente che in alcuni casi, l'estensione di file determina in quali cartelle aggiuntive verranno cercati i file di inclusione. Questo potrebbe essere importante quando si dispone di un file incluso che include altri file.

-   Il contenuto incluso viene elaborato più o meno come se facesse parte del modello di testo che include. Tuttavia, è possibile includere un file che contiene un blocco della funzionalità di classe `<#+...#>` anche se la direttiva `include` è seguita da testo ordinario e blocchi di controllo standard.

-   Utilizzare `once="true"` per garantire che un modello sia incluso una sola volta, anche se viene chiamato da più di un file di inclusione.

     Rende questa funzionalità è più facile creare una libreria di frammenti di codice T4 riutilizzabile che è possibile includere in verrà senza doversi preoccupare che alcuni altri frammento ha già incluse.  Si supponga, ad esempio, che si dispone di una raccolta di frammenti di codice specifici che gestiscono l'elaborazione di modello e la generazione di c#.  Che a sua volta, vengono utilizzati da alcune utilità di più attività specifiche, ad esempio la generazione di eccezioni, è quindi possibile utilizzare qualsiasi modello più specifici dell'applicazione. Se si crea il grafico dipendenze, si noterà che alcuni frammenti verranno inclusi più volte. Ma il parametro `once` impedisce le inclusioni successive.

 **MyTextTemplate.tt:**

```
<#@ output extension=".txt" #>
Output message 1 (from top template).
<#@ include file="TextFile1.t4"#>
Output message 5 (from top template).
<#
   GenerateMessage(6); // defined in TextFile1.t4
   AnotherGenerateMessage(7); // defined in TextFile2.t4
#>

```

 **TextFile1.t4:**

```
   Output Message 2 (from included file).
<#@include file="TextFile2.t4" #>
   Output Message 4 (from included file).
<#+ // Start of class feature control block.
void GenerateMessage(int n)
{
#>
   Output Message <#= n #> (from GenerateMessage method).
<#+
}
#>

```

 **TextFile2.t4:**

```
        Output Message 3 (from included file 2).
<#+ // Start of class feature control block.
void AnotherGenerateMessage(int n)
{
#>
       Output Message <#= n #> (from AnotherGenerateMessage method).
<#+
}
#>

```

 **Il file generato risultante, MyTextTemplate. txt:**

```
Output message 1 (from top template).
   Output Message 2 (from included file).
        Output Message 3 (from included file 2).

   Output Message 4 (from included file).

Output message 5 (from top template).
   Output Message 6 (from GenerateMessage method).
       Output Message 7 (from AnotherGenerateMessage method).

```

##  <a name="msbuild"></a> Utilizzo delle proprietà di progetto in MSBuild e Visual Studio
 Sebbene sia possibile usare macro di Visual Studio, ad esempio $ (SolutionDir) in una direttiva include, non funzionano in MSBuild. Se si desidera trasformare i modelli nel computer di compilazione, è necessario utilizzare le proprietà del progetto.

 Modificare il file con estensione csproj o vbproj per definire una proprietà del progetto. In questo esempio viene definita una proprietà denominata `myIncludeFolder`:

```xml
<!-- Define a project property, myIncludeFolder: -->
<PropertyGroup>
    <myIncludeFolder>$(MSBuildProjectDirectory)\..\libs</myIncludeFolder>
</PropertyGroup>

<!-- Tell the MSBuild T4 task to make the property available: -->
<ItemGroup>
    <T4ParameterValues Include="myIncludeFolder">
      <Value>$(myIncludeFolder)</Value>
    </T4ParameterValues>
  </ItemGroup>

```

 È ora possibile utilizzare la proprietà del progetto nei modelli di testo, che si convertono correttamente in Visual Studio e in MSBuild:

```
<#@ include file="$(myIncludeFolder)\defs.tt" #>
```