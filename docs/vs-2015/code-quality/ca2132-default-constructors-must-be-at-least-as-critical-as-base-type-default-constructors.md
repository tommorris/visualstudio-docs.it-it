---
title: 'CA2132: I costruttori predefiniti devono essere critici almeno come i costruttori predefiniti del tipo di base | Microsoft Docs'
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
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ecf78792e18df4956fa0147754879fb2e80648bc
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "47590310"
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: I costruttori predefiniti devono essere Critical almeno come i costruttori predefiniti del tipo base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versione più recente di questo argomento è reperibile in [CA2132: i costruttori predefiniti devono essere critici almeno come i costruttori predefiniti del tipo di base](https://docs.microsoft.com/visualstudio/code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors).

|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|Category|Microsoft.Security|
|Modifica importante|Interruzione|

> [!NOTE]
>  Questo avviso viene applicato solo al codice che esegue CoreCLR (la versione di CLR è specifico per le applicazioni Silverlight Web).

## <a name="cause"></a>Causa
 L'attributo di trasparenza del costruttore predefinito di una classe derivata non è critico come la trasparenza della classe di base.

## <a name="rule-description"></a>Descrizione della regola
 Tipi e membri che hanno il <xref:System.Security.SecurityCriticalAttribute> non può essere usato dal codice dell'applicazione Silverlight. I tipi e i membri critici per la sicurezza possono essere usati solo da codice attendibile nella libreria di classi .NET Framework per Silverlight. Poiché una costruzione pubblica o protetta in una classe derivata deve disporre della trasparenza uguale o superiore alla classe di base, una classe in un'applicazione non può essere derivata da una classe contrassegnata come SecurityCritical.

 Per il codice di piattaforma di CoreCLR, se un tipo di base ha un costruttore predefinito pubblico o protetto non trasparente quindi il tipo derivato deve rispettare le regole di ereditarietà del costruttore predefinito. Il tipo derivato deve anche avere un costruttore predefinito e tale costruttore deve essere almeno un costruttore predefinito critico del tipo di base.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere la violazione, rimuovere il tipo o non derivano dal tipo di sicurezza non trasparente.

## <a name="when-to-suppress-warnings"></a>Esclusione di avvisi
 Non eliminare gli avvisi da questa regola. Le violazioni di questa regola dal codice dell'applicazione comporta che caricare il tipo con CoreCLR un <xref:System.TypeLoadException>.

### <a name="code"></a>Codice
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2132.defaultconstructorsmusthaveconsistenttransparency/cs/ca2132 - defaultconstructorsmusthaveconsistenttransparency.cs#1)]

### <a name="comments"></a>Commenti



