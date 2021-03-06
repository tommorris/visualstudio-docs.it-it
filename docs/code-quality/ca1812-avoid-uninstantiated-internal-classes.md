---
title: 'CA1812: Evitare classi interne prive di istanze'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68597c0748fbc235178da6b6e583c48b9f1b422f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551769"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: Evitare classi interne prive di istanze
|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|Category|Microsoft.Performance|
|Modifica importante|Non sostanziale|

## <a name="cause"></a>Causa
 Un'istanza di un tipo a livello di assembly non viene creata dal codice nell'assembly.

## <a name="rule-description"></a>Descrizione della regola
 Questa regola cerca di individuare una chiamata a uno dei costruttori del tipo e se viene trovata alcuna chiamata viene segnalata una violazione.

 I tipi seguenti non vengono analizzati da questa regola:

- Tipi valore

- Tipi astratti

- Enumerazioni

- Delegati

- Tipi di matrice emesso dal compilatore

- I tipi che non può essere inizializzata e che definiscono `static` (`Shared` in Visual Basic) solo i metodi.

 Se si applicano <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> all'assembly che si sta analizzando, questa regola non verrà eseguita su qualsiasi costruttore contrassegnati come `internal` poiché non è possibile stabilire se un campo viene usato da un altro `friend` assembly.

 Anche se è possibile aggirare questa limitazione in analisi di codice di Visual Studio, FxCop autonomo esterno si verificherà in costruttori interni se ogni `friend` assembly è presente nell'analisi.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, rimuovere il tipo o aggiungere il codice che lo utilizza. Se il tipo contiene solo i metodi statici, aggiungere uno dei valori seguenti per il tipo per impedire al compilatore di creazione di un costruttore di istanza pubblici predefinito:

- Un costruttore privato per i tipi che hanno come destinazione [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] versioni 1.0 e 1.1.

- Il `static` (`Shared` in Visual Basic) che hanno come destinazione i tipi di modificatore per [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 È possibile eliminare un avviso da questa regola. Si consiglia di eliminare l'avviso nelle situazioni seguenti:

- La classe viene creata tramite i metodi di reflection con associazione tardiva, ad esempio <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>.

- La classe viene creata automaticamente dal runtime o [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]. Ad esempio, le classi che implementano <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> o <xref:System.Web.IHttpHandler?displayProperty=fullName>.

- La classe viene passata come parametro di tipo generico che ha un nuovo vincolo. Nell'esempio seguente genera ad esempio, questa regola.

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }
    // [...]
    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

 In questi casi, si consiglia che non visualizzare questo avviso.

## <a name="related-rules"></a>Regole correlate
 [CA1811: Evitare il codice privato non chiamato](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1801: Rivedere i parametri non usati](../code-quality/ca1801-review-unused-parameters.md)

 [CA1804: Rimuovere locali non usati](../code-quality/ca1804-remove-unused-locals.md)