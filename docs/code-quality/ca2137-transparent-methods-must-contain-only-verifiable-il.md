---
title: 'CA2137: I metodi Transparent devono contenere solo IL verificabile'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 536072f8dc019921fecd1fc6f53d255a1a0ae0d8
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551545"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: I metodi Transparent devono contenere solo IL verificabile
|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|Category|Microsoft.Security|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Un metodo contiene codice non verificabile o restituisce un tipo tramite riferimento.

## <a name="rule-description"></a>Descrizione della regola
 Questa regola viene attivata sui tentativi tramite codice trasparente per la sicurezza per eseguire MSIL (Microsoft Intermediate Language) non verificabile. Tuttavia, la regola non contiene un verificatore di IL completo, ma usa invece regole euristiche per intercettare la maggior parte delle violazioni di verifica MSIL.

 Per essere certi che il codice contiene codice MSIL verificabile solo, eseguire [Peverify.exe (strumento PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool) sull'assembly. Esecuzione di PEVerify con il **/ trasparente** opzione che limita l'output da solo non verificabili metodi trasparenti di cui verrebbe generato un errore. Se il / opzione trasparente non viene utilizzata, PEVerify verifica inoltre metodi critici che possono contenere codice non verificabile.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, contrassegnare il metodo con il <xref:System.Security.SecurityCriticalAttribute> o <xref:System.Security.SecuritySafeCriticalAttribute> o attributo, oppure rimuovere il codice non verificabile.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Non escludere un avviso da questa regola.

## <a name="example"></a>Esempio
 Il metodo in questo esempio Usa il codice non verificabile e devono essere contrassegnato con il <xref:System.Security.SecurityCriticalAttribute> o <xref:System.Security.SecuritySafeCriticalAttribute> attributo.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]