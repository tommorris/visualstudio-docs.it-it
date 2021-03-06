---
title: Identità per i sottoscrittori di Visual Studio
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: Come aggiungere un'identità alternativa PER sottoscrizione di Visual Studio da usare per Visual Studio Team Services e Azure
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 30aa1e918e289a6cfe8f11329d5df7682cd90239
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2018
ms.locfileid: "43289500"
---
# <a name="identities-for-visual-studio-subscribers"></a>Identità per i sottoscrittori di Visual Studio

Quando si attiva la sottoscrizione di Visual Studio, l'identità (o l'account di accesso) usata durante l'attivazione viene collegata alla sottoscrizione di Visual Studio. In questo modo, è possibile riconoscere l'utente nel [portale per i sottoscrittori Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), in Visual Studio Team Services (VSTS) e in Azure.

In Visual Studio Team Services, lo stato della sottoscrizione di Visual Studio viene controllato a ogni accesso e vengono concesse automaticamente le funzionalità incluse per ogni account in cui si è membri.
Poiché queste funzionalità sono incluse come vantaggio per i sottoscrittori, un utente può essere aggiunto gratuitamente come membro di qualsiasi account di Visual Studio Team Services quando si usa un'identità collegata alla sottoscrizione di Visual Studio.

In Azure, lo stato della sottoscrizione di Visual Studio viene controllato quando si attiva il [credito di Azure mensile](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) che è un vantaggio dei sottoscrittori.

All'interno del [portale per i sottoscrittori di Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) potrebbe essere possibile aggiungere un'**identità alternativa** oltre a quella usata durante l'attivazione. Attualmente l'aggiunta di un'identità alternativa è consentita se è stato usato un account Microsoft per attivare la sottoscrizione. In questo modo è possibile aggiungere anche un account aziendale o dell'istituto di istruzione (usato per l'accesso a Visual Studio, Office 365 o alla rete aziendale o dell'istituto di istruzione), consentendo l'accesso a Visual Studio Team Services tramite l'account personale e l'account aziendale o dell'istituto di istruzione.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Aggiungere un account alternativo alla sottoscrizione di Visual Studio

L'aggiunta di un account alternativo alla sottoscrizione di Visual Studio consente di accedere ai vantaggi della sottoscrizione, tra cui Visual Studio Team Services (VSTS) e Azure, con un'identità diversa rispetto a quella a cui è assegnata la sottoscrizione. In precedenza, questa funzionalità era disponibile solo se la sottoscrizione di Visual Studio (VS) era assegnata a un account Microsoft. Questa funzionalità è stata estesa agli account aziendali o di istituti di istruzione in Azure Active Directory (Azure AD).

Questa funzionalità non fornisce una copia della sottoscrizione all'altro account, ma consente solo di accedere ai due vantaggi con l'account alternativo.

Per tutte le sottoscrizioni è possibile aggiungere un "account aziendale o dell'istituto di istruzione" in modo da poter usare l'account con i vantaggi che richiedono un account di accesso (IDE di Visual Studio, Visual Studio Team Services e Azure).


### <a name="add-the-alternate-account"></a>Aggiungere l'account alternativo


1. Accedere al portale per i sottoscrittori di Visual Studio con il proprio account Microsoft (https://my.visualstudio.com).

2. Passare a **Sottoscrizioni**.

    > [!div class="mx-imgBorder"]
    > ![Aggiungere l'account alternativo. Passare alle sottoscrizioni in Visual Studio](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. Scegliere **Aggiungi un account alternativo**.
    > [!div class="mx-imgBorder"]
    > ![Scegliere Aggiungi un account alternativo](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. Aggiungere l'account aziendale o dell'istituto di istruzione.
    > [!div class="mx-imgBorder"]
    > ![Aggiungere l'account aziendale o dell'istituto di istruzione](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Usare l'account aziendale o dell'istituto di istruzione per accedere a Visual Studio Team Services (https://{account}.visualstudio.com).
    > [!div class="mx-imgBorder"]
    > ![Usare l'account aziendale o dell'istituto di istruzione](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

L'account alternativo viene aggiunto alla sottoscrizione Visual Studio, consentendo a entrambe le identità di sfruttare i vantaggi della sottoscrizione che richiedono di accedere con l'account alternativo (IDE, Visual Studio Team Services e Azure).

## <a name="faq"></a>Domande frequenti

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>D: perché VSTS non riconosce un utente come sottoscrittore di Visual Studio?

R: VSTS dovrebbe riconoscere automaticamente la sottoscrizione quando si esegue l'accesso con l'identità primaria o alternativa. In caso contrario, è possibile:

* Controllare di avere una sottoscrizione di Visual Studio attiva che [include VSTS come vantaggio](vs-vsts.md).

* Assicurarsi di usare un account di accesso o un'identità che rappresenta l'identità primaria o alternativa per la sottoscrizione di Visual Studio.

* Visitare il [portale per i sottoscrittori di Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) almeno una volta prima di accedere a VSTS.

Se VSTS non riconosce ancora la sottoscrizione, [contattare il supporto tecnico](https://visualstudio.microsoft.com/team-services/support/)
