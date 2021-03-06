---
title: Formattare gli identificatori nel debugger (c#) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- expressions [C#], formatting values
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- specifiers, watch variable format
- QuickWatch dialog box, format specifiers in C#
- specifiers
- watch variable symbols
- Watch window, format specifiers in C#
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 345c8589-5f36-4d34-a58c-e56271687dd6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0e8605671d1c245826ce6d699e91795fcd7ee32e
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756860"
---
# <a name="format-specifiers-in-c-in-the-visual-studio-debugger"></a>Identificatori di formato in c# il debugger di Visual Studio
È possibile modificare il formato con cui viene visualizzato il valore nella finestra **Espressioni di controllo** usando gli identificatori di formato. È anche possibile usare gli identificatori di formato nel **controllo immediato** finestra, il **comando** finestra, in [i punti di analisi](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)e persino nelle finestre di origine. Se in queste finestre ci si posiziona su un'espressione, il risultato verrà visualizzato in un suggerimento dati. I suggerimenti dati riflettono l'identificatore di formato nella visualizzazione Suggerimento dati.  
  
 Per usare un identificatore di formato, digitare l'espressione seguita da una virgola e dall'identificatore appropriato.  
  
## <a name="using-format-specifiers"></a>Uso degli identificatori di formato  
 Se si ha il codice seguente:  
  
```csharp  
{  
        int my_var1 = 0x0065;  
        int my_var2 = 0x0066;  
        int my_var3 = 0x0067;  
}  
```  
  
 Aggiungere il `my_var1` variabile alla finestra Espressioni di controllo (durante il debug **Debug > Windows > espressioni di controllo > espressione di controllo 1**) e impostare la visualizzazione su esadecimale (nel **Watch** finestra, fare doppio clic la variabile e Selezionare **visualizzazione esadecimale**). La finestra **Espressioni di controllo** mostra il valore 0x0065. Per visualizzare questo valore espresso come intero decimale invece che intero esadecimale, aggiungere l'identificatore di formato decimale dopo la variabile del nome nella colonna Nome: **, d**. La colonna Valore visualizza il valore decimale 101  
  
 ![WatchFormatCSharp](../debugger/media/watchformatcsharp.png "WatchFormatCSharp")  
  
## <a name="format-specifiers"></a>Identificatori di formato  
 Nella tabella riportata di seguito sono elencati gli identificatori di formato C# riconosciuti dal debugger.  
  
|Identificatore|Formato|Valore dell'espressione di controllo originale|Visualizza|  
|---------------|------------|--------------------------|--------------|  
|ac|Impone la valutazione di un'espressione. Può risultare utile quando la valutazione implicita di proprietà e di chiamate di funzione implicite è disattivata.|Messaggio "valutazione della funzione implicita è stata disattivata dall'utente"|\<valore >|  
|d|intero decimale|0x0065|101|  
|dynamic|Visualizza l'oggetto specificato usando una visualizzazione dinamica|Visualizza tutti i membri dell'oggetto, inclusa la visualizzazione dinamica|Visualizza solo la visualizzazione dinamica|  
|h|intero esadecimale|61541|0x0000F065|  
|nq|stringa senza virgolette|"Stringa"|Stringa|  
|protocollo nSe|Specifica il comportamento, non di formato. Valuta l'espressione "Senza effetti collaterali". Se l'espressione non può essere interpretato e può essere risolti solo da una versione di valutazione (ad esempio, una chiamata di funzione), si verrà visualizzato un errore.|N/D|N/D|
|hidden|Visualizza tutti i membri pubblici e non pubblici|Visualizza i membri pubblici|Visualizza tutti i membri|  
|raw|Visualizza l'elemento così come appare nel nodo degli elementi non elaborati. Valido unicamente sugli oggetti proxy.|Dizionario\<T >|Visualizzazione non elaborata di Dictionary\<T >|  
|results|Utilizzato con una variabile di un tipo che implementa IEnumerable o IEnumerable\<T >, generalmente il risultato di un'espressione di query. Visualizza solo i membri che contengono il risultato della query.|Visualizza tutti i membri.|Visualizza i membri che soddisfano le condizioni della query.|  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni di controllo e controllo immediato Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Finestre Auto e Variabili locali](../debugger/autos-and-locals-windows.md)
