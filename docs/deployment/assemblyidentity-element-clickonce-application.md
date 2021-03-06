---
title: '&lt;assemblyIdentity&gt; elemento (applicazione ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 89b54c52625578b6ba1f7859654804fa1caaad32
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081270"
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity&gt; elemento (applicazione ClickOnce)
Identifica l'applicazione distribuita un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] distribuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```xml
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## <a name="elements-and-attributes"></a>Gli elementi e attributi  
 Il `assemblyIdentity` elemento è obbligatorio. Non contiene alcun elemento figlio e ha gli attributi seguenti.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`Name`|Obbligatorio. Identifica il nome dell'applicazione.<br /><br /> Se `Name` contiene caratteri speciali, ad esempio le virgolette singole o doppie, l'applicazione potrebbe non riuscire per l'attivazione.|  
|`Version`|Obbligatorio. Specifica il numero di versione dell'applicazione nel formato seguente: `major.minor.build.revision`|  
|`publicKeyToken`|Facoltativo. Specifica una stringa esadecimale a 16 caratteri rappresentato dagli ultimi 8 byte del `SHA-1` valore della chiave pubblica utilizzata per firmare l'applicazione o assembly hash. La chiave pubblica utilizzato per firmare il catalogo deve essere 2048 bit o superiore.<br /><br /> Anche se la firma di un assembly è facoltativo ma consigliato, questo attributo è obbligatorio. Se un assembly è firmato, è necessario copiare un valore da un assembly autofirmato oppure utilizzare un valore "fittizio" di tutti gli zeri.|  
|`processorArchitecture`|Obbligatorio. Specifica il processore. I valori validi sono `msil` per tutti i processori `x86` per Windows, a 32 `IA64` per Windows a 64 bit, e `Itanium` per processori Itanium di Intel a 64 bit.|  
|`language`|Obbligatorio. Identifica i codici di lingua di due parti (ad esempio, `en-US`) dell'assembly. Questo elemento è presente il `asmv2` dello spazio dei nomi. Se non viene specificato, il valore predefinito è `neutral`.|  
  
## <a name="examples"></a>Esempi  
  
### <a name="description"></a>Descrizione  
 L'esempio di codice seguente illustra un' `assemblyIdentity` elemento in un [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesto dell'applicazione. Questo esempio di codice è parte di un esempio più esaustivo disponibile nel [ClickOnce Application Manifest](../deployment/clickonce-application-manifest.md).  
  
### <a name="code"></a>Codice  
  
```xml  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Manifesto dell'applicazione ClickOnce](../deployment/clickonce-application-manifest.md)   
 [\<assemblyIdentity > elemento](../deployment/assemblyidentity-element-clickonce-deployment.md)