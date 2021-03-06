---
title: Implementazione di un Service1 Language Legacy | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0486b8ad035d64f542d48f1e304413780958d90c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129334"
---
# <a name="implementing-a-legacy-language-service"></a>Implementazione di un servizio di linguaggio Legacy
È possibile utilizzare classi il framework di pacchetto gestito (MPF) per implementare un servizio di linguaggio legacy che supporta un'ampia gamma di funzionalità, ad esempio l'evidenziazione della sintassi, corrispondenza parentesi graffe e il completamento di IntelliSense.  
  
 Servizi di linguaggio legacy vengono implementati come parte di un VSPackage, ma il più recente per implementare le funzionalità del servizio di linguaggio consiste nell'utilizzare le estensioni MEF. Per ulteriori informazioni sul programma per implementare un servizio di linguaggio, vedere [Editor e le estensioni del servizio di linguaggio](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Si consiglia di iniziare a usare il nuovo editor di API appena possibile. Verrà migliorare le prestazioni del servizio di linguaggio e consentono di sfruttare nuove funzionalità dell'editor.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica dei servizi di linguaggio legacy](../../extensibility/internals/legacy-language-service-overview.md)  
 Panoramica di servizio delle funzionalità del linguaggio che sono supportati in MPF.  
  
 [Implementazione di un servizio di linguaggio Legacy](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 Vengono descritte le funzionalità necessarie per implementare un servizio di linguaggio tramite MPF.  
  
 [Registrazione di un servizio di linguaggio Legacy](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 Vengono descritti i passaggi necessari per registrare un servizio di linguaggio basato su MPF con [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Scanner e parser dei servizi di linguaggio legacy](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 Descrive i due parser necessari per implementare tutte le funzionalità di un servizio di linguaggio tramite MPF.  
  
 [Procedura dettagliata: Creazione di un servizio di linguaggio legacy](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Fornisce i passaggi di base necessarie per implementare un servizio di linguaggio MPF in un pacchetto VSPackage.  
  
 [Procedura dettagliata: Recupero di un elenco di frammenti di codice installati (implementazione legacy)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 Vengono illustrate le tecniche di recupero di un elenco di frammenti di codice installato.  
  
 [Funzionalità del linguaggio legacy](../../extensibility/internals/legacy-language-service-features1.md)  
 Vengono forniti collegamenti ad argomenti che illustrano in dettaglio le operazioni necessarie per implementare tutte le funzionalità di un servizio di linguaggio tramite MPF.