---
title: 'CA2103: Controllare la sicurezza imperativa'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f8975e3118e9907bf4688efe93dc60646b6d80b
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45547696"
---
# <a name="ca2103-review-imperative-security"></a>CA2103: Controllare la sicurezza imperativa

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|Category|Microsoft.Security|
|Modifica importante|Interruzione|

## <a name="cause"></a>Causa
 Un metodo utilizza la sicurezza imperativa e potrebbe costruire l'autorizzazione tramite le informazioni sullo stato o i valori restituiti che possono essere modificati mentre la richiesta è attiva.

## <a name="rule-description"></a>Descrizione della regola
 La sicurezza imperativa Usa gli oggetti gestiti per specificare le autorizzazioni e le azioni di sicurezza durante l'esecuzione di codice, rispetto alla protezione dichiarativa, che usa gli attributi per archiviare le autorizzazioni e le azioni nei metadati. La sicurezza imperativa è molto flessibile in quanto è possibile impostare lo stato di un oggetto di autorizzazione e selezionare azioni di sicurezza con le informazioni che non sono disponibile fino al runtime. Tale flessibilità comporta il rischio che le informazioni di runtime utilizzato per determinare che lo stato di un'autorizzazione non rimangono invariate, purché l'azione è attiva.

 Utilizzare la sicurezza dichiarativa quando possibile. Le richieste dichiarative sono più facili da comprendere.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni
 Rivedere le richieste di sicurezza imperativa per assicurarsi che lo stato dell'autorizzazione non si basa sulle informazioni che possono cambiare, purché l'autorizzazione è in uso.

## <a name="when-to-suppress-warnings"></a>Soppressione degli avvisi
 È possibile eliminare un avviso da questa regola se l'autorizzazione non si basa sulla modifica dei dati. Tuttavia, è preferibile modificare la richiesta imperativa equivalente dichiarativo.

## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](/dotnet/standard/security/secure-coding-guidelines)
- [Dati e modellazione](/dotnet/framework/data/index)