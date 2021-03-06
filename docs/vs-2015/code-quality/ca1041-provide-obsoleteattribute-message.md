---
title: 'CA1041: Fornire una proprietà ObsoleteAttribute. message | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 298f6d3cbfc8b71443fe9e8e9733e5729963cea8
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "47590337"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: Fornire una proprietà ObsoleteAttribute.Message
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [CA1041: fornire proprietà ObsoleteAttribute. message](https://docs.microsoft.com/visualstudio/code-quality/ca1041-provide-obsoleteattribute-message).

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

## <a name="when-to-suppress-warnings"></a>Esclusione di avvisi
 Non escludere un avviso da questa regola poiché il <xref:System.ObsoleteAttribute.Message%2A> proprietà fornisce informazioni essenziali di tipo o membro obsoleto.

## <a name="example"></a>Esempio
 L'esempio seguente mostra un membro obsoleto che ha dichiarato in modo corretto <xref:System.ObsoleteAttribute>.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>Vedere anche
 <xref:System.ObsoleteAttribute?displayProperty=fullName>



