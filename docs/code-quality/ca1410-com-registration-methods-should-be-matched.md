---
title: 'CA1410: I metodi di registrazione COM devono corrispondere'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
helpviewer_keywords:
- CA1410
- ComRegistrationMethodsShouldBeMatched
ms.assetid: f3b2e62d-fd66-4093-9f0c-dba01ad995fd
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 1d4cbff52a5b5b5ef5fc46ef0b2f93926f097485
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550895"
---
# <a name="ca1410-com-registration-methods-should-be-matched"></a>CA1410: I metodi di registrazione COM devono corrispondere

|||
|-|-|
|TypeName|ComRegistrationMethodsShouldBeMatched|
|CheckId|CA1410|
|Category|Microsoft.Interoperability|
|Modifica importante|Non sostanziale|

## <a name="cause"></a>Causa
 Un tipo dichiara un metodo contrassegnato con il <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> attributo ma non dichiara un metodo contrassegnato con il <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> attributo, o viceversa.

## <a name="rule-description"></a>Descrizione della regola
 Per i client modello COM (Component Object) creare un [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tipo, il tipo deve prima essere registrato. Se è disponibile, un metodo contrassegnato con il <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> attributo viene chiamato durante il processo di registrazione per l'esecuzione di codice specificato dall'utente. Un metodo corrispondente che è contrassegnato con il <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute> attributo viene chiamato durante il processo di annullamento della registrazione per invertire le operazioni del metodo di registrazione.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Per correggere una violazione di questa regola, aggiungere il metodo di annullamento della registrazione o di registrazione corrispondente.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 Non escludere un avviso da questa regola.

## <a name="example"></a>Esempio
 Nell'esempio seguente viene illustrato un tipo che viola la regola. Il codice commentato Mostra la correzione per la violazione.

 [!code-csharp[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/CSharp/ca1410-com-registration-methods-should-be-matched_1.cs)]
 [!code-vb[FxCop.Interoperability.ComRegistration#1](../code-quality/codesnippet/VisualBasic/ca1410-com-registration-methods-should-be-matched_1.vb)]

## <a name="related-rules"></a>Regole correlate
 [CA1411: I metodi di registrazione COM non devono essere visibili](../code-quality/ca1411-com-registration-methods-should-not-be-visible.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.RegistrationServices?displayProperty=fullName>
- [Registrazione di assembly presso COM](/dotnet/framework/interop/registering-assemblies-with-com)
- [Regasm.exe (strumento di registrazione di assembly)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)