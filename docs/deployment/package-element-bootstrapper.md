---
title: '&lt;Pacchetto&gt; elemento (programma di avvio automatico) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <package> element [bootstrapper]
ms.assetid: ecd06658-ad02-4440-bccd-88437b7fb816
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0c1ab7a2e304fcaede2a51a1047691343f34783
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080786"
---
# <a name="ltpackagegt-element-bootstrapper"></a>&lt;Pacchetto&gt; elemento (programma di avvio automatico)
Il `Package` elemento è l'elemento XML di primo livello all'interno di un file del pacchetto.  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<Package  
    Culture  
    Name  
    LicenseAgreement  
>  
    <InstallChecks>  
        <AssemblyCheck   
            Property  
            Name  
            PublicKeyToken  
            Version  
            Language  
            ProcessorArchitecture  
        />  
        <RegistryCheck  
            Property  
            Key  
            Value  
        />  
        <ExternalCheck   
            PackageFile  
            Property  
            Arguments  
            Log  
        />  
        <FileCheck   
            Property  
            FileName  
            SearchPath  
            SpecialFolder  
            SearchDepth  
        />  
        <MsiProductCheck   
            Property  
            Product  
            Feature  
        />  
        <RegistryFileCheck   
            Property  
            Key  
            Value  
            File  
            SearchDepth  
        />  
    </InstallChecks>  
  
    <Commands  
        Reboot  
    >  
        <Command  
            PackageFile  
            Arguments  
            EstimatedInstallSeconds  
            EstimatedDiskBytes  
            EstimatedTempBytes  
            Log  
        >  
            <InstallConditions>  
                <BypassIf   
                    Property  
                    Compare  
                    Value  
                    Schedule  
                />  
                <FailIf   
                    Property  
                    Compare  
                    Value  
                    String  
                    Schedule  
                />  
            </InstallConditions>  
            <ExitCodes>  
                <ExitCode   
                    Value  
                    Result  
                    String  
                />  
            </ExitCodes>  
        </Command>  
    </Commands>  
  
    <PackageFiles  
        CopyAllComponents  
    >  
        <PackageFile   
            Name  
            Path  
            HomeSite  
            PublicKey  
        />  
    </PackageFiles>  
  
    <Strings>  
        <String  
            Name  
        >  
        </String>  
    </Strings>  
  
    <Schedules>  
        <Schedule  
            Name  
        >  
           <BuildList />  
           <BeforePackage />  
           <AfterPackage />  
        </Schedule>  
    </Schedules>  
</Package>  
```  
  
## <a name="elements-and-attributes"></a>Gli elementi e attributi  
 Il `Package` elemento è obbligatorio. Include gli attributi seguenti.  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`Culture`|Obbligatorio. Definisce le impostazioni cultura per questo pacchetto, che determina la lingua da utilizzare. Questo attributo è una chiave nel `Strings` elemento, che elenca le stringhe specifiche delle impostazioni cultura per i nomi dei prodotti e i messaggi di errore durante l'installazione.|  
|`Name`|Obbligatorio. Il nome del pacchetto visualizzato per lo sviluppatore all'interno di uno strumento, ad esempio [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Questo attributo è una chiave nel `Strings` elemento che deve contenere un `String` elemento con la `Name` e `Culture` proprietà impostate in modo che corrisponda il `Name` e `Culture` le proprietà di `Package`.|  
|`LicenseAgreement`|Facoltativo. Specifica il nome del file del pacchetto di distribuzione che contiene il contratto di licenza dell'utente finale (EULA).  Questo file può essere una stringa di testo normale (*txt*) in formato testo. (*RTF*)|  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato un file del pacchetto completo per la ridistribuzione di [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)].  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
  
<Package  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  Name="DisplayName"  
  Culture="Culture"  
  LicenseAgreement="eula.rtf"  
>  
  
    <PackageFiles>  
        <PackageFile Name="eula.rtf"/>  
    </PackageFiles>  
  
    <!-- Defines a localizable string table for error messages-->  
    <Strings>  
        <String Name="DisplayName">.NET Framework 2.0</String>  
        <String Name="Culture">en</String>  
        <String Name="AdminRequired">Administrator permissions are required to install the .NET Framework 2.0. Contact your administrator.</String>  
        <String Name="InvalidPlatformWin9x">Installation of the .NET Framework 2.0 is not supported on Windows 95. Contact your application vendor.</String>  
        <String Name="InvalidPlatformWinNT">Installation of the .NET Framework 2.0 is not supported on Windows NT 4.0. Contact your application vendor.</String>  
        <String Name="InvalidPlatformIE">Installation of the .NET Framework 2.0 requires Internet Explorer 5.01 or greater. Contact your application vendor.</String>  
        <String Name="InvalidPlatformArchitecture">This version of the .NET Framework 2.0 is not supported on a 64-bit operating system. Contact your application vendor.</String>  
        <String Name="WindowsInstallerImproperInstall">Due to an error with Windows Installer, the installation of the .NET Framework 2.0 cannot proceed.</String>  
        <String Name="AnotherInstanceRunning">Another instance of setup is already running. The running instance must complete before this setup can proceed.</String>  
        <String Name="BetaNDPFailure">A beta version of the .NET Framework was detected on the computer. Uninstall any previous beta versions of .NET Framework before continuing.</String>  
        <String Name="GeneralFailure">A failure occurred attempting to install the .NET Framework 2.0.</String>  
        <String Name="DotNetFXExe">http://go.microsoft.com/fwlink/?LinkId=37283</String>  
        <String Name="InstMsiAExe">http://go.microsoft.com/fwlink/?LinkId=37285</String>  
        <String Name="Msi30Exe">http://go.microsoft.com/fwlink/?LinkId=37287</String>  
    </Strings>  
  
</Package>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento allo schema di Product e package](../deployment/product-and-package-schema-reference.md)