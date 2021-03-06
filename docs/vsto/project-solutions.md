---
title: "Projekt Lösungen | Microsoft Docs"
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
- projects [Office development in Visual Studio], Project
- Office solutions [Office development in Visual Studio], Project
- Project [Office development in Visual Studio]
- templates [Office development in Visual Studio], Project
- Office projects [Office development in Visual Studio], Project
- solutions [Office development in Visual Studio], Project
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 39ee63d84ef0c7830da9c218a6e4c7b25f7bac99
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="project-solutions"></a>Projektmappen
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] stellt Projektvorlagen bereit, die Sie zum Erstellen von VSTO-Add-Ins für Microsoft Office Project verwenden können. Mit VSTO-Add-Ins können Sie Project automatisieren, Project-Features erweitern oder die Project-Benutzeroberfläche anpassen.  
  
 Weitere Informationen zu VSTO-Add-Ins finden Sie unter [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md) und [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md). Wenn Sie mit Microsoft Office-Programmierung noch nicht vertraut sind, finden Sie unter [Einstieg &#40; Office-Entwicklung in Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
> [!NOTE]  
>  Bei der Entwicklung von Lösungen, die über die Office-Erfahrungen erweitern "interested" [mehrere Plattformen](https://dev.office.com/add-in-availability)? Sehen Sie sich die neue [Office-Add-ins Modell](https://dev.office.com/docs/add-ins/overview/office-add-ins). Office-Add-ins haben einen geringen Ressourcenbedarf im Vergleich zu VSTO-add-ins und Lösungen, und Sie können sie mithilfe von fast allen Web-Technologien, wie HTML5, JavaScript, CSS3 und XML-Programmierung erstellen.  
  
## <a name="automating-project-by-using-the-project-object-model"></a>Automatisieren von Project mithilfe des Project-Objektmodells  
 Das Project-Objektmodell macht viele Typen verfügbar, die Sie zum Automatisieren von Project verwenden können. Mit diesen Typen können Sie Code zum Ausführen gebräuchlicher Aufgaben schreiben, beispielsweise für das programmgesteuerte Erstellen und Ändern von Aufgaben in einem Projekt.  
  
 Wenn Sie in einem VSTO-Add-In auf das Project-Objektmodell zugreifen möchten, verwenden Sie das `Application` -Feld der `ThisAddIn` -Klasse im Projekt. Die `Application` Feld gibt einen Microsoft.Office.Interop.MsProject.Application-Objekt, das die aktuelle Instanz von Project darstellt. Weitere Informationen finden Sie unter [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md).  
  
 Bei einem Aufruf des Project-Objektmodells verwenden Sie Typen, die in der primären Interopassembly für Project bereitgestellt werden. Die primäre Interopassembly dient als Brücke zwischen verwaltetem Code im VSTO-Add-In und dem COM-Objektmodell in Project. Alle Typen in der primären Interopassembly für Project werden im Microsoft.Office.Interop.MSProject-Namespace definiert. Weitere Informationen zu primären Interopassemblys finden Sie unter [Übersicht über die Entwicklung von Office-Lösungen &#40; VSTO- &#41; ](../vsto/office-solutions-development-overview-vsto.md) und [primären Interopassemblys für Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="using-the-project-object-model-documentation"></a>Verwenden der Dokumentation für das Project-Objektmodell  
 Ausführliche Informationen zum Project-Objektmodell finden Sie in der VBA-Objektmodellreferenz für Project. Die VBA-Objektmodellreferenz dokumentiert das Project-Objektmodell, das für VBA (Visual Basic for Applications) verfügbar gemacht wird. Weitere Informationen finden Sie in der [Project 2010-Objektmodellreferenz](http://go.microsoft.com/fwlink/?LinkId=199771).  
  
 Alle Objekte und Member in der VBA-Objektmodellreferenz entsprechen Typen und Membern in der primären Interopassembly (PIA) für Project. Das Kalender-Objekt in der VBA-Objektmodellreferenz entspricht z. B. der Microsoft.Office.Interop.MSProject.Calendar-Typ in der Project-PIA. Obwohl die VBA-Objektmodellreferenz Codebeispiele für die meisten Eigenschaften, Methoden und Ereignisse enthält, müssen Sie den VBA-Code in dieser Referenz in Visual Basic oder Visual C# übersetzen, wenn Sie ihn in einem mit Visual Studio erstellten Project-VSTO-Add-In-Projekt verwenden möchten.  
  
> [!NOTE]  
>  Derzeit ist keine Referenzdokumentation für die primäre Interopassembly für Project verfügbar.  
  
### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Infrastrukturtypen in der primären Interopassembly für Project  
 Wenn Sie Code schreiben, in dem die Project-PIA verwendet wird, werden Ihnen möglicherweise viele Typen begegnen, die nicht in der VBA-Referenz beschrieben sind. Diese zusätzlichen Typen helfen dabei, Objekte im COM-basierten Objektmodell von Project in verwalteten Code zu übersetzen. Sie sind nicht für die direkte Verwendung im Code vorgesehen.  
  
 Weitere Informationen finden Sie in der[Übersicht über Klassen und Schnittstellen in den primären Interopassemblys für Office](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
## <a name="customizing-the-user-interface-of-project"></a>Anpassen der Benutzeroberfläche von Project  
 Sie können die Benutzeroberfläche von Project folgendermaßen anpassen:  
  
|Aufgabe|Weitere Informationen|  
|----------|--------------------------|  
|Hinzufügen benutzerdefinierter Registerkarten zum Menüband in Project|[Übersicht über das Menüband](../vsto/ribbon-overview.md)|  
  
 Weitere Informationen zum Anpassen der Benutzeroberfläche von Project und anderen Microsoft Office-Anwendungen finden Sie unter [Anpassung der Office-Benutzeroberfläche](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen Ihrer ersten VSTO-Add-Ins für Project](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Übersicht über die Entwicklung von Office-Lösungen &#40; VSTO- &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [Architektur von VSTO-Add-ins](../vsto/architecture-of-vsto-add-ins.md)   
 [Vorgehensweise: Erstellen von Office-Projekten in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Schreiben von Code in Office-Projektmappen](../vsto/writing-code-in-office-solutions.md)   
 [Primäre Interopassemblys für Office](../vsto/office-primary-interop-assemblies.md)   
 [Anpassung der Office-Benutzeroberfläche](../vsto/office-ui-customization.md)   
 [Project 2010 und Projektserver 2010 in Office-Entwicklung](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  