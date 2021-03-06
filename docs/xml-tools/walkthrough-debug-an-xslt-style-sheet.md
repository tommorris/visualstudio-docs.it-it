---
title: 'Procedura dettagliata: eseguire il debug di un foglio di stile XSLT'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 3db9fa5a-f619-4cb6-86e7-64b364e58e5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ebc8e8f8700690a2ae74fcc91384fb77b238ea33
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693396"
---
# <a name="walkthrough-debug-an-xslt-style-sheet"></a>Procedura dettagliata: Debug di un foglio di stile XSLT

Nei passaggi della procedura dettagliata viene illustrato come usare il debugger XSLT. I passaggi comprendono la visualizzazione delle variabili, l'impostazione dei punti di interruzione e l'esecuzione del codice un'istruzione alla volta. Nel foglio di stile vengono elencati tutti i libri con prezzo inferiore a quello del libro medio.

## <a name="to-prepare-for-this-walkthrough"></a>Operazioni preliminari per la procedura dettagliata

1.  Chiudere eventuali soluzioni aperte.

2.  Copiare i due file di esempio nel computer locale.

## <a name="start-debugging"></a>Avvia debug

### <a name="to-start-debugging"></a>Per avviare il debug

1.  Dal **File** dal menu **aprire**, fare clic su **File**.

2.  Individuare il *belowAvg* del file e fare clic su **Apri**.

     Il foglio di stile viene aperto nell'editor XML.

3.  Fare clic sul pulsante Sfoglia (**...** ) nei **Input** campo della finestra delle proprietà del documento.

4.  Individuare il *Books* del file e fare clic su **Apri**.

     In questo modo viene impostato il file del documento di origine usato per la trasformazione XSLT.

5.  Fare doppio clic su di `xsl:if` tag di inizio, scegliere **punto di interruzione**, fare clic su **Inserisci punto di interruzione**.

6.  Fare clic su di **Debug XSLT** pulsante sulla barra degli strumenti Editor XML.

Verrà avviato il processo di debug e verranno aperte diverse nuove finestre usate dal debugger.

In due finestre vengono visualizzati il documento di input e il foglio di stile. Il debugger usa queste finestre per mostrare lo stato di esecuzione corrente Il debugger è posizionato in corrispondenza di `xsl:if` elemento del foglio di stile e sul primo nodo libro nel *Books* file.

Il **variabili locali** finestra Visualizza tutte le variabili locali e i relativi valori correnti. incluse le variabili definite nel foglio di stile e quelle usate dal debugger per tenere traccia dei nodi presenti nel contesto.

Il **Output XSL** finestra Visualizza l'output della trasformazione XSL. Questa finestra è separata dal **Output di Visual Studio** finestra.

## <a name="watch-window"></a>Finestra Espressioni di controllo

### <a name="to-use-the-watch-window"></a>Per usare la finestra Espressioni di controllo

1.  Dal **Debug** dal menu **Windows**, scegliere **espressioni di controllo**, fare clic su **controllo1**.

     In questo modo, il **controllo1** finestra visibile.

2.  Tipo di `$bookAverage` nella **nome** campo e premere **invio**.

     Il valore della variabile `$bookAverage` viene visualizzato nella finestra.

3.  Tipo di `self::node()` nella **nome** campo e premere **invio**.

     `self::node()` è un'espressione XPath che restituisce il nodo di contesto corrente. Il valore dell'espressione XPath `self::node()` costituisce il primo nodo libro.  Il valore verrà modificato durante le fasi della trasformazione.

4.  Espandere il nodo `self::node()`, quindi il nodo `price`.

     Ciò consente di visualizzare il valore del prezzo del libro e di confrontarlo facilmente con il valore `$bookAverage`. Poiché il prezzo del libro è maggiore del prezzo medio, la condizione `xsl:if` dovrebbe essere eseguita correttamente.

## <a name="step-through-the-code"></a>Eseguire il codice
 Il debugger consente di eseguire il codice una riga alla volta.

### <a name="to-step-through-the-code"></a>Per eseguire il codice un'istruzione alla volta

1.  Premere **F5** per continuare.

     Poiché il primo nodo libro soddisfatti il `xsl:if` condizione, il nodo libro viene aggiunto per il **Output XSL** finestra. Il debugger continua l'esecuzione se non viene posizionato di nuovo sull'elemento `xsl:if` nel foglio di stile. Il debugger è ora posizionato sul secondo nodo libro nel *Books* file.

     Nel **controllo1** finestra di `self::node()` valore viene modificato nel secondo nodo libro. Analizzando il valore dell'elemento prezzo, è possibile determinare che il prezzo è maggiore del prezzo medio e che pertanto la condizione `xsl:if` non dovrebbe essere eseguita correttamente.

2.  Premere **F5** per continuare.

     Poiché il secondo nodo libro non soddisfa il `xsl:if` condizione, il nodo libro non viene aggiunto per il **Output XSL** finestra. Il debugger continua l'esecuzione se non viene posizionato di nuovo sull'elemento `xsl:if` nel foglio di stile. Il debugger è ora posizionato sul terzo `book` nodo il *Books* file.

     Nel **controllo1** finestra di `self::node()` valore viene modificato nel terzo nodo libro. Analizzando il valore dell'elemento `price`, è possibile determinare che il prezzo è inferiore al prezzo medio e che pertanto la condizione `xsl:if` dovrebbe essere eseguita correttamente.

3.  Premere **F5** per continuare.

     Poiché il `xsl:if` condizione è soddisfatta, il terzo libro viene aggiunto per il **Output XSL** finestra. Tutti i libri nel documento XML sono stati elaborati e il debugger si arresta.

## <a name="sample-files"></a>File di esempio

I due file seguenti vengono usati nella procedura dettagliata.

### <a name="belowavgxsl"></a>belowAvg.xsl

```xml
<?xml version='1.0'?>
<xsl:stylesheet version="1.0"
      xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output method="xml" encoding="utf-8"/>
  <xsl:template match="/">
    <xsl:variable name="bookCount" select="count(/bookstore/book)"/>
    <xsl:variable name="bookTotal" select="sum(/bookstore/book/price)"/>
    <xsl:variable name="bookAverage" select="$bookTotal div $bookCount"/>
    <books>
      <!--Books That Cost Below Average-->
      <xsl:for-each select="/bookstore/book">
        <xsl:if test="price < $bookAverage">
          <xsl:copy-of select="."/>
        </xsl:if>
      </xsl:for-each>
    </books>
  </xsl:template>
</xsl:stylesheet>
```

### <a name="booksxml"></a>books.xml

```xml
<?xml version='1.0'?>
<!-- This file represents a fragment of a book store inventory database -->
<bookstore>
  <book genre="autobiography" publicationdate="1981" ISBN="1-861003-11-0">
    <title>The Autobiography of Benjamin Franklin</title>
    <author>
      <first-name>Benjamin</first-name>
      <last-name>Franklin</last-name>
    </author>
    <price>8.99</price>
  </book>
  <book genre="novel" publicationdate="1967" ISBN="0-201-63361-2">
    <title>The Confidence Man</title>
    <author>
      <first-name>Herman</first-name>
      <last-name>Melville</last-name>
    </author>
    <price>11.99</price>
  </book>
  <book genre="philosophy" publicationdate="1991" ISBN="1-861001-57-6">
    <title>The Gorgias</title>
    <author>
      <name>Plato</name>
    </author>
    <price>9.99</price>
  </book>
</bookstore>
```

## <a name="see-also"></a>Vedere anche

- [Debug di fogli di stile XSLT (Extensible Stylesheet Language Transformation)](../xml-tools/debugging-xslt.md)