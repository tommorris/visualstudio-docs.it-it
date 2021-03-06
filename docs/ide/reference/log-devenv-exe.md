---
title: -Log (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3373f1e1a23ae0373a9c49a39a924398ebe143e0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704772"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Registra tutte le attività nel file di log per la risoluzione dei problemi. Il file verrà visualizzato dopo aver chiamato `devenv /log` almeno una volta. Per impostazione predefinita, il file di log è:

 *%APPDATA%* \Microsoft\VisualStudio\\*Versione*\ActivityLog.xml

 dove *Versione* indica la versione di Visual Studio. È tuttavia possibile specificare un percorso e un nome di file diversi.

## <a name="syntax"></a>Sintassi

```cmd
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>Note
 Questa opzione deve apparire alla fine della riga di comando, dopo tutte le altre opzioni.

 Il log viene scritto per tutte le istanze di Visual Studio richiamate con l'opzione /log. Non vengono registrate le istanze di Visual Studio richiamate senza l'opzione /log.

## <a name="see-also"></a>Vedere anche

- [Opzioni della riga di comando devenv](../../ide/reference/devenv-command-line-switches.md)