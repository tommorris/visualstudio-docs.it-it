---
title: IDebugClassField::GetDefaultIndexer | Documenti Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f16f4dc94a5019fa66425f55c8f7706db566db9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101535"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
Ottiene il nome dell'indicizzatore predefinita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDefaultIndexer(   
   BSTR* pbstrIndexer  
);  
```  
  
```csharp  
int GetDefaultIndexer(  
   out string pbstrIndexer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbstrIndexer`  
 [out] Restituisce una stringa contenente il nome dell'indicizzatore predefinita.  
  
## <a name="return-value"></a>Valore restituito  
 Se ha esito positivo, restituisce S_OK o restituisce S_FALSE se non esiste alcun indicizzatore predefinito. In caso contrario, verrà restituito un codice di errore.  
  
## <a name="remarks"></a>Note  
 L'indicizzatore predefinito di una classe è la proprietà che è contrassegnata come il `Default` proprietà per gli accessi di matrice. Questa operazione è specifica per [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]. Di seguito è riportato un esempio di un indicizzatore predefinito dichiarato in [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] e come utilizzarlo.  
  
```vb  
Imports System.Collections;  
  
Public Class Class1  
    Private myList as Hashtable  
  
    Default Public Property Item(ByVal Index As Integer) As Integer  
        Get  
            Return CType(List(Index), Integer)  
        End Get  
        Set(ByVal Value As Integer)  
            List(Index) = Value  
        End Set  
    End Property  
End Class  
  
Function GetItem(Index as Integer) as Integer  
    Dim classList as Class1 = new Class1  
    Dim value as Integer  
  
    ' Access array through default indexer  
    value = classList(2)  
  
    ' Access array through explicit property  
    value = classList.Item(2)  
  
    Return value  
End Function  
```  
  
## <a name="see-also"></a>Vedere anche  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)