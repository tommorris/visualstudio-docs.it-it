---
title: Come è possibile eseguire il Debug di una violazione di accesso C++? | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 9311d754-0ce9-4145-b147-88b6ca77ba63
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: b131ba4acf761a11aa9f39807d1db3202b021c9d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
ms.locfileid: "31475350"
---
# <a name="how-can-i-debug-a-c-access-violation"></a>Come è possibile eseguire il Debug di una violazione di accesso C++?
## <a name="problem-description"></a>Descrizione del problema  
 Il programma genera una violazione di accesso. Come è possibile effettuarne il debug?  
  
## <a name="solution"></a>Soluzione  
 Se si riceve un avviso di violazione di accesso su una riga di codice che dereferenzia più puntatori, può essere difficile individuare il puntatore che ha causato la violazione di accesso. A partire da Visual Studio 2015 Update 1, la finestra di dialogo di eccezione ora specifica esplicitamente il puntatore che ha causato la violazione di accesso.  
  
 Ad esempio, con il codice seguente si dovrebbe ottenere una violazione di accesso:  
  
```C++  
#include <iostream>  
using namespace std;  
  
class ClassB {  
public:  
        ClassC* C;  
        ClassB() {  
                C = new ClassC();  
        }  
     void printHello() {  
                cout << "hello world";  
        }  
};  
  
class ClassA {  
public:  
    ClassB* B;  
      ClassA() {  
                B = nullptr;  
        }  
};  
  
int main() {  
    ClassA* A = new ClassA();  
      A->B->printHello();  
}  
```  
  
 Se si esegue questo codice in Visual Studio 2015 Update 1, dovrebbe comparire la finestra di dialogo di eccezione seguente:  
  
 ![AccessViolationCPlus](../debugger/media/accessviolationcplus.png "AccessViolationCPlus")  
  
 Se non è possibile determinare perché il puntatore ha causato una violazione di accesso, tracciare il codice per assicurarsi che il puntatore che provoca il problema sia stato assegnato correttamente.  Se viene passato come parametro, assicurarsi che viene passato in modo corretto e che non si accidentalmente un [superficialmente copia](http://stackoverflow.com/questions/184710/what-is-the-difference-between-a-deep-copy-and-a-shallow-copy). Verificare che i valori non sono vengano involontariamente modificati in un punto nel programma tramite la creazione di un punto di interruzione dei dati per il puntatore in questione per assicurarsi che non venga modificato altrove nel programma. Per ulteriori informazioni sui punti di interruzione dei dati, vedere la relativa sezione in [Using Breakpoints](../debugger/using-breakpoints.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Domande frequenti sul debug del codice nativo](../debugger/debugging-native-code-faqs.md)