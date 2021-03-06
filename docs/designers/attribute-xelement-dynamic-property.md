---
title: Attributo (proprietà dinamica XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: caacdd787f1765721d281db885364aafc36c5183
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "37890009"
---
# <a name="attribute-xelement-dynamic-property"></a>Attributo (proprietà dinamica XElement)

Ottiene un indicizzatore usato per recuperare l'istanza dell'attributo che corrisponde al nome espanso specificato.

## <a name="syntax"></a>Sintassi

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito

Indicizzatore del tipo `XAttribute Item(String expandedName)`. Questo indicizzatore accetta il nome espanso dell'attributo specificato e restituisce l'oggetto <xref:System.Xml.Linq.XAttribute> corrispondente o `null` se non esiste nessun attributo con il nome specificato.

## <a name="remarks"></a>Note

Questa proprietà è equivalente al metodo <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [Proprietà dinamiche della classe XElement](../designers/xelement-class-dynamic-properties.md)
- [Valore](../designers/value-xattribute-dynamic-property.md)