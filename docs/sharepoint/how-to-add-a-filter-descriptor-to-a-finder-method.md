---
title: 'Procedura: aggiungere un descrittore di filtro a un metodo Finder | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], filter descriptors
- Business Data Connectivity service [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], add a filter
- BDC [SharePoint development in Visual Studio], filter descriptors
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 63374f4d96c86ea3eafbd4c6fa3fbe3d1f5a5899
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755599"
---
# <a name="how-to-add-a-filter-descriptor-to-a-finder-method"></a>Procedura: aggiungere un descrittore di filtro a un metodo Finder
  Descrittori di filtro consentono ai consumer del modello passare valori ai metodi prima che vengano eseguiti. Per altre informazioni, vedere [progettare un modello di integrazione applicativa dei dati business](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Uno scenario comune è che gli utenti di SharePoint recuperare le istanze di un tipo di contenuto esterno che corrispondono a certi criteri. È possibile supportare questo scenario tramite l'aggiunta di un descrittore di filtro a un metodo Finder.  
  
### <a name="to-add-a-filter-descriptor-to-a-finder-method"></a>Per aggiungere un descrittore di filtro a un metodo Finder  
  
1.  Nel **Dettagli metodo BDC** finestra, espandere il nodo di un metodo Finder, il **parametri** nodo e quindi aggiungere un parametro di input. Per altre informazioni, vedere [procedura: aggiungere un parametro a un metodo](../sharepoint/how-to-add-a-parameter-to-a-method.md).  
  
2.  Nel **Dettagli metodo** finestra, scegliere il descrittore di tipo del parametro.  
  
3.  Nella barra dei menu, scegliere **View** > **finestra proprietà**.  
  
4.  Nel **proprietà** impostare nella finestra di **nome tipo** proprietà a un tipo di dati che è appropriato per il filtro.  
  
     Ad esempio, un filtro potrebbe usare una data di ordine per limitare il numero di ordini di vendita restituiti dal metodo. Per supportare tale filtro, il **nome del tipo** proprietà del descrittore del tipo deve essere impostata su **System. DateTime**.  
  
5.  Nel **Dettagli metodo** finestra, espandere il **descrittori di filtro** nodo.  
  
6.  Nelle **aggiungere un descrittore di filtro** casella di riepilogo **Crea descrittore di filtro**.  
  
     Un nuovo descrittore di filtro viene visualizzato sotto il **descrittori di filtro** nodo.  
  
7.  Nella barra dei menu, scegliere **View** > **finestra proprietà**.  
  
8.  Nel **delle proprietà** finestra, scegliere il **tipo** proprietà.  
  
9. Nell'elenco visualizzato per il **tipo** proprietà, scegliere il criterio di filtro desiderati.  
  
     Ad esempio, per creare un filtro che usa una data di ordine per limitare il numero di ordini di vendita restituiti in un metodo Finder, scegliere **confronto**. Un filtro di confronto assicura che un metodo finder restituisce solo le istanze che soddisfano una condizione specifica. Per altre informazioni su ogni modello di filtro, vedere [tipi di filtri supportati per l'integrazione applicativa dei dati](http://go.microsoft.com/fwlink/?LinkId=169287).  
  
10. Nel **delle proprietà** finestra, scegliere il **associati descrittori di tipo** proprietà.  
  
11. Nell'elenco visualizzato per il **descrittori di tipo associati** proprietà, scegliere il descrittore di tipi che è stato creato in precedenza in questa procedura. Il filtro verrà associato al parametro di input del metodo Finder.  
  
12. Aggiungere codice al metodo di ricerca che restituisce i dati. È possibile usare il parametro di input come una condizione in una query select.  
  
     L'esempio seguente restituisce gli ordini di vendita che hanno la data dell'ordine specificato.  
  
    > [!NOTE]  
    >  Sostituire il valore del `ServerName` campo con il nome del server.  
  
     [!code-csharp[SP_BDC#11](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderservice.cs#11)]
     [!code-vb[SP_BDC#11](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderservice.vb#11)]  
  
## <a name="see-also"></a>Vedere anche
 [Procedura: aggiungere un metodo Finder](../sharepoint/how-to-add-a-finder-method.md)   
 [Procedura: aggiungere un metodo Finder specifico](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Procedura: aggiungere un parametro a un metodo](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Procedura: definire il descrittore di tipo di parametro](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Progettare un modello di integrazione applicativa dei dati business](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Integrazione di dati aziendali in SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  
