---
title: Concedere l'attendibilità alle soluzioni Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- security [Office development in Visual Studio], trust
- inclusion lists [Office development in Visual Studio], about inclusion lists
- trust [Office development in Visual Studio], 2007 Office system
- granting trust [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cfce58ca765e7e3710ecb55a1c84c09f0ee14f52
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2018
ms.locfileid: "34447245"
---
# <a name="grant-trust-to-office-solutions"></a>Concedere l'attendibilità alle soluzioni Office
  Concedere l'attendibilità a Office soluzioni mezzi Modifica criteri di sicurezza di ogni computer di destinazione per considerare attendibile l'assembly della soluzione, manifesto dell'applicazione, il manifesto di distribuzione e documento. È possibile concedere l'attendibilità alla soluzione Office per l'utente o l'utente finale.  
  
 È possibile concedere l'attendibilità alla soluzione Office firmando i manifesti dell'applicazione e distribuzione.  
  
 Gli utenti finali possono concedere l'attendibilità alla soluzione Office effettuando una decisione di attendibilità nel [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] richiesta di attendibilità.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
##  <a name="Signing"></a> Attendibilità alla soluzione firmando i manifesti dell'applicazione e distribuzione  
 Tutte le applicazioni e distribuzione di manifesti per soluzioni devono essere firmate con un certificato che identifica il server di pubblicazione di Office. I certificati forniscono una base per prendere decisioni sull'attendibilità.  
  
 Un certificato temporaneo viene creato e concessa l'attendibilità in fase di compilazione in modo la soluzione verrà eseguita durante il debug. Se si pubblica una soluzione che viene firmata con un certificato temporaneo, l'utente finale verrà richiesto di prendere una decisione di attendibilità.  
  
 Se si esegue la soluzione con un certificato noto e attendibile, la soluzione verrà installata automaticamente senza chiedere conferma all'utente finale di prendere una decisione di attendibilità. Per ulteriori informazioni su come ottenere un certificato per la firma, vedere [ClickOnce e Authenticode](/visualstudio/deployment/clickonce-and-authenticode). Dopo aver ottenuto un certificato, il certificato deve essere attendibile in modo esplicito per aggiungerlo all'elenco di editori attendibili. Per altre informazioni, vedere [procedura: aggiungere un autore attendibile a un computer client per le applicazioni ClickOnce](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications).  
  
 Se uno sviluppatore esegue la soluzione con un certificato temporaneo, un amministratore può firmare nuovamente la personalizzazione con un certificato noto e attendibile mediante la generazione e la modifica dello strumento (*mage.exe*), che fa parte di Strumenti di Microsoft .NET Framework. Per ulteriori informazioni sulla firma delle soluzioni, vedere [come: soluzioni Office Sign](../vsto/how-to-sign-office-solutions.md) e [procedura: firmare manifesti dell'applicazione e distribuzione](/visualstudio/ide/how-to-sign-application-and-deployment-manifests).  
  
##  <a name="TrustPrompt"></a>Attendibilità alla soluzione utilizzando la richiesta di attendibilità di ClickOnce  
 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] richiede all'utente finale di prendere la decisione di attendibilità se nessun criterio a livello di organizzazione che considera attendibile il certificato della soluzione. Se l'utente finale concede l'attendibilità alla soluzione, viene creata una voce di elenco di inclusione contenente un URL e una chiave pubblica per archiviare la decisione di attendibilità. Quando una personalizzazione attendibile viene eseguita in un secondo momento, è possibile che all'utente finale non è richiesto nuovamente.  
  
 Gli amministratori possono disabilitare la [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] richiesta di attendibilità o richiedono che il prompt dei comandi si verificano solo per le soluzioni che sono firmate con un certificato Authenticode. Per ulteriori informazioni su come modificare queste impostazioni per le zone MyComputer, LocalIntranet, Internet, ai siti attendibili e siti non attendibili, vedere [procedura: configurare il comportamento della richiesta di attendibilità ClickOnce](/visualstudio/deployment/how-to-configure-the-clickonce-trust-prompt-behavior).  
  
## <a name="see-also"></a>Vedere anche  
 [Proteggere le soluzioni Office](../vsto/securing-office-solutions.md)   
 [Concedere l'attendibilità a documenti](../vsto/granting-trust-to-documents.md)   
 [Risolvere i problemi di sicurezza delle soluzioni Office](../vsto/troubleshooting-office-solution-security.md)   
 [Considerazioni specifiche sulla sicurezza per le soluzioni Office](../vsto/specific-security-considerations-for-office-solutions.md)  
  
  