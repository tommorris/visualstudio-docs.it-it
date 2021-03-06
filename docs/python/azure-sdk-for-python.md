---
title: Azure SDK per Python
description: Azure SDK per Python semplifica l'utilizzo dei servizi di Microsoft Azure dalle applicazioni Python eseguite su qualsiasi piattaforma.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 6c7f38dbe58c5172c8480c88ae84c6e28f5d512b
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545554"
---
# <a name="azure-sdk-for-python"></a>Azure SDK per Python

Azure SDK per Python semplifica l'uso e la gestione dei servizi di Microsoft Azure dalle applicazioni eseguite in Windows, Mac, OSX e Linux.

## <a name="installation"></a>Installazione

Azure SDK può essere installato da [Python Package Index](https://pypi.python.org/pypi/azure) (Indice dei pacchetti Python).

Installare la **versione stabile più recente** che supporta Python 2.7 e 3.x, come indicato di seguito:

```command
pip install azure
```

È anche possibile seguire le indicazioni in [Installazione di Python e dell'SDK](https://docs.microsoft.com/azure/python-how-to-install/) nella documentazione di Azure.

## <a name="documentation"></a>Documentazione

La documentazione è disponibile in [azure-sdk-for-python.readthedocs.org](https://docs.microsoft.com/en-us/python/azure/?view=azure-python).

Anche nella sezione [Azure SDK per Python del Centro per sviluppatori Python](https://azure.microsoft.com/develop/python/) sono disponibili numerose risorse utili, incluse alcune esercitazioni:

- Creazione di app Web con [Django](/azure/app-service-web/web-sites-python-create-deploy-django-app), [Flask](/azure/app-service-web/web-sites-python-create-deploy-flask-app) e [Bottle](/azure/app-service-web/web-sites-python-create-deploy-bottle-app).
- [Archiviazione - BLOB](/azure/storage/storage-python-how-to-use-blob-storage)
- [Archiviazione - Tabelle](/azure/storage/storage-python-how-to-use-table-storage)
- [Archiviazione - Code](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [Code del bus di servizio](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [Argomenti e sottoscrizioni del bus di servizio con Python](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [Gestione dei servizi](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

Per le API pubbliche senza documentazione, gli unit test nel [repository GitHub dell'SDK](https://github.com/Azure/azure-sdk-for-python) sono una buona fonte di informazioni:

- [Unit test per l'archiviazione](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Unit test per il bus di servizio](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [Unit test per la gestione dei servizi](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>Supporto

Il repository Git per l'SDK si trova in [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python).

Per qualsiasi problema o domanda relativi all'uso dell'SDK, [registrare i problemi nel repository](https://github.com/Azure/azure-sdk-for-python/issues).
