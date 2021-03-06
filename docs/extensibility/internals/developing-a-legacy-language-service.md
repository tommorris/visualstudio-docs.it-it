---
title: Sviluppo di un servizio di linguaggio Legacy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- vs.vsip.LangServWiz.langtoks
- vs.vsip.LangServWiz.welcome
- vs.vsip.LangServWiz.langSpec
- vs.vsip.LangServWiz.langInfo
- vs.vsip.LangServWiz.langServOpts
helpviewer_keywords:
- language services, developing
ms.assetid: 6151ba88-c1c3-41de-a1cc-668f494d48d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d92c07742dcc4433aa96071d655f58d938a1f80
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497830"
---
# <a name="develop-a-legacy-language-service"></a>Sviluppare un servizio di linguaggio legacy
Questa sezione sono riportati i collegamenti ad argomenti che consentono di creare un servizio di linguaggio legacy.  
  
 Servizi di linguaggio legacy vengono implementati come parte di un pacchetto VSPackage, ma il modo più recente per implementare le funzionalità del servizio di linguaggio consiste nell'usare le estensioni MEF. Per altre informazioni sul nuovo modo per implementare un servizio di linguaggio, vedere [le estensioni del servizio di Editor e linguaggio](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  È consigliabile che si inizia a usare il nuovo editor delle API appena possibile. Verrà migliorare le prestazioni del servizio di linguaggio e consentono di sfruttare nuove funzionalità dell'editor.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Modello di un servizio di linguaggio legacy](../../extensibility/internals/model-of-a-legacy-language-service.md)  
 Fornisce un modello di un servizio di linguaggio minimo per il [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] editor principale. È possibile usare questo modello come guida per la creazione di un proprio servizio di linguaggio.  
  
 [Interfacce del servizio di linguaggio legacy](../../extensibility/internals/legacy-language-service-interfaces.md)  
 Descrive gli oggetti necessari per implementare un servizio di linguaggio e fornisce un elenco di oggetti aggiuntivi che è possibile usare per fornire l'evidenziazione della sintassi, i dati del metodo e altre funzionalità.  
  
 [Intercetta comandi del servizio di linguaggio legacy](../../extensibility/internals/intercepting-legacy-language-service-commands.md)  
 Viene descritto come inserire un filtro di comando nel servizio di linguaggio per intercettare i comandi che in caso contrario, è necessario gestire la visualizzazione di testo.  
  
 [Registrare un servizio di linguaggio legacy](../../extensibility/internals/registering-a-legacy-language-service2.md)  
 Fornisce informazioni su come registrare il servizio di linguaggio usando [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Supporto del servizio del linguaggio per il debug](../../extensibility/internals/language-service-support-for-debugging.md)  
 Viene descritto come un servizio di linguaggio può fornire funzionalità per supportare un debugger.  
  
 [Elenco di controllo: Creare un servizio di linguaggio legacy](../../extensibility/internals/checklist-creating-a-legacy-language-service.md)  
 Vengono fornite istruzioni dettagliate per la creazione e l'integrazione di un servizio di linguaggio per l'editor principale.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Colorazione della sintassi in un servizio di linguaggio legacy](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)  
 Viene illustrato come implementare l'evidenziazione della sintassi nel servizio di linguaggio.  
  
 [Completamento delle istruzioni in un servizio di linguaggio legacy](../../extensibility/internals/statement-completion-in-a-legacy-language-service.md)  
 Illustra il completamento, il processo mediante il quale un servizio di linguaggio consente agli utenti di completare una parola chiave del linguaggio o l'elemento che è stato avviato digitando.  
  
 [Informazioni sui parametri in un servizio di linguaggio legacy](../../extensibility/internals/parameter-info-in-a-legacy-language-service1.md)  
 Viene descritto come fornire suggerimenti di metodo per le funzioni in overload e i metodi.  
  
 [Procedura: fornire il testo nascosto supportare in un servizio di linguaggio legacy](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)  
 Viene illustrato lo scopo di un'area di testo nascosto e vengono fornite istruzioni su come implementare un'area di testo nascosto.  
  
 [Procedura: fornire supporto per la struttura espanso in un servizio di linguaggio legacy](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)  
 Illustra le due opzioni che estendono il supporto della struttura per il linguaggio oltre, supportando il *Comprimi alle definizioni* comando.