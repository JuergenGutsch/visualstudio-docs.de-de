---
title: Architektur von VSTO-Add-ins | Microsoft Docs
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VSTOLoader.dll
- architecture [Office development in Visual Studio], application-level add-ins
- vstoee.dll
- application-level add-ins [Office development in Visual Studio], architecture
- add-ins [Office development in Visual Studio], architecture
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a8abb77978731a9fa5cd43acdcb4928944c605b1
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="architecture-of-vsto-add-ins"></a>Architektur von VSTO-Add-Ins
  VSTO-Add-Ins, die mit den Office Developer Tools in Visual Studio erstellt werden, verfügen über Architekturfunktionen, mit denen die Stabilität und Sicherheit gestärkt werden und die enge Zusammenarbeit mit Microsoft Office ermöglicht wird. In diesem Thema werden die folgenden Aspekte von VSTO-Add-Ins beschrieben:  
  
-   [Grundlegendes zu VSTO-Add-Ins](#UnderstandingAddIns)  
  
-   [Komponenten von VSTO-Add-Ins](#AddinComponents)  
  
-   [Verwenden von VSTO-Add-Ins mit Microsoft Office-Anwendungen](#HowAddinsWork)  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Allgemeine Informationen zum Erstellen von VSTO-Add-ins finden Sie unter [Übersicht über die Entwicklung von Office-Lösungen &#40; VSTO- &#41; ](../vsto/office-solutions-development-overview-vsto.md) und [Einstieg Programmieren von VSTO-Add-ins](../vsto/getting-started-programming-vsto-add-ins.md).  
  
##  <a name="UnderstandingAddIns"></a> Grundlegendes zu VSTO-Add-Ins  
 Wenn Sie die Office Developer Tools in Visual Studio verwenden, um ein VSTO-Add-In zu erstellen, erstellen Sie eine verwaltete Codeassembly, die von einer Microsoft Office-Anwendung geladen wird. Nach dem Laden der Assembly kann das VSTO-Add-In auf Ereignisse reagieren, die in der Anwendung ausgelöst werden (z. B. wenn ein Benutzer auf ein Menüelement klickt). Außerdem kann das VSTO-Add-In einen Aufruf an das Objektmodell ausführen, um die Anwendung zu automatisieren und zu erweitern, und der Code kann alle Klassen in [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)]verwenden.  
  
 Die Assembly verwendet die primäre Interopassembly der Anwendung, um mit den COM-Komponenten der Anwendung zu kommunizieren. Weitere Informationen finden Sie unter [Office Primary Interopassemblys](../vsto/office-primary-interop-assemblies.md) und [Übersicht über die Entwicklung von Office-Lösungen &#40; VSTO- &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 Wenn für eine Anwendung mehrere VSTO-Add-Ins installiert werden, wird jedes VSTO-Add-In in einer anderen Anwendungsdomäne geladen. So kann ein VSTO-Add-In, das sich falsch verhält, nicht bewirken, dass für andere VSTO-Add-Ins Fehler auftreten. Es wird auch sichergestellt, dass beim Schließen der Anwendung alle VSTO-Add-In-Assemblys aus dem Speicher entladen werden. Weitere Informationen zu Anwendungsdomänen finden Sie unter [Anwendungsdomänen](/dotnet/framework/app-domains/application-domains).  
  
> [!NOTE]  
>  VSTO-Add-Ins, die mit den Office Developer Tools in Visual Studio erstellt werden, sollen nur dann verwendet werden, wenn die Microsoft Office-Hostanwendung von einem Endbenutzer gestartet wird. Wird die Anwendung programmgesteuert gestartet (beispielsweise per Automatisierung), verhält sich das VSTO-Add-In unter Umständen nicht wie erwartet.  
  
##  <a name="AddinComponents"></a> Komponenten von VSTO-Add-Ins  
 Die VSTO-Add-In-Assembly ist zwar die Hauptkomponente, aber es gibt noch mehrere andere Komponenten, die eine wichtige Rolle dabei spielen, wie Microsoft Office-Anwendungen VSTO-Add-Ins ermitteln und laden.  
  
### <a name="registry-entries"></a>Registrierungseinträge  
 Microsoft Office-Anwendungen ermitteln VSTO-Add-Ins, indem sie nach einem Satz von Registrierungseinträgen suchen. Eine vollständige Liste der von VSTO-Add-ins verwendeten Registrierungseinträge, finden Sie unter [Registrierungseinträge für VSTO-Add-ins](../vsto/registry-entries-for-vsto-add-ins.md).  
  
 Wenn Sie die Projektmappe erstellen, erstellt Visual Studio alle erforderlichen Registrierungseinträge auf dem Entwicklungscomputer, damit Sie Ihr VSTO-Add-In debuggen und ausführen können. Weitere Informationen finden Sie unter [Erstellen von Office-Projektmappen](../vsto/building-office-solutions.md).  
  
 Wenn Sie ClickOnce zum Bereitstellen Ihrer Lösung verwenden, erstellt das Setupprogramm, das während des Veröffentlichungsprozesses generiert wurde, auf dem Endbenutzercomputer automatisch die Registrierungsschlüssel. Weitere Informationen finden Sie unter [Bereitstellen einer Office-Lösung mithilfe von ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
### <a name="deployment-manifest-and-application-manifest"></a>Bereitstellungsmanifest und Anwendungsmanifest  
 VSTO-Add-Ins verwenden Bereitstellungs- und Anwendungsmanifeste, um die aktuelle Version der VSTO-Add-In-Assembly zu identifizieren und zu laden. Das Bereitstellungsmanifest verweist auf das aktuelle Anwendungsmanifest. Das Anwendungsmanifest verweist auf die VSTO-Add-In-Assembly und gibt die Einstiegspunktklasse an, die in der Assembly ausgeführt wird. Weitere Informationen finden Sie unter [Application and Deployment Manifests in Office Solutions](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
### <a name="visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office Runtime  
 Zum Ausführen von mit den Office Developer Tools in Visual Studio erstellten VSTO-Add-Ins muss auf den Endbenutzercomputern [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] installiert sein. Die Laufzeit enthält nicht verwaltete Komponenten und einen Satz verwalteter Assemblys. Die nicht verwalteten Komponenten laden die VSTO-Add-In-Assembly. Die verwalteten Assemblys enthalten das Objektmodell, das Ihr VSTO-Add-In-Code verwendet, um die Hostanwendung zu automatisieren und zu erweitern.  
  
 Weitere Informationen finden Sie unter [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
##  <a name="HowAddinsWork"></a> How VSTO Add-ins Work with Microsoft Office Applications  
 Wenn ein Benutzer eine Microsoft Office-Anwendung startet, verwendet die Anwendung das Bereitstellungsmanifest und das Anwendungsmanifest, um die aktuelle Version der VSTO-Add-In-Assembly zu suchen und zu laden. Die folgende Abbildung zeigt die grundlegende Architektur dieser VSTO-Add-Ins.  
  
 ![2007 Office-add-in-Architektur](../vsto/media/office07addin.png "2007 Office-add-in-Architektur")  
  
> [!NOTE]  
>  In Office-Projektmappen, die auf [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] oder [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]abzielen, rufen Projektmappen das Objektmodell der Hostanwendung mithilfe von in die Projektmappenassembly eingebetteten PIA-Typinformationen auf, statt die PIA direkt aufzurufen. Weitere Informationen finden Sie unter [Designing and Creating Office Solutions](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="loading-process"></a>Ladevorgang  
 Die folgenden Schritte werden ausgeführt, wenn ein Benutzer eine Anwendung startet:  
  
1.  Die Anwendung überprüft die Registrierung auf Einträge, mit denen VSTO-Add-Ins identifiziert werden, die mit den Office Developer Tools in Visual Studio erstellt wurden.  
  
2.  Wenn die Anwendung diese Registrierungseinträge findet, lädt die Anwendung die Datei „VSTOEE.dll“, mit der wiederum die Datei „VSTOLoader.dll“ geladen wird. Hierbei handelt es sich um nicht verwaltete DLLs, die die Ladeprogrammkomponenten für Visual Studio 2010-Tools für Office-Laufzeit sind. Weitere Informationen finden Sie unter [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
3.  VSTOLoader.dll lädt [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] und startet den verwalteten Teil von [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
4.  Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] führt eine Prüfung auf Manifestaktualisierungen durch und lädt die aktuellen Anwendungs- und Bereitstellungsmanifeste herunter.  
  
5.  Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] führt eine Reihe von Sicherheitsüberprüfungen durch. Weitere Informationen finden Sie unter [Securing Office Solutions](../vsto/securing-office-solutions.md).  
  
6.  Wenn das VSTO-Add-In vertrauenswürdig ist und ausgeführt werden darf, verwendet [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] das Bereitstellungsmanifest und das Anwendungsmanifest, um nach Assemblyaktualisierungen zu suchen. Wenn eine neue Version der Assembly verfügbar ist, lädt die Laufzeit die neue Version der Assembly in den [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] -Cache auf dem Clientcomputer. Weitere Informationen finden Sie unter [Bereitstellen einer Office-Lösung](../vsto/deploying-an-office-solution.md).  
  
7.  Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] erstellt eine neue Anwendungsdomäne, in die die VSTO-Add-In-Assembly geladen wird.  
  
8.  Die VSTO-Add-In-Assembly wird von der [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] in die Anwendungsdomäne geladen.  
  
9. Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ruft die <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> -Methode in Ihrem VSTO-Add-In auf, wenn Sie sie außer Kraft gesetzt haben.  
  
     Sie können diese Methode optional außer Kraft setzen, um in Ihrem VSTO-Add-In ein Objekt für andere Microsoft Office-Projektmappen verfügbar zu machen. Weitere Informationen finden Sie unter [Calling Code in VSTO Add-ins from Other Office Solutions](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
10. Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ruft die <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> -Methode in Ihrem VSTO-Add-In auf, wenn Sie sie außer Kraft gesetzt haben.  
  
     Sie können diese Methode optional außer Kraft setzen, um eine Microsoft Office-Funktion zu erweitern, indem Sie ein Objekt zurückgeben, mit dem eine Erweiterbarkeitsschnittstelle implementiert wird. Weitere Informationen finden Sie unter [Customizing UI Features By Using Extensibility Interfaces](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md).  
  
    > [!NOTE]  
    >  Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] führt separate Aufrufe der <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> -Methode für die einzelnen Erweiterbarkeitsschnittstellen durch, die von der Hostanwendung unterstützt werden. Obwohl der erste Aufruf der <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> -Methode normalerweise vor dem Aufruf der `ThisAddIn_Startup` -Methode erfolgt, sollten in Ihrem VSTO-Add-In keine Annahmen dazu getroffen werden, wann oder wie oft die <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> -Methode aufgerufen wird.  
  
11. Die [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ruft die `ThisAddIn_Startup` -Methode in Ihrem VSTO-Add-In auf. Diese Methode ist der Standardereignishandler für das <xref:Microsoft.Office.Tools.AddInBase.Startup> -Ereignis. Weitere Informationen finden Sie unter [Events in Office Projects](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von Office-Projektmappen in Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektur von Anpassungen auf Dokumentebene](../vsto/architecture-of-document-level-customizations.md)   
 [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Entwickeln von Office-Projektmappen](../vsto/developing-office-solutions.md)   
 [Sichern von Office-Projektmappen](../vsto/securing-office-solutions.md)   
 [Bereitstellen einer Office-Projektmappe](../vsto/deploying-an-office-solution.md)  
  
  