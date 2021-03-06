---
title: Funzione SccBeginBatch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f9593496f36fba4a56334a206cf39e9a6ad96ad2
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639789"
---
# <a name="sccbeginbatch-function"></a>Funzione SccBeginBatch
Questa funzione avvia una sequenza di batch di operazioni di controllo codice sorgente. Il [SccEndBatch](../extensibility/sccendbatch-function.md) verrà chiamato per terminare il batch. Questi batch non possono essere annidati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
### <a name="parameters"></a>Parametri  
 Nessuno.  
  
## <a name="return-value"></a>Valore restituito  
 Implementazione di plug-in del controllo dell'origine di questa funzione deve restituire uno dei valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|SCC_OK|Batch di operazioni completata è stata avviata.|  
|SCC_E_UNKNOWNERROR|Errore non specifico.|  
  
## <a name="remarks"></a>Note  
 Batch di controllo di origine utilizzati per eseguire le stesse operazioni in più progetti o più contesti. Batch sono utilizzabile per eliminare finestre di dialogo per ogni progetto ridondanti rispetto all'esperienza utente durante un'operazione batch. Il `SccBeginBatch` funzione e il [SccEndBatch](../extensibility/sccendbatch-function.md) vengono utilizzati come una coppia di funzione per indicare l'inizio e alla fine di un'operazione. Non possono essere annidate. `SccBeginBatch` imposta un flag che indica che un'operazione batch è in corso.  
  
 Mentre è attiva un'operazione batch, il plug-in del controllo del codice sorgente debba presentare al massimo una finestra di dialogo per qualsiasi domanda all'utente e applicare la risposta da questa finestra di dialogo in tutte le operazioni successive.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni API del plug-in origine controllo](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)