---
title: 'CA1501: Evitare ereditarietà eccessiva'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0627d246fe9f9f72a95cded7daf8d2c94bf20b3a
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546964"
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Evitare ereditarietà eccessiva

|||
|-|-|
|TypeName|AvoidExcessiveInheritance|
|CheckId|CA1501|
|Category|Microsoft.Maintainability|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Un tipo si trova oltre il quarto livello di annidamento nella gerarchia di ereditarietà.

## <a name="rule-description"></a>Descrizione della regola
 Le gerarchie di tipi eccessivamente annidate possono comportare difficoltà di comprensione e gestione. Questa regola consente di limitare analysis alle gerarchie nello stesso modulo.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, derivare il tipo da un tipo di base che è meno approfondito nella gerarchia di ereditarietà o eliminare alcuni dei tipi di base intermedi.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 È possibile eliminare un avviso da questa regola. Tuttavia, il codice potrebbe essere più difficile da gestire. Si noti che, a seconda della visibilità dei tipi di base, la risoluzione delle violazioni di questa regola potrebbe creare le modifiche di rilievo. Ad esempio, la rimozione dei tipi di base pubblici è una modifica sostanziale.

## <a name="example"></a>Esempio
 Nell'esempio seguente viene illustrato un tipo che viola la regola.

 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]