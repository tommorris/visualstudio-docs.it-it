---
title: 'CA1041: Fornire una proprietà ObsoleteAttribute.Message'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: d8e8a4be147a786da06f3fdb7f961a7b36aa85a4
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546953"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: Fornire una proprietà ObsoleteAttribute.Message

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Category|Microsoft.Design|
|Modifica importante|Non sostanziale|

## <a name="cause"></a>Causa
 Un tipo o membro è contrassegnato utilizzando un <xref:System.ObsoleteAttribute?displayProperty=fullName> attributo che non è relativo <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> proprietà specificata.

## <a name="rule-description"></a>Descrizione della regola
 <xref:System.ObsoleteAttribute> Consente di contrassegnare i membri e tipi di libreria obsoleto. Consumer della libreria è consigliabile evitare l'uso di qualsiasi tipo o membro che è contrassegnato come obsoleto. Si tratta in quanto potrebbero non essere supportata e verranno infine rimosse dalle versioni successive della libreria. Quando un tipo o il membro contrassegnato utilizzando <xref:System.ObsoleteAttribute> viene compilato, la <xref:System.ObsoleteAttribute.Message%2A> proprietà dell'attributo viene visualizzata. In questo modo vengono fornite le informazioni utente sul tipo o sul membro obsoleto. Queste informazioni includono in genere il tempo di tipo obsoleto o membro sarà supportato per le finestre di progettazione di libreria e la sostituzione preferita da usare.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, aggiungere il `message` parametro per il <xref:System.ObsoleteAttribute> costruttore.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Non escludere un avviso da questa regola poiché il <xref:System.ObsoleteAttribute.Message%2A> proprietà fornisce informazioni essenziali di tipo o membro obsoleto.

## <a name="example"></a>Esempio
 L'esempio seguente mostra un membro obsoleto che ha dichiarato in modo corretto <xref:System.ObsoleteAttribute>.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>Vedere anche
 <xref:System.ObsoleteAttribute?displayProperty=fullName>