---
title: 'CA1819: Le proprietà non devono restituire matrici'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 68f64d37a7616f095a86452353edc498d2d27f28
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549417"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Le proprietà non devono restituire matrici

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Category|Microsoft.Performance|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Una proprietà pubblica o protetta in un tipo pubblico restituisce una matrice.

## <a name="rule-description"></a>Descrizione della regola
 Le matrici restituite dalle proprietà non sono protette in scrittura, anche se la proprietà è di sola lettura. Affinché la matrice sia protetta da eventuali alterazioni, la proprietà deve restituire una copia della matrice. In genere, gli utenti non comprendono le implicazioni negative sulle prestazioni derivanti dalla chiamata di tale proprietà. In particolare, si potrebbe usare la proprietà come una proprietà indicizzata.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, verificare la proprietà di un metodo o modificare le proprietà per restituire una raccolta.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Gli attributi possono contenere proprietà che restituiscono matrici, ma non possono contenere proprietà che restituiscono raccolte. È possibile eliminare un avviso che viene generato per una proprietà di un attributo derivato dal <xref:System.Attribute> classe. In caso contrario, non escludere un avviso da questa regola.

## <a name="example-violation"></a>Esempio di violazione

### <a name="description"></a>Descrizione
 Nell'esempio seguente viene illustrata una proprietà che violano questa regola.

### <a name="code"></a>Codice
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

### <a name="comments"></a>Commenti
 Per correggere una violazione di questa regola, verificare la proprietà di un metodo o modificare le proprietà per restituire una raccolta invece di una matrice.

## <a name="change-the-property-to-a-method-example"></a>Impostare la proprietà su un esempio di metodo

### <a name="description"></a>Descrizione
 Nell'esempio seguente consente di correggere la violazione modificando la proprietà a un metodo.

### <a name="code"></a>Codice
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

## <a name="return-a-collection-example"></a>Restituisce un raccolta di esempio

### <a name="description"></a>Descrizione
 Nell'esempio seguente la violazione viene corretta modificando la proprietà per restituire un

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.

### <a name="code"></a>Codice
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allowing-users-to-modify-a-property"></a>Consentire agli utenti di modificare una proprietà

### <a name="description"></a>Descrizione
 Si potrebbe voler consentono al consumer della classe modificare una proprietà. Nell'esempio seguente viene illustrata una proprietà di lettura/scrittura che violano questa regola.

### <a name="code"></a>Codice
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

### <a name="comments"></a>Commenti
 Nell'esempio seguente la violazione viene corretta modificando la proprietà per restituire un <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.

### <a name="code"></a>Codice
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>Regole correlate
 [CA1024: Usare proprietà dove appropriato](../code-quality/ca1024-use-properties-where-appropriate.md)