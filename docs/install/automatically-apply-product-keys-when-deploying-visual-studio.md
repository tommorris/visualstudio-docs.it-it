---
title: Applicare automaticamente i codici Product Key durante la distribuzione di Visual Studio
description: Informazioni sulla procedura di applicazione dei codici Product Key a livello di programmazione durante la distribuzione di Visual Studio.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fea2ffa8fd81a5012c89289df36d7f698fb60c4e
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138716"
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Applicare automaticamente i codici Product Key durante la distribuzione di Visual Studio

È possibile applicare il codice Product Key a livello di programmazione come parte dello script utilizzato per automatizzare la distribuzione di Visual Studio. È possibile impostare i codici Product Key su un dispositivo a livello di programmazione durante l'installazione di Visual Studio o al termine dell'installazione.

## <a name="apply-the-license-after-installation"></a>Applicare la licenza dopo l'installazione

 È possibile attivare una versione installata di Visual Studio con un codice Product Key tramite l'utilità `StorePID.exe` nei computer di destinazione in modalità invisibile all'utente. `StorePID.exe` è un programma di utilità che viene installato con Visual Studio 2017 nel percorso predefinito seguente: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 Eseguire `StorePID.exe` con privilegi elevati, usando un agente System Center o un prompt dei comandi con privilegi elevati. Continuare quindi con il codice Product Key (con i trattini) e il codice Microsoft Product Code (MPC).

>[!IMPORTANT]
> Assicurarsi di includere i trattini nel codice Product Key.

 ```cmd
 StorePID.exe [product key including the dashes] [MPC]
 ```

 In questo esempio è riportata una riga di comando per l'applicazione della licenza di Visual Studio 2017 Enterprise, con codice MPC 08860 e codice Product Key `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`, presupponendone l'installazione in un percorso predefinito:

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 La tabella seguente riporta i codici MPC per ogni edizione di Visual Studio:

| Edizione di Visual Studio                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

Se `StorePID.exe` applica correttamente il codice Product Key, restituisce un `%ERRORLEVEL%` pari a 0. Se si verificano errori, verrà restituito uno dei codici seguenti, a seconda della condizione di errore:

| Error                     | Codice |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Vedere anche

* [Installare Visual Studio](../install/install-visual-studio.md)
* [Creare un'installazione offline di Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)
