---
title: 'CA1034: I tipi annidati non devono essere visibili'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 14c0837d482341e1ba60191c8b6bb3f5bd8e6dd4
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550947"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: I tipi annidati non devono essere visibili

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Category|Microsoft.Design|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa

Un tipo visibile esternamente contiene una dichiarazione del tipo visibile esternamente. Enumerazioni annidate e i tipi protetti sono esclusi da questa regola.

## <a name="rule-description"></a>Descrizione della regola
 Un tipo annidato è un tipo dichiarato nell'ambito di un altro tipo. I tipi annidati sono utili per incapsulare i dettagli di implementazione privati del tipo contenitore. I tipi annidati utilizzati per questo scopo non devono essere visibili esternamente.

 Non usare i tipi annidati visibili esternamente per il raggruppamento logico o per evitare conflitti di nome; Usare invece gli spazi dei nomi.

 I tipi annidati includono la nozione di accessibilità del membro, che alcuni programmatori non supportano in modo chiaro.

 Tipi protetti possono essere utilizzati nelle sottoclassi e i tipi annidati in scenari di personalizzazione avanzate.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Se non si intende il tipo annidato da essere visibili esternamente, modificare l'accessibilità del tipo. In caso contrario, rimuovere il tipo annidato dal relativo elemento padre. Se lo scopo dell'annidamento è per classificare il tipo annidato, usare uno spazio dei nomi per creare invece una gerarchia.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Non escludere un avviso da questa regola.

## <a name="example"></a>Esempio
 Nell'esempio seguente viene illustrato un tipo che viola la regola.

 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]