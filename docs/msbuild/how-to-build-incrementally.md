---
title: 'Vorgehensweise: Inkrementelles Erstellen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, incremental builds
- incremental builds
- MSBuild, building incrementally
ms.assetid: 8d82d7d8-a2f1-4df6-9d2f-80b9e0cb3ac3
caps.latest.revision: "21"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 73931a8be39933c727225d582bc4e4e35b805d7d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-incrementally"></a>Gewusst wie: Inkrementelles Erstellen
Wenn Sie ein großes Projekt erstellen, dann ist es sehr wichtig, dass zuvor erstellte Komponenten, die noch immer auf dem neuesten Stand sind, nicht neu erstellt werden. Wenn alle Ziele jedes mal neu erstellt werden, braucht jeder Build sehr lange, bis er abgeschlossen wird. Um inkrementelle Builds zu aktivieren (es werden nur Builds mit den Zielen neu erstellt, die zuvor noch nicht erstellt wurden oder mit Zielen, die nicht mehr aktuell sind) kann [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]) die Zeitstempel der Eingabedateien mit jenen der Ausgabedateien vergleichen und bestimmen, ob ein Ziel übersprungen, erstellt oder teilweise neu erstellt wird. Es muss jedoch eine 1:1-Zuordnung zwischen Eingaben und Ausgaben bestehen. Sie können Transformationen verwenden, damit Ziele diese direkte Zuordnung identifizieren können. Weitere Informationen zu Transformationen finden Sie unter [MSBuild Transforms (Transformationen)](../msbuild/msbuild-transforms.md).  
  
## <a name="specifying-inputs-and-outputs"></a>Angeben von Eingaben und Ausgaben  
 Ein Ziel kann inkrementell erstellt werden, wenn die Eingaben und Ausgaben in der Projektdatei angegeben werden.  
  
#### <a name="to-specify-inputs-and-outputs-for-a-target"></a>So geben Sie Eingaben und Ausgaben für ein Ziel an  
  
-   Verwenden Sie die `Inputs`- und `Outputs`-Attribute des `Target`-Elements an. Zum Beispiel:  
  
    ```xml  
    <Target Name="Build"  
        Inputs="@(CSFile)"  
        Outputs="hello.exe">  
    ```  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] kann die Zeitstempel der Eingabedatei mit den Zeitstempeln der Ausgabedateien bestimmen und festlegen, ob ein Ziel übersprungen, erstellt oder teilweise neu erstellt wird. Wenn im folgenden Beispiel eine Datei in der `@(CSFile)`-Elementauflistung neuer als die „hello.exe“-Datei ist, führt [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] das Ziel aus; andernfalls wird es übersprungen.  
  
```xml  
<Target Name="Build"   
    Inputs="@(CSFile)"   
    Outputs="hello.exe">  
  
    <Csc  
        Sources="@(CSFile)"   
        OutputAssembly="hello.exe"/>  
</Target>  
```  
  
 Wenn Eingaben und Ausgaben in einem Ziel angegeben sind, kann entweder jede Ausgabe nur einer Eingabe zugeordnet werden, oder es entsteht keine Zuordnung zwischen Aus- und Eingaben. In der vorherigen [Csc-Aufgabe](../msbuild/csc-task.md) kann z.B. die Ausgabedatei „hello.exe“ keiner einzelnen Eingabe zugeordnet werden – sie hängt von allen Eingaben ab.  
  
> [!NOTE]
>  Ein Ziel, in dem keine direkte Zuordnung zwischen den Ein- und Ausgaben besteht, führt immer öfter eine Erstellung durch, als ein Ziel, in dem jede Ausgabe nur einer Eingabe zugeordnet werden kann, da [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nicht bestimmen kann, welche Ausgaben neu erstellt werden müssen, wenn sich einige der Eingaben verändert haben.  
  
 Aufgaben, in denen Sie eine direkte Zuordnung zwischen den Aus- und Eingaben erkennen können, z.B. die [LC-Aufgabe](../msbuild/lc-task.md), sind am besten für inkrementelle Builds geeignet, im Gegensatz zu Aufgaben wie `Csc` und [Vbc](../msbuild/vbc-task.md), die nur eine Ausgabeassembly aus einer Reihe von Eingaben erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet ein Projekt, das Hilfedateien für ein hypothetisches Hilfesystem erstellt. Das Projekt arbeitet, indem TXT-Quelldateien in CONTENT-Zwischendateien konvertiert werden, die dann mit XML-Metadatendateien kombiniert werden, um die finale Hilfedatei zu erstellen, die vom Hilfesystem verwendet wird. Das Projekt verwendet die folgenden hypothetischen Aufgaben:  
  
-   `GenerateContentFiles`: Konvertiert TXT-Dateien in CONTENT-Dateien.  
  
-   `BuildHelp`: Kombiniert CONTENT-Dateien und XML-Metadatendateien, um die finale Hilfedatei zu erstellen.  
  
 Das Projekt verwendet Transformationen, um eine 1:1-Zuordnung zwischen Eingaben und Ausgaben in der `GenerateContentFiles`-Ausgabe zu erstellen. Weitere Informationen finden Sie unter [Transformationen](../msbuild/msbuild-transforms.md). Es wird ebenso festgelegt, dass das `Output`-Element automatisch die Ausgaben der `GenerateContentFiles`-Aufgabe als Eingaben für die `BuildHelp`-Aufgabe verwendet.  
  
 Diese Projektdatei enthält jeweils die Ziele `Convert` und `Build`. Die `GenerateContentFiles`- und `BuildHelp`-Aufgaben sind jeweils in den Zielen `Convert` und `Build` platziert, sodass jedes Ziel inkrementell erstellt werden kann. Indem das `Output`-Element verwendet wird, werden die Ausgaben der `GenerateContentFiles`-Aufgabe in der `ContentFile`-Elementauflistung platziert, wo sie als Eingaben für die `BuildHelp`-Aufgabe verwendet werden können. Wenn Sie das `Output`-Element so nutzen, werden automatisch die Ausgaben aus einer Aufgabe als Eingaben für eine andere Aufgabe verwendet, sodass Sie nicht die einzelnen Elemente oder Elementauflistungen manuell in jeder Aufgabe eingeben müssen.  
  
> [!NOTE]
>  Obwohl das `GenerateContentFiles`-Ziel eine inkrementelle Erstellung vornehmen kann, werden alle Ausgaben aus diesem Ziel immer als Eingaben für das `BuildHelp`-Ziel benötigt. [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] stellt automatisch alle Ausgaben von einem Ziel als Eingaben für ein anderes Ziel bereit, wenn Sie das `Output`-Element verwenden.  
  
```xml  
<Project DefaultTargets="Build"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <TXTFile Include="*.txt"/>  
        <XMLFile Include="\metadata\*.xml"/>  
    </ItemGroup>  
  
    <Target Name = "Convert"  
        Inputs="@(TXTFile)"  
        Outputs="@(TXTFile->'%(Filename).content')">  
  
        <GenerateContentFiles  
            Sources = "@(TXTFile)">  
            <Output TaskParameter = "OutputContentFiles"  
                ItemName = "ContentFiles"/>  
        </GenerateContentFiles>  
    </Target>  
  
    <Target Name = "Build" DependsOnTargets = "Convert"  
        Inputs="@(ContentFiles);@(XMLFiles)"  
        Outputs="$(MSBuildProjectName).help">  
  
        <BuildHelp  
            ContentFiles = "@(ContentFiles)"  
            MetadataFiles = "@(XMLFile)"  
            OutputFileName = "$(MSBuildProjectName).help"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../msbuild/msbuild-targets.md)   
 [Target-Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [Transformationen](../msbuild/msbuild-transforms.md)   
 [Csc-Aufgabe](../msbuild/csc-task.md)   
 [Vbc-Aufgabe](../msbuild/vbc-task.md)