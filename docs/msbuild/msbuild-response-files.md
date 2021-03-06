---
title: File di risposta MSBuild | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83f8e5ad4522a47eaea978b14678fe134b4faa8e
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081592"
---
# <a name="msbuild-response-files"></a>File di risposta MSBuild
I file di risposta (con estensione *rsp*) sono file di testo che contengono opzioni della riga di comando di *MSBuild.exe*. Ogni opzione può essere su una riga separata oppure tutte le opzioni possono essere sulla stessa riga. Le righe di commento sono precedute da un simbolo **#**. L'opzione **@** viene usata per passare un altro file di risposta a *MSBuild.exe*.  
  
## <a name="msbuildrsp"></a>MSBuild.rsp
Il file di risposta automatica è un file speciale con *estensione rsp* che *MSBuild.exe* usa automaticamente quando si compila un progetto. Il file *MSBuild.rsp* si deve trovare nella stessa directory di *MSBuild.exe*, in caso contrario non sarà rilevato. È possibile modificare questo file per specificare opzioni predefinite della riga di comando per *MSBuild.exe*. Ad esempio, se si usa lo stesso logger ogni volta che si compila un progetto, è possibile aggiungere l'opzione **/logger** a *MSBuild.rsp* e *MSBuild.exe* userà il logger ogni volta che viene compilato un progetto.  

## <a name="directorybuildrsp"></a>Directory.Build.rsp
Nella versione 15.6 e successive MSBuild cercherà un file denominato *Directory.Build.rsp*. nelle directory padre del progetto.  Questo file può risultare utile in un repository di codice sorgente per la visualizzazione degli argomenti predefiniti durante le compilazioni da riga di comando.  Può anche essere usato per specificare gli argomenti della riga di comando delle build ospitate.

## <a name="see-also"></a>Vedere anche  
 [Riferimenti a MSBuild](../msbuild/msbuild-reference.md)   
 [Riferimenti alla riga di comando](../msbuild/msbuild-command-line-reference.md)