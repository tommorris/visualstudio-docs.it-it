---
title: Funzione SccCloseProject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccCloseProject
helpviewer_keywords:
- SccCloseProject function
ms.assetid: 259c2069-d349-4814-810f-1c3151b7fb84
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 49d3196fbe2eb6c3bafa1ec234e27072e50a4b7d
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636025"
---
# <a name="scccloseproject-function"></a>Funzione SccCloseProject
Questa funzione consente di chiudere un progetto, contrassegna la fine di una determinata sessione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
SCCRTN SccCloseProject (  
   LPVOID pvContext  
);  
```  
  
### <a name="parameters"></a>Parametri  
 pvContext  
 La struttura del contesto plug-in del controllo origine.  
  
## <a name="return-value"></a>Valore restituito  
 Implementazione di plug-in del controllo dell'origine di questa funzione deve restituire uno dei valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|SCC_OK|Il progetto è stato chiuso.|  
|SCC_E_PROJNOTOPEN|Nessun progetto è aperto.|  
|SCC_E_NOTAUTHORIZED|L'utente non è autorizzato a eseguire questa operazione.|  
|SCC_E_NONSPECIFICERROR|Errore non specifico.|  
  
## <a name="remarks"></a>Note  
 Il [SccOpenProject](../extensibility/sccopenproject-function.md) viene sempre chiamato prima di questa funzione. Una chiamata a questa funzione viene quindi seguita da una chiamata a uno il `SccOpenProject` funzione o il [SccUninitialize](../extensibility/sccuninitialize-function.md), che termina la connessione al sistema di controllo di origine completamente.  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni API del plug-in origine controllo](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)