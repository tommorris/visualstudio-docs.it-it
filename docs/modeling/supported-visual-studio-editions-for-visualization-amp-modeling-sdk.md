---
title: Edizioni di Visual Studio per la visualizzazione &amp; SDK di modellazione
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language Tools, supported Visual Studio editions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 004a6b75bb66ebf3c1797abac9c1cc6f7faa6eb9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948194"
---
# <a name="supported-visual-studio-editions-for-visualization-amp-modeling-sdk"></a>Edizioni di Visual Studio per la visualizzazione &amp; SDK di modellazione
Di seguito sono riportati gli elenchi delle versioni di Visual Studio che sono supportati con [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] negli ambienti di creazione e la distribuzione. Per ulteriori informazioni su queste edizioni, vedere Microsoft [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] [Developer Center](http://go.microsoft.com/fwlink/?LinkId=75628).

## <a name="authoring-edition"></a>Edizione per lo sviluppo
 Per definire un linguaggio specifico di dominio (Domain-Specific Language, DSL) devono essere installati i componenti seguenti:

|||
|-|-|
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|Visual Studio SDK|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|SDK di visualizzazione e modellazione di Visual Studio|[http://go.microsoft.com/fwlink/?LinkID=186128](http://go.microsoft.com/fwlink/?LinkID=186128)|

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="deployment-editions"></a>Edizioni per la distribuzione
 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] supporta le configurazioni seguenti per la distribuzione dei linguaggi specifici di dominio compilati:

-   Visual Studio Enterprise

-   Visual Studio Professional

-   Pacchetto ridistribuibile pacchetto ridistribuibile di Visual Studio Shell (modalità integrata)

-   Pacchetto ridistribuibile Visual Studio Shell (modalità isolata)

> [!NOTE]
>  Per un linguaggio DSL in grado di eseguire su un prodotto di Shell, è necessario impostare il **edizione supportata di Visual Studio** campo nel manifesto dell'estensione. Per ulteriori informazioni, vedere [soluzioni per la distribuzione di un linguaggio specifico di dominio](../modeling/deploying-domain-specific-language-solutions.md).

## <a name="see-also"></a>Vedere anche

- [Glossario di strumenti di linguaggio specifico di dominio](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
