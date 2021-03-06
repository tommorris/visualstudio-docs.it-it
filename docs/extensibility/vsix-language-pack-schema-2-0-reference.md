---
title: Riferimenti su VSIX Language Pack Schema 2.0 | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: dagriffe
author: dgriffen
manager: douge
ms.workload:
- dagriffe
ms.openlocfilehash: e4a8bc0f4b276ed649cdff986bdfc56cf8c77e06
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586222"
---
# <a name="vsix-language-pack-schema-20-reference"></a>Riferimenti su VSIX language pack schema 2.0

Lo schema del Language Pack VSIX fornisce informazioni sull'installazione localizzati di pacchetti VSIX. La versione 2.0 di questo schema supporta gli elementi di localizzazione aggiuntive.

## <a name="language-pack-schema"></a>Schema del language pack

L'elemento radice del file language pack è `<PackageLanguagePackManifest>`, con un attributo `Version`, ovvero la versione del formato language pack. Questo articolo descrive la versione 2.0 del formato language pack, che viene specificato nel manifesto impostando il `Version` sul valore dell'attributo `Version="2.0.0"`. L'elemento radice contiene esattamente un elemento figlio `<Metadata>` elemento.

### <a name="packagelangaugepackmanifest-element"></a>Elemento PackageLangaugePackManifest

All'interno di `<PackageLanguagePackManifest>` elemento deve essere presente l'elemento seguente:
|Titolo|Descrizione|
|-----------|-----------------|
|`<Metadata>`| L'elemento contenitore per tutti i metadati di pacchetti localizzati

### <a name="metadata-element"></a>Elemento dei metadati

All'interno di `<Metadata>` elemento si possono presentare gli elementi seguenti:
|Titolo|Descrizione|
|-----------|-----------------|
|`<DisplayName>`|Il nome localizzato dell'estensione da installare|
|`<Description>`|La descrizione localizzata dell'estensione da installare|
|`<License>`| Un percorso a una versione localizzata di licenza dell'estensione|
|`<MoreInfo>`| Un collegamento a informazioni localizzate sull'estensione|
|`<ReleaseNotes>`| Un percorso o un collegamento a una versione localizzata delle note sulla versione|
|`<Icon>`| Un percorso a una versione localizzata dell'icona delle estensioni|

### <a name="sample-manifest"></a>Manifesto di esempio

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</LocalizedName>
    <Description> Esta extensión pone control personalizado en la caja de herramientas por manejar información de familia.</Description>
    <MoreInfo> http://www.contoso.com/products/es/ArbolDeFamilia.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
</PackageLanguagePackManifest>
```

## <a name="see-also"></a>Vedere anche

|Titolo|Descrizione|
|-----------|-----------------|
|[Localizzazione di pacchetti VSIX](../extensibility/localizing-vsix-packages.md)|Viene illustrato come fornire supporto di installazione localizzata per un pacchetto VSIX.|
|[Riferimenti su VSIX extension schema 2.0](../extensibility/vsix-extension-schema-2-0-reference.md)|Un manifesto VSIX descrive il contenuto di un *VSIX* file di distribuzione. Il file di distribuzione consente di installare un'estensione di Visual Studio usando il **estensioni e aggiornamenti** nella finestra di dialogo.|
|[Individuare e usare le estensioni di Visual Studio](../ide/finding-and-using-visual-studio-extensions.md)|Viene illustrato come utilizzare il **estensioni e aggiornamenti** finestra di dialogo per installare, rimuovere, attivare e disattivare le estensioni.|