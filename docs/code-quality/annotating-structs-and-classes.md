---
title: Annotazioni di struct e classi
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Field_size_bytes_part_
- _Field_size_bytes_full_opt_
- _Field_size_bytes_
- _Field_size_opt_
- _Field_size_part_
- _Field_size_bytes_part_opt_
- _Field_range_
- _Field_size_part_opt_
- _Field_size_
- _Field_size_bytes_opt_
- _Struct_size_bytes_
- _Field_size_bytes_full_
- _Field_size_full_
- _Field_size_full_opt_
- _Field_z_
ms.assetid: b8278a4a-c86e-4845-aa2a-70da21a1dd52
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: e4294284ff2911fd05cc771bf4deaad368e3c28b
ms.sourcegitcommit: 95aedf723c6be5272c3c5a2911cb2bdec50e2148
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47228825"
---
# <a name="annotating-structs-and-classes"></a>Annotazioni di struct e classi
È possibile annotare i membri struct e di classe utilizzando le annotazioni che operano come invarianti, si presume che siano true per qualsiasi chiamata di funzione o entrata/uscita di funzione che include la struttura contenitore come parametro o valore restituito.

## <a name="struct-and-class-annotations"></a>Annotazioni di classi e struct

-   `_Field_range_(low, high)`

     Il campo è compreso nell'intervallo (inclusivo) dal `low` a `high`.  Equivalente ad applicare `_Satisfies_(_Curr_ >= low && _Curr_ <= high)` all'oggetto annotato utilizzando le pre/postcondizioni appropriate.

-   `_Field_size_(size)`, `_Field_size_opt_(size)`, `_Field_size_bytes_(size)`, `_Field_size_bytes_opt_(size)`

     Campo con una dimensione scrivibile in elementi (o byte) come specificato da `size`.

-   `_Field_size_part_(size, count)`, `_Field_size_part_opt_(size, count)`,         `_Field_size_bytes_part_(size, count)`, `_Field_size_bytes_part_opt_(size, count)`

     Campo con una dimensione scrivibile in elementi (o byte) come specificato da `size` e `count` degli elementi (byte) che sono leggibili.

-   `_Field_size_full_(size)`, `_Field_size_full_opt_(size)`, `_Field_size_bytes_full_(size)`, `_Field_size_bytes_full_opt_(size)`

     Campo che contiene sia dimensione leggibile che modificabile in elementi (o byte) come specificato da `size`.

-   `_Field_z_`

     Un campo contenente una stringa con terminazione null.

-   `_Struct_size_bytes_(size)`

     Si applica alla dichiarazione di classe o struct.  Indica che un oggetto valido di tale tipo può essere maggiore rispetto al tipo dichiarato, con il numero di byte specificati da `size`.  Ad esempio:

    ```cpp

    typedef _Struct_size_bytes_(nSize)
    struct MyStruct {
        size_t nSize;
        ...
    };

    ```

     Le dimensioni del buffer in byte di un parametro `pM` di tipo `MyStruct *` viene quindi considerato:

    ```cpp
    min(pM->nSize, sizeof(MyStruct))
    ```

## <a name="see-also"></a>Vedere anche
 [Uso delle annotazioni SAL per ridurre i difetti del codice C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md) [comprensione SAL](../code-quality/understanding-sal.md) [annotazione di parametri di funzione e valori restituiti](../code-quality/annotating-function-parameters-and-return-values.md) [annotazione del comportamento della funzione](../code-quality/annotating-function-behavior.md) [Annotazione del comportamento di blocco](../code-quality/annotating-locking-behavior.md) [specificare dove e quando applicare un'annotazione](../code-quality/specifying-when-and-where-an-annotation-applies.md) [funzioni intrinseche](../code-quality/intrinsic-functions.md) [procedure consigliate e Esempi](../code-quality/best-practices-and-examples-sal.md)
