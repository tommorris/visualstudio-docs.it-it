---
title: 'CA1043: Utilizzare argomento di tipo stringa o integrale per gli indicizzatori'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: bb8781b205da07c1c075e2638716cfc139491d07
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550583"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043: Utilizzare argomento di tipo stringa o integrale per gli indicizzatori

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Category|Microsoft.Design|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Un tipo pubblico o protetto contiene un indicizzatore pubblico o protetto che utilizza un tipo di indice diverso da <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, o <xref:System.String?displayProperty=fullName>.

## <a name="rule-description"></a>Descrizione della regola
 Gli indicizzatori, ovvero, le proprietà indicizzate, devono utilizzare tipi integer o stringa per l'indice. Questi tipi vengono generalmente usati per indicizzare strutture di dati e aumentano l'usabilità della libreria. Usare il <xref:System.Object> tipo deve essere limitato ai casi in cui non è possibile specificare il tipo specifico di tipo integer o stringa in fase di progettazione. Se la struttura richiede altri tipi per l'indice, verificare che il tipo rappresenta un archivio dati logici. Se non rappresenta un archivio dati logici, utilizzare un metodo.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, modificare l'indice in un tipo integer o stringa o usare un metodo invece l'indicizzatore.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Eliminare un avviso da questa regola solo dopo aver considerato con attenzione la necessità per l'indicizzatore non standard.

## <a name="example"></a>Esempio
 L'esempio seguente mostra un indicizzatore che usa un <xref:System.Int32> indice.

 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>Regole correlate
 [CA1023: Gli indicizzatori non devono essere multidimensionali](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024: Usare proprietà dove appropriato](../code-quality/ca1024-use-properties-where-appropriate.md)