---
title: Comando contratti negli assembly di interoperabilità | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c2ac80125111ebfe3d8a7e5dc89d1f2597f8d3a4
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510855"
---
# <a name="command-contracts-in-interop-assemblies"></a>Contratti dei comandi negli assembly di interoperabilità
Il contratto di base per la gestione dei comandi tramite il <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfaccia è che l'ambiente chiama il <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metodo per determinare se il comando è supportato e, se supportato, per determinarne lo stato e testo. Quindi, l'ambiente chiama il <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metodo per eseguire il comando.  
  
 Il <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metodo viene gestito in modo identico per tutti i comandi. Ulteriori comunicazioni, se necessario (ad esempio, con elenchi a discesa), vengano gestita chiamando il <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> metodo con i parametri appropriati. L'interpretazione di questi parametri dipende il comando specificato.  
  
 Se la destinazione del comando restituisce i valori nel parametro di output, il chiamante è sempre responsabile della liberazione tutte le risorse che sono state allocate. Poiché questo parametro è una variante, la cancellazione di variant libera le risorse.  
  
 Nei casi in cui i comandi devono operare all'interno di una finestra della gerarchia, il <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> interfaccia deve essere usata. Il <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> interfaccia dispone di un contratto analogo con metodi simili: <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> e <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 [Come i pacchetti VSPackage aggiungono elementi dell'interfaccia utente](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Routing dei comandi nei pacchetti VSPackage](../../extensibility/internals/command-routing-in-vspackages.md)   
 [Implementazione del comando](../../extensibility/internals/command-implementation.md)