---
title: Implementazione di generatori di File singolo | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71db8036634cfc266db3c585c48317262f48b367
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129364"
---
# <a name="implementing-single-file-generators"></a>Implementazione di generatori di File singolo
Uno strumento personalizzato, talvolta detta un generatore di file singolo, possono essere usati per estendere il [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] e [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] sistemi di progetto [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Uno strumento personalizzato è un componente COM che implementa il <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> interfaccia. Utilizzo di questa interfaccia, uno strumento personalizzato Trasforma un singolo file di input in un singolo file di output. Il risultato della trasformazione può essere codice sorgente, o qualsiasi altro output che è utile. Due esempi di file di codice generati da strumenti personalizzati sono codice generato in risposta alle modifiche in una finestra di progettazione e i file generati utilizzando i servizi Web (WSDL, Web Services Description Language).  
  
 Quando viene caricato uno strumento personalizzato o viene salvato il file di input, il sistema di progetto chiama il <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metodo e passa un riferimento a un <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> interfaccia di callback, in base al quale lo strumento può segnalare lo stato di avanzamento all'utente.  
  
 Il file di output generato dallo strumento personalizzato viene aggiunto al progetto con una dipendenza sul file di input. Il sistema del progetto determina automaticamente il nome del file di output, in base alla stringa restituita dall'implementazione dello strumento personalizzato di <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 Uno strumento personalizzato deve implementare il <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> interfaccia. Facoltativamente, gli strumenti personalizzati supportano il <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> interfaccia per il recupero di informazioni da origini diverse del file di input. In ogni caso, prima di poter utilizzare uno strumento personalizzato, è necessario registrarlo con il sistema o nel [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Registro di sistema locale. Per ulteriori informazioni sulla registrazione di strumenti personalizzati, vedere [registrazione generatori di File singolo](../../extensibility/internals/registering-single-file-generators.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Esposizione di tipi nelle finestre di progettazione visiva](../../extensibility/internals/exposing-types-to-visual-designers.md)