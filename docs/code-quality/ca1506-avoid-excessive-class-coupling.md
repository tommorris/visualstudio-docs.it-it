---
title: 'CA1506: Evitare un numero eccessivo di accoppiamenti di classi'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 57c23ea9c6afb27ee89886936fff690a4285f5c0
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549911"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Evitare un numero eccessivo di accoppiamenti di classi

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|Category|Microsoft.Maintainability|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Un tipo o metodo è associata a molti altri tipi.

## <a name="rule-description"></a>Descrizione della regola
 Questa regola misura l'accoppiamento tra classi contando il numero di riferimenti al tipo univoci contenuti in un tipo o metodo.

 Tipi e metodi che hanno un livello elevato di accoppiamenti di classi possono essere difficili da gestire. È buona norma disporre di tipi e metodi che mostrano uno stile accoppiamento ridotto e un'elevata coesione.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere questa violazione, provare a riprogettare il tipo o metodo in modo da ridurre il numero di tipi a cui è associato.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Escludere questo avviso quando il tipo o metodo è considerato accettabile, nonostante il numero elevato di dipendenze da altri tipi.

## <a name="see-also"></a>Vedere anche

- [Avvisi di manutenibilità](../code-quality/maintainability-warnings.md)
- [Misurazione della complessità e della manutenibilità del codice gestito](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)