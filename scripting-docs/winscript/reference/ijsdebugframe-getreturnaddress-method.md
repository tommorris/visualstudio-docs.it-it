---
title: 'Metodo ijsdebugframe:: Getreturnaddress | Documenti Microsoft'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetReturnAddress
apilocation:
- jscript9diag.dll
ms.assetid: 7f10c1d6-d7b9-402e-9020-04cded37f9d3
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9d2b78f049a080f70b30edb82af1066817f6adb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2017
ms.locfileid: "24727701"
---
# <a name="ijsdebugframegetreturnaddress-method"></a>Metodo IJsDebugFrame::GetReturnAddress
Ottiene l'indirizzo del mittente inserito all'inizio' ' (vedere GetStackRange) del frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetReturnAddress(  
   UINT64 *pReturnAddress  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pReturnAddress`  
 [out] Indirizzo del mittente.  
  
## <a name="return-value"></a>Valore restituito  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** jscript9diag  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IJsDebugFrame](../../winscript/reference/ijsdebugframe-interface.md)