---
title: GetFrameworkSdkPath-Aufgabe | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8a24d7e459e0320cd33ad5fe1b3c2fe60f6e0d91
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath-Aufgabe
Ruft den Pfad zu [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)] ab  
  
## <a name="task-parameters"></a>Aufgabenparameter  
 In der folgenden Tabelle werden die Parameter der `GetFrameworkSdkPath`-Aufgabe beschrieben.  
  
|Parameter|description|  
|---------------|-----------------|  
|`FrameworkSdkVersion20Path`|Optionaler schreibgeschützter `String`-Parameter<br /><br /> Gibt den Pfad zum .NET SDK-Version 2.0 zurück, falls vorhanden Andernfalls wird `String.Empty` zurückgegeben.|  
|`FrameworkSdkVersion35Path`|Optionaler schreibgeschützter `String`-Parameter<br /><br /> Gibt den Pfad zum .NET SDK-Version 3.5 zurück, falls vorhanden Andernfalls wird `String.Empty` zurückgegeben.|  
|`FrameworkSdkVersion40Path`|Optionaler schreibgeschützter `String`-Parameter<br /><br /> Gibt den Pfad zum .NET SDK-Version 4.0 zurück, falls vorhanden Andernfalls wird `String.Empty` zurückgegeben.|  
|`Path`|Optionaler `String`-Ausgabeparameter.<br /><br /> Enthält den Pfad zum neuesten .NET SDK, wenn eine Version vorhanden ist. Andernfalls wird `String.Empty` zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Zusätzlich zu den oben aufgeführten Parametern erbt diese Aufgabe Parameter von der <xref:Microsoft.Build.Tasks.TaskExtension>-Klasse, die selbst von der <xref:Microsoft.Build.Utilities.Task>-Klasse erbt. Eine Liste mit diesen zusätzlichen Parametern und ihren Beschreibungen finden Sie unter [TaskExtension Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird mit der Aufgabe `GetFrameworkSdkPath` der Pfad zu [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] in der `SdkPath`-Eigenschaft gespeichert.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="GetPath">  
        <GetFrameworkSdkPath>  
            <Output  
                TaskParameter="Path"  
                PropertyName="SdkPath" />  
        </GetFrameworkSdkPath>  
        <Message Text="$(SdkPath)"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Tasks (Aufgaben)](../msbuild/msbuild-tasks.md)   
 [Aufgabenreferenz](../msbuild/msbuild-task-reference.md)