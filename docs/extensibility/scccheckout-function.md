---
title: Funzione SccCheckout | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccCheckout
helpviewer_keywords:
- SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 50e82c04dc9dda306d8c9204aad6606dff6f89c7
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2018
ms.locfileid: "39635915"
---
# <a name="scccheckout-function"></a>Funzione SccCheckout
Dato un elenco di nomi completi dei file, questa funzione li estrae nell'unità locale. Il commento viene applicata a tutti i file in corso l'estrazione. L'argomento commento può essere un `null` stringa.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
### <a name="parameters"></a>Parametri  
 pvContext  
 [in] La struttura del contesto plug-in del controllo origine.  
  
 hWnd  
 [in] Handle per la finestra dell'IDE che il plug-in del controllo del codice sorgente è possibile utilizzare come padre per le finestre di dialogo che fornisce.  
  
 nFile  
 [in] Numero di file selezionati da estrarre.  
  
 lpFileNames  
 [in] Matrice di nomi di percorso locale completo dei file da estrarre.  
  
 lpComment  
 [in] Commento da applicare a ognuno dei file selezionati in corso l'estrazione.  
  
 Opzioni  
 [in] Flag di comando (vedere [flag di bit usati da comandi specifici](../extensibility/bitflags-used-by-specific-commands.md)).  
  
 pvOptions  
 [in] Opzioni specifiche plug-in controllo sorgente.  
  
## <a name="return-value"></a>Valore restituito  
 Implementazione di plug-in del controllo dell'origine di questa funzione deve restituire uno dei valori seguenti:  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|SCC_OK|Check-out è stato completato.|  
|SCC_E_FILENOTCONTROLLED|Il file selezionato non è incluso nel controllo del codice sorgente.|  
|SCC_E_ACCESSFAILURE|Si è verificato un problema di accesso di sistema di controllo di origine, probabilmente a causa di problemi di contesa o di rete. È consigliabile un nuovo tentativo.|  
|SCC_E_NOTAUTHORIZED|L'utente non è autorizzato a eseguire questa operazione.|  
|SCC_E_NONSPECIFICERROR|Errore non specifico. Il file non è stato estratto.|  
|SCC_E_ALREADYCHECKEDOUT|L'utente ha già estratto il file.|  
|SCC_E_FILEISLOCKED|Il file è bloccato, che vieta la creazione di nuove versioni.|  
|SCC_E_FILEOUTEXCLUSIVE|Un altro utente ha eseguito un'estrazione esclusiva su questo file.|  
|SCC_I_OPERATIONCANCELED|L'operazione è stata annullata prima del completamento.|  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni API del plug-in origine controllo](../extensibility/source-control-plug-in-api-functions.md)   
 [Flag di bit usati da comandi specifici](../extensibility/bitflags-used-by-specific-commands.md)