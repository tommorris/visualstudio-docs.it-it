---
title: Scheda File di paging, finestra di dialogo Proprietà processo | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: daf41a06-8a55-48f6-95f5-49a8416bd308
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 624be76badf8d57b060198c2ee910ead17b5efcb
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
ms.locfileid: "31472968"
---
# <a name="page-file-tab-process-properties-dialog-box"></a>Scheda File di paging, finestra di dialogo Proprietà processo
Utilizzare il **File di paging** scheda per esaminare il file di paging di un processo. Per visualizzare il [finestra di dialogo Proprietà processo](../debugger/process-properties-dialog-box.md), spostare lo stato attivo per un [visualizzazione processi](../debugger/processes-view.md) finestra. Selezionare qualsiasi nodo del processo nell'albero, quindi scegliere **proprietà** dal **vista** menu.  
  
 Le impostazioni seguenti sono disponibili sul **File di paging** scheda:  
  
|Voce|Descrizione|  
|-----------|-----------------|  
|**Byte File di paging**|Il numero corrente di pagine che utilizza questo processo nel file di paging. Il file di paging archivia le pagine di dati utilizzata dal processo ma non contenute in altri file. Il file di paging viene usato da tutti i processi e mancanza di spazio nel file di paging può causare errori durante l'eseguono di altri processi.|  
|**Numero massimo byte di File di paging**|Il numero massimo di pagine in cui il processo ha usato nel file di paging.|  
|**Errori di pagina**|Il numero di errori di pagina nei thread di questo processo. Quando un thread fa riferimento a una pagina di memoria virtuale che non è presente nel working set nella memoria principale, si verifica un errore di pagina. Di conseguenza, la pagina non essere richiamata dal disco se è presente nell'elenco standby e quindi già nella memoria principale o se è in uso da un altro processo con cui la pagina è condivisa.|