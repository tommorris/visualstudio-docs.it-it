---
title: 'Procedura: aggiungere una dipendenza a un pacchetto VSIX | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84865bf354bd1822ca872ed5f0df89a4330fb690
ms.sourcegitcommit: 3dd15e019cba7d35dbabc1aa3bf55842a59f5278
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371043"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Procedura: aggiungere una dipendenza a un pacchetto VSIX

È possibile configurare una distribuzione di pacchetto VSIX che installa le dipendenze che non sono già presenti nel computer di destinazione. A tale scopo, includere le dipendenze di progetto VSIX per la *vsixmanifest* file.

## <a name="to-add-a-dependency"></a>Per aggiungere una dipendenza

1. Aprire il *vsixmanifest* del file nei **progettazione** visualizzazione. Andare alla **dipendenze** scheda e fare clic su **New**.

2. Per aggiungere un'estensione installata: nel **aggiungere nuove dipendenze** finestra di dialogo **estensione installata** e quindi, per il **nome**, selezionare un'estensione nell'elenco.

3. Per aggiungere un altro progetto VSIX che non è installato: nel **aggiungere nuove dipendenze** finestra di dialogo **File nel file system** e quindi usare il **Sfoglia** pulsante per selezionare il progetto VSIX.

## <a name="require-a-specific-visual-studio-release"></a>Richiedi una versione specifica di Visual Studio

Se l'estensione richiede una versione specifica di Visual Studio 2017, ad esempio, dipende da una funzionalità disponibile nella versione 15.3, è possibile specificare il numero di build in VSIX **la destinazione di installazione**. Ad esempio, versione 15.3 presenta un numero di build del '15.0.26730.3'. È possibile visualizzare il mapping delle versioni per i numeri di build [qui](../install/visual-studio-build-numbers-and-release-dates.md). Si noti che usando il numero di versione '15.3' non funzionerà correttamente.

Se l'estensione richiede la versione 15.3 o versioni successive, è necessario dichiarare la **versione la destinazione di installazione** come [15.0.26730.3, 16.0):

```xml
<Installation>
  <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0.26730.3, 16.0)" />
</Installation>
```

Il VSIX Installer rileverà le versioni precedenti di Visual Studio e informare l'utente che è necessario un aggiornamento successivo.


## <a name="see-also"></a>Vedere anche

 [Riferimenti su VSIX extension schema 1.0](https://msdn.microsoft.com/library/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [Anatomia di un pacchetto VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Preparare le estensioni per la distribuzione di Windows Installer](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
