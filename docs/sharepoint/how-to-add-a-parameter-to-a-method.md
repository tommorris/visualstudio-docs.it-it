---
title: 'Procedura: aggiungere un parametro a un metodo | Microsoft Docs'
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
- Business Data Connectivity service [SharePoint development in Visual Studio], adding a method to a parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter
- BDC [SharePoint development in Visual Studio], adding a method to a parameter
- BDC [SharePoint development in Visual Studio], parameter
- Business Data Connectivity service [SharePoint development in Visual Studio], method parameters
- BDC [SharePoint development in Visual Studio], method parameters
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 196ac37cc9bc4f53cfa886b92c62c7a301c3451a
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756311"
---
# <a name="how-to-add-a-parameter-to-a-method"></a>Procedura: aggiungere un parametro a un metodo
  Usare un parametro per passare le informazioni nel metodo o per restituire informazioni da un metodo. Tutti i metodi devono avere almeno un parametro. Per altre informazioni su come progettare un parametro per supportare il tipo di metodo che si desidera creare, vedere [progettare un Business Data Connectivity Model](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Quando si aggiunge un parametro a un metodo, Visual Studio aggiunge l'elemento del parametro al codice XML del file modello nel progetto. Per altre informazioni sugli attributi di un elemento di parametro, vedere [parametro](http://go.microsoft.com/fwlink/?LinkId=169284).  
  
### <a name="to-add-a-parameter-to-a-method"></a>Per aggiungere un parametro a un metodo  
  
1.  Aggiungere un metodo a un'entità.  
  
2.  Nella barra dei menu, scegliere **View** > **Other Windows** > **Dettagli metodo BDC**.  
  
     Il **Dettagli metodo BDC** verrà visualizzata la finestra. Per altre informazioni, vedere [panoramica degli strumenti di progettazione modello di integrazione applicativa dei dati](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  Nel **Dettagli metodo BDC** finestra, espandere il nodo del metodo e quindi espandere il **parametri** nodo.  
  
4.  Nel **aggiungere un parametro** casella di riepilogo **Crea parametro**.  
  
     Un nuovo parametro verrà visualizzata sotto il **parametri** nodo.  
  
5.  Nella barra dei menu, scegliere **View** > **finestra proprietà**.  
  
6.  Nel **delle proprietà** impostare nella finestra di **nome** proprietà a un nome significativo. Ad esempio, se il metodo restituirà i clienti, è possibile denominare il metodo **GetCustomers**.  
  
7.  Nel **Dettagli metodo BDC** finestra, aprire l'elenco visualizzato per la direzione del parametro e quindi scegliere **nelle**, **InOut**, **Out**, oppure **restituire**.  
  
     Per altre informazioni sulla direzione in cui scegliere per il metodo del tipo che si sta creando, vedere [progettare un modello di integrazione applicativa dei dati business](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
8.  Modificare il descrittore di tipo del parametro. Per altre informazioni, vedere [procedura: definire il descrittore di tipo di parametro](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
## <a name="see-also"></a>Vedere anche
 [Panoramica degli strumenti di progettazione modello di integrazione applicativa dei dati](../sharepoint/bdc-model-design-tools-overview.md)   
 [Procedura: aggiungere un'entità a un modello](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Procedura: definire il descrittore di tipo di parametro](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [Procedura: definire un'istanza del metodo](../sharepoint/how-to-define-a-method-instance.md)   
 [Progettare un modello di integrazione applicativa dei dati business](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
