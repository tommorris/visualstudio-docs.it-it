---
title: Elemento KeyBinding | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: eb8e0dca8293d5d5e853dde19e0c411cfd3e4e63
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495297"
---
# <a name="keybinding-element"></a>Elemento KeyBinding
L'elemento KeyBinding specifica tasti di scelta rapida per i comandi.  
  
 I comandi possono avere una o due tasti di scelta rapida associati. È un esempio di un unico tasto di scelta rapida **Ctrl**+**S** per i **Salva** comando. Tasti di scelta doppia richiedono due combinazioni di tasti successive per attivare un comando. È un esempio di un tasto di scelta rapida duale **Ctrl * +** K **,** Ctrl**+** K * * per impostare un segnalibro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|guid|Obbligatorio.|  
|ID|Obbligatorio.|  
|editor|Obbligatorio. Il GUID dell'editor indica il contesto di modifica per il quale sarà attiva questo tasto di scelta rapida. Il valore dell'ambito dell'associazione globale è "guidVSStd97".|  
|key1|Obbligatorio. I valori validi includono possibile digitare tutti i caratteri alfanumerici, nonché i valori esadecimali a due cifre preceduti da 0x e [VK_constants](/windows/desktop/inputdev/virtual-key-codes).|  
|MOD1|Facoltativo. Qualsiasi combinazione delle **Ctrl**, **Alt**, e **MAIUSC** separati da spazio.|  
|key2|Facoltativo. I valori validi includono possibile digitare tutti i caratteri alfanumerici, nonché i valori esadecimali a due cifre preceduti da 0x e [VK_constants](/windows/desktop/inputdev/virtual-key-codes).|  
|MOD2|Facoltativo. Qualsiasi combinazione delle **Ctrl**, **Alt**, e **MAIUSC** separati da spazio.|  
|Emulatore|Facoltativo.|  
|Condizione|Facoltativo. Visualizzare [attributi condizionali](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|Padre||  
|Annotazione||  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento KeyBindings](../extensibility/keybindings-element.md)|Raggruppa gli elementi di tasto di scelta rapida e altri raggruppamenti di tasti di scelta rapida.|  
  
## <a name="example"></a>Esempio  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Elemento KeyBindings](../extensibility/keybindings-element.md)   
 [File di Visual Studio comando table (vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
