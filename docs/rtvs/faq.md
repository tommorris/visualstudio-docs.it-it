---
title: Domande frequenti su R Tools per Visual Studio
description: Domande frequenti su R in Visual Studio.
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: reference
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 832d581a4147b8b050da16b1a1f72d8a3909fc35
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36235307"
---
# <a name="frequently-asked-questions"></a>Domande frequenti

## <a name="visual-studio-support"></a>Supporto di Visual Studio

**D. RTVS funziona in OS X o Linux?**

R. RTVS è attualmente basato su Visual Studio, un'implementazione solo per Windows. Microsoft sta valutando il supporto in Visual Studio Code e Visual Studio per Mac. Fare riferimento al [problema 1295 di RTVS](https://github.com/Microsoft/RTVS/issues/1295).

**D. RTVS funziona con le edizioni di Visual Studio Express?**

R. No.

**D. È possibile usare estensioni di Visual Studio con RTVS?**

R. Certamente. Di seguito sono elencate alcune estensioni usate di frequente dagli utenti che utilizzano R.

- [VsVim per tasti di scelta rapida Vim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)
- [GitHub](https://marketplace.visualstudio.com/items?itemName=GitHub.GitHubExtensionforVisualStudio)
- [Editor markdown con anteprima in tempo reale](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.MarkdownEditor)

Per altre informazioni, vedere [Visual Studio Marketplace](https://marketplace.visualstudio.com/).

**D. Dato che RTVS è integrato in Visual Studio, significa che è possibile usarlo facilmente con C#, C++ e altri linguaggi Microsoft?**

R. No. RTVS è uno strumento per lo sviluppo di codice R e usa gli interpreti R nativi standard. L'interoperabilità tra R e altri linguaggi non è al momento supportata.

**D. RTVS funziona con impostazioni locali diverse dall'inglese?**

R. La versione 1.0 di RTVS è solo in lingua inglese. La versione 1.1 sarà localizzata per lo stesso set di lingue di Visual Studio. Nel frattempo, usare [Visual Studio 2015 Language Pack](https://www.microsoft.com/download/details.aspx?id=48157) o, in Visual Studio 2017, eseguire il programma di installazione e selezionare Inglese nella scheda **Language Pack**.

![Impostazioni internazionali per Visual Studio 2017](media/FAQ-international-settings.png)

**D. Apprezzo molto le impostazioni correnti di Visual Studio, ma vorrei provare le nuove impostazioni di Data Science. Come si deve procedere?**

R. Salvare le impostazioni correnti di Visual Studio usando **Strumenti** > **Importa/Esporta impostazioni**, quindi passare alle impostazioni di Data Science. Per ripristinare le impostazioni salvate, usare di nuovo il comando **Importa/Esporta impostazioni**.

**D. È possibile archiviare un progetto di Visual Studio in una condivisione di rete?**

R. No, Visual Studio non supporta il caricamento di progetti da una condivisione di rete.

## <a name="r-interpretersintegration"></a>Interpreti/integrazione di R

**D. Con quali interpreti R funziona RTVS?**

R. [CRAN R](https://cran.r-project.org/), [Microsoft R Client e Microsoft Machine Learning Server](/machine-learning-server/)

**D. Dove è possibile scaricare questi interpreti?**

R. Vedere l'argomento [Installation](installing-r-tools-for-visual-studio.md) (Installazione).

D. **Che cos'è Microsoft R Server?**

R. R Server è il nome precedente di [Microsoft Machine Learning Server](/machine-learning-server/what-is-machine-learning-server).

**D. RTVS funziona con edizioni di R a 32 bit?**

R.  No, RTVS supporta soltanto edizioni di R a 64 bit in esecuzione su edizioni di Windows a 64 bit.

**D. RTVS funziona con il sistema di controllo del codice sorgente in uso?**

R. Sì, è possibile usare qualsiasi sistema di controllo del codice sorgente integrato in Visual Studio.

**D. Quali sono le impostazioni *.gitignore* consigliate per un progetto RTVS?**

R. GitHub gestisce un repository master di file *.gitignore* consigliati. È possibile visualizzarlo qui: [R .gitignore](https://github.com/github/gitignore/blob/master/R.gitignore)

## <a name="remote-services"></a>Servizi remoti

D. **Cosa sono i servizi remoti in Visual Studio?**

R. I servizi R remoti per Visual Studio consentono di configurare un computer Windows o Linux e quindi di connettersi a tale computer da RTVS. Vedere [Impostare aree di lavoro remote](setting-up-remote-r-workspaces.md).

D. **RTVS può connettersi a Microsoft Machine Learning Server?**

R. No, in quanto Microsoft ML Server è una tecnologia diversa e non offre lo stesso meccanismo di connettività richiesto da RTVS.

D. **RTVS può connettersi a una macchina virtuale creata usando l'immagine di macchina virtuale data science in Azure?**

R. Sì. Nell'immagine [Data Science Virtual Machine - Windows 2016](https://azure.microsoft.com/services/virtual-machines/data-science-virtual-machines/) sono preinstallati i servizi R remoti per Visual Studio.

D. **RTVS può connettersi a un computer remoto con R installato?**

Per eseguire codice R in un computer remoto deve esistere un servizio che si pone in ascolto delle richieste, riceve il codice e restituisce i risultati al computer client. Queste sono le funzionalità dei servizi R remoti per Visual Studio. Vedere [Impostare aree di lavoro remote](setting-up-remote-r-workspaces.md).

D. **Che cos'è una sessione remota?**

R. Vedere l'articolo [Execute on remote server](/machine-learning-server/r/how-to-execute-code-remotely) (Eseguire in un server remoto) nella documentazione di Machine Learning Server.

## <a name="rtvs-development-and-features"></a>Sviluppo e funzionalità di RTVS

**D. La funzionalità X non è presente, mentre è disponibile in RStudio.**

R. RStudio è un IDE per R avanzato e maturo il cui sviluppo è in corso da diversi anni. RTVS tenta di offrire tutte le funzionalità critiche necessarie agli utenti. È consigliabile contribuire alla definizione delle priorità del lavoro futuro partecipando al [sondaggio RTVS](https://www.surveymonkey.com/r/RTVS1) e registrando eventuali problemi in [GitHub](https://github.com/Microsoft/RTVS/issues/).

**D. È possibile contribuire a RTVS?**

R. Certamente. Il codice sorgente è disponibile su [GitHub](https://github.com/microsoft/RTVS). Usare la funzionalità di gestione dei problemi per segnalare bug e commentare quelli già registrati.

È anche possibile contribuire a questa documentazione. È sufficiente selezionare il comando **Modifica** disponibile in altro a destra in tutte le pagine. Sono inoltre benvenuti i commenti sulla documentazione, da aggiungere nella parte inferiore della pagina.
