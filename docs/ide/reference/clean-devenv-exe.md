---
title: "/Clean („devenv.exe“) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- builds [Team System], cleaning files
- clean Devenv switch
- /clean Devenv switch
- Devenv, /clean switch
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5982cfd7b9201008f4ecc5930041200fd4980dca
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clean-devenvexe"></a>/Clean (devenv.exe)
Bereinigt alle Zwischendateien und Ausgabeverzeichnisse  
  
## <a name="syntax"></a>Syntax  
  
```  
devenv FileName /Clean [ /project projectnameorfile [/projectconfig name ] ]  
```  
  
## <a name="arguments"></a>Argumente  
 `FileName`  
 Erforderlich. Der vollständige Pfad und Name der Projektmappen- oder Projektdatei.  
  
 /project `ProjName`  
 Dies ist optional. Der Pfad und der Name einer Projektdatei innerhalb der Projektmappe. Sie können einen relativen Pfad vom `SolutionName`-Ordner zur Projektdatei, dem Anzeigenamen des Projekts oder dem vollständigen Pfad und Namen der Projektdatei eingeben.  
  
 /projectconfig `ProjConfigName`  
 Dies ist optional. Der Name der Projektbuildkonfiguration für die Bereinigung des benannten `/project`.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Schalter führt dieselbe Funktion aus wie der Menübefehl **Projektmappe bereinigen** in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE).  
  
 Schließen Sie Zeichenfolgen, die Leerzeichen enthalten, in doppelten Anführungszeichen ein.  
  
 Zusammenfassende Informationen für Bereinigungen und Builds, inklusive Fehlermeldungen, können im **Befehlsfenster** oder durch den `/out`-Schalter in einer Protokolldatei angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Im ersten Beispiel wird die `MySolution`-Projektmappe mithilfe der in der Projektmappendatei angegebenen Standardkonfiguration bereinigt.  
  
 In diesem Beispiel wird das Projekt `CSharpConsoleApp` mithilfe der Projektbuildkonfiguration `Debug` in der `Debug`-Projektmappenkonfiguration von `MySolution` bereinigt.  
  
```  
Devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean  
  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Devenv-Befehlszeilenschalter](../../ide/reference/devenv-command-line-switches.md)   
 [/Build („devenv.exe“)](../../ide/reference/build-devenv-exe.md)   
 [/Rebuild („devenv.exe“)](../../ide/reference/rebuild-devenv-exe.md)   
 [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)