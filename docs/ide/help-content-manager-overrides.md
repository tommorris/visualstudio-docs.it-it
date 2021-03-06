---
title: Override di Gestione contenuto della Guida
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8a02f4af740910fe666af295aa8535c8aef8245c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571738"
---
# <a name="help-content-manager-overrides"></a>Override di Gestione contenuto della Guida

È possibile modificare il comportamento predefinito di Help Viewer e le funzionalità correlate alla Guida nell'IDE di Visual Studio. Alcune opzioni vengono specificate mediante la creazione di un file con estensione [pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) per impostare vari valori di chiavi del Registro di sistema. Altre vengono impostate direttamente nel Registro di sistema.

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>Come controllare il comportamento di Help Viewer usando un file pkgdef

1. Creare un file *.pkgdef* con la prima riga `[$RootKey$\Help]`.

2. Aggiungere uno o tutti i valori delle chiavi del Registro di sistema descritti nella tabella seguente su righe separate, ad esempio `"UseOnlineHelp"=dword:00000001`.

3. Copiare il file in *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\\<edition\>\Common7\IDE\CommonExtensions*.

4. Eseguire `devenv /updateconfiguration` in un prompt dei comandi per gli sviluppatori.

### <a name="registry-key-values"></a>Valori delle chiavi del Registro di sistema

|Valore della chiave del Registro di sistema|Tipo|Dati|Descrizione|
|------------------|----|----|-----------|
|NewContentAndUpdateService|stringa|\<URL HTTP per l'endpoint di servizio\>|Definire un endpoint di servizio univoco|
|UseOnlineHelp|dword|`0` per specificare la Guida locale, `1` per specificare la Guida online|Impostare la Guida online o offline come predefinita|
|OnlineBaseUrl|stringa|\<URL HTTP per l'endpoint di servizio\>|Definire un endpoint F1 univoco|
|OnlineHelpPreferenceDisabled|dword|`0` per abilitare o `1` per disabilitare l'opzione di preferenza della Guida online|Disabilitare l'opzione di preferenza della Guida online|
|DisableManageContent|dword|`0` per abilitare o `1` per disabilitare la scheda **Gestisci contenuto** in Help Viewer|Disabilitare la scheda **Gestisci contenuto**|
|DisableFirstRunHelpSelection|dword|`0` per abilitare o `1` per disabilitare le funzionalità della Guida configurate al primo avvio di Visual Studio|Disabilitare l'installazione del contenuto al primo avvio di Visual Studio|

### <a name="example-pkgdef-file-contents"></a>Esempio di contenuto del file pkgdef

```
[$RootKey$\Help]
"NewContentAndUpdateService"="https://some.service.endpoint"
"UseOnlineHelp"=dword:00000001
"OnlineBaseUrl"="https://some.service.endpoint"
"OnlineHelpPreferenceDisabled"=dword:00000000
"DisableManageContent"=dword:00000000
"DisableFirstRunHelpSelection"=dword:00000001
```

## <a name="use-registry-editor-to-change-help-viewer-behavior"></a>Uso dell'editor del Registro di sistema per modificare il comportamento di Help Viewer

È possibile controllare i due comportamenti seguenti impostando i valori di chiavi del Registro di sistema nell'Editor del Registro di sistema.

|Attività|Chiave del Registro di sistema|Valore|Dati|
|----------|-----|------|----|
|Eseguire l'override della priorità del processo BITS|HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node (in un computer a 64 bit)\Microsoft\Help\v2.3|BITSPriority|**foreground**, **high**, **normal** o **low**|
|Puntare all'archivio del contenuto locale nella condivisione di rete|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\ v2.3\Catalogs\VisualStudio15|LocationPath|"*ContentStoreNetworkShare*"|

## <a name="see-also"></a>Vedere anche

- [Guida dell'amministratore di Help Viewer](../ide/help-viewer-administrator-guide.md)
- [Argomenti della riga di comando per la Gestione contenuto della Guida](../ide/command-line-arguments-for-the-help-content-manager.md)
- [Microsoft Help Viewer](../ide/microsoft-help-viewer.md)