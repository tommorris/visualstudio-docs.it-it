---
title: Creare codice personalizzato e plug-in per i test di carico in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 213824ff9be80a151d20b4906839969dce3be7d1
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2018
ms.locfileid: "39175537"
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Creare codice personalizzato e plug-in per test di carico

Un plug-in personalizzato usa codice scritto e collegato a un test di carico o a un test Web. È possibile usare l'API del test di carico e l'API del test Web per creare plug-in personalizzati per i test al fine di espandere le funzionalità predefinite. È possibile aggiungere più plug-in al test di carico.

## <a name="tasks"></a>Attività

|Attività|Argomenti correlati|
|-----------|-----------------------|
|**Creare un plug-in personalizzato per il test di carico**: è possibile usare l'API del test di carico per creare un plug-in personalizzato che consenta di aggiungere altre funzionalità di test al test di carico.|-   [Procedura: Usare l'API del test di carico](../test/how-to-use-the-load-test-api.md)<br />-   [Procedura: Creare un plug-in test di carico](../test/how-to-create-a-load-test-plug-in.md)|
|**Creare un plug-in personalizzato per il test delle prestazioni Web:** è possibile usare l'API del test delle prestazioni Web per creare un plug-in personalizzato che consenta di aggiungere altre funzionalità di test al test delle prestazioni Web, anche a livello di richiesta. È anche possibile creare un test del servizio Web.<br /><br /> Inoltre, è possibile creare un plug-in di registrazione Web con il quale è possibile modificare un test delle prestazioni Web dopo che viene registrato, ma prima che venga visualizzato nel Visualizzatore risultati test prestazioni Web.|-   [Procedura: Usare l'API del test delle prestazioni Web](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Procedura: Creare un plug-in di test prestazioni Web](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Procedura: Creare un plug-in a livello di richiesta](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Procedura: Creare un test di servizio Web](../test/how-to-create-a-web-service-test.md)<br />-   [Procedura: Creare un plug-in di registrazione](../test/how-to-create-a-recorder-plug-in.md)|
|**Aggiungere funzionalità dell'interfaccia utente al Visualizzatore risultati test prestazioni Web:** è possibile aggiungere altre funzionalità dell'interfaccia utente al Visualizzatore risultati test prestazioni Web usando un componente aggiuntivo di Visual Studio.|-   [Procedura: Creare un componente aggiuntivo di Visual Studio per il Visualizzatore risultati test prestazioni Web](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Creare un editor del corpo HTTP personalizzato:** è possibile creare un editor personalizzato per modificare le risposte XML HTTP stringa o binario di un servizio Web.|-   [Procedura: Creare un editor del corpo HTTP personalizzato per l'Editor test prestazioni Web](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Riferimenti

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Vedere anche

- [Analizzare i risultati dei test di carico](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Generare ed eseguire un test delle prestazioni Web codificato](../test/generate-and-run-a-coded-web-performance-test.md)