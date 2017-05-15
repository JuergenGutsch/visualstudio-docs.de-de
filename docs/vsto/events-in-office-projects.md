---
title: "Ereignisse in Office-Projekten"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Sheet1_Startup"
  - "ThisDocument_Shutdown"
  - "ThisDocument_Startup"
  - "Add-Ins auf Anwendungsebene [Office-Entwicklung in Visual Studio], Ereignisse"
  - "Ereignishandler [Office-Entwicklung in Visual Studio]"
  - "ThisWorkbook_Startup"
  - "Sheet2_Startup"
  - "ThisWorkbook_Shutdown"
  - "Anpassungen auf Dokumentebene [Office-Entwicklung in Visual Studio], Ereignisse"
  - "Sheet2_Shutdown"
  - "Startup-Ereignis"
  - "Sheet3_Shutdown"
  - "Add-Ins [Office-Entwicklung in Visual Studio], Ereignisse"
  - "Shutdown-Ereignis"
  - "ThisAddIn_Startup"
  - "Sheet3_Startup"
  - "Startup-Methode [Office-Entwicklung in Visual Studio]"
  - "Shutdown-Methode [Office-Entwicklung in Visual Studio]"
  - "Sheet1_Shutdown"
  - "Ereignisse [Office-Entwicklung in Visual Studio]"
  - "ThisAddIn_Shutdown"
ms.assetid: 666d7f23-ef85-4f2e-9cd3-258df5bdc6fd
caps.latest.revision: 51
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 50
---
# Ereignisse in Office-Projekten
  Jede Office\-Projektvorlage generiert automatisch mehrere Ereignishandler. Die Ereignishandler für Anpassungen auf Dokumentebene unterscheiden sich geringfügig von Ereignishandlern für VSTO\-Add\-Ins.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## Projekte auf Dokumentebene  
 Visual Studio stellt generierten Code hinter neuen oder vorhandenen Dokumenten oder Arbeitsblättern in Anpassungen auf Dokumentebene bereit. Mit diesem Code werden zwei unterschiedliche Ereignisse ausgelöst: **Startup** und **Shutdown**.  
  
### Startup\-Ereignis  
 Das **Startup**\-Ereignis wird für jedes Hostelement ausgelöst \(Dokument, Arbeitsmappe oder Arbeitsblatt\), nachdem das Dokument und der gesamte Initialisierungscode in der Assembly ausgeführt wurde. Dies ist das letzte ausgeführte Element im Konstruktor der Klasse, in dem Ihr Code ausgeführt wird. Weitere Informationen zu Hostelementen finden Sie unter [Übersicht über Hostelemente und Hoststeuerelemente](../vsto/host-items-and-host-controls-overview.md).  
  
 Wenn Sie ein Projekt auf Dokumentebene erstellen, erstellt Visual Studio Ereignishandler für das **Startup**\-Ereignis in den generierten Codedateien:  
  
-   Für Microsoft Office Word\-Projekte hat der Ereignishandler den Namen `ThisDocument_Startup`.  
  
-   Für Microsoft Office Excel\-Projekte haben die Ereignishandler die folgenden Namen:  
  
    -   `Sheet1_Startup`  
  
    -   `Sheet2_Startup`  
  
    -   `Sheet3_Startup`  
  
    -   `ThisWorkbook_Startup`  
  
### Shutdown\-Ereignis  
 Das  **Shutdown** \-Ereignis wird für jedes Hostelement \(Dokument oder Arbeitsblatt\) ausgelöst, wenn die Anwendungsdomäne, in der Ihr Code geladen wurde, entladen werden soll. Dies ist das letzte Element, das beim Entladen in der Klasse aufgerufen wird.  
  
 Wenn Sie ein Projekt auf Dokumentebene erstellen, erstellt Visual Studio Ereignishandler für das  **Shutdown** \-Ereignis in den generierten Codedateien:  
  
-   Für Microsoft Office Word\-Projekte hat der Ereignishandler den Namen `ThisDocument_Shutdown`.  
  
-   Für Microsoft Office Excel\-Projekte haben die Ereignishandler die folgenden Namen:  
  
    -   `Sheet1_Shutdown`  
  
    -   `Sheet2_Shutdown`  
  
    -   `Sheet3_Shutdown`  
  
    -   `ThisWorkbook_Shutdown`  
  
> [!NOTE]  
>  Vermeiden Sie es, Steuerelemente während des **Shutdown**\-Ereignishandlerzeitraums des Dokuments programmgesteuert zu entfernen. Die Benutzeroberflächenelemente des Dokuments sind nicht mehr verfügbar, wenn das **Shutdown**\-Ereignis eintritt. Wenn Sie Steuerelemente vor dem Schließen der Anwendung entfernen möchten, können Sie Ihren Code einem anderen Ereignishandler hinzufügen, z. B. **BeforeClose** oder **BeforeSave**.  
  
### Ereignishandler\-Methodendeklarationen  
 An jede Ereignishandler\-Methodendeklaration werden die gleichen Argumente übergeben: *sender* und *e*. In Excel bezieht sich das *sender*\-Argument auf das Arbeitsblatt, z. B. `Sheet1` oder `Sheet2`. In Word bezieht sich das *sender*\-Argument auf das Dokument. Das *e*\-Argument bezieht sich auf die Standardargumente für ein Ereignis, die in diesem Fall nicht verwendet werden.  
  
 Im folgenden Codebeispiel werden die Standardereignishandler in Projekten auf Dokumentebene für Word veranschaulicht.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#121](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#121)]
 [!code-vb[Trin_VstcoreWordAutomation#121](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#121)]  
  
 Im folgenden Codebeispiel werden die Standardereignishandler in Projekten auf Dokumentebene für Excel veranschaulicht.  
  
> [!NOTE]  
>  Im folgenden Codebeispiel werden die Ereignishandler in der `Sheet1`\-Klasse veranschaulicht. Die Namen der Ereignishandler in anderen Hostelementklassen entsprechen dem Klassennamen. In der `Sheet2`\-Klasse hat der **Startup**\-Ereignishandler beispielsweise den Namen `Sheet2_Startup`. In der `ThisWorkbook`\-Klasse hat der **Startup**\-Ereignishandler den Namen `ThisWorkbook_Startup`.  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#83](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#83)]
 [!code-vb[Trin_VstcoreExcelAutomation#83](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#83)]  
  
### Reihenfolge der Ereignisse in Excel\-Projekten auf Dokumentebene  
 Die **Startup**\-Ereignishandler in Excel\-Projekten werden in dieser Reihenfolge aufgerufen:  
  
1.  `ThisWorkbook_Startup`.  
  
2.  `Sheet1_Startup`.  
  
3.  `Sheet2_Startup`.  
  
4.  `Sheet3_Startup`.  
  
5.  Andere Blätter laut Reihenfolge.  
  
 Die  **Shutdown**\-Ereignishandler in einer Arbeitsmappen\-Projektmappe werden in dieser Reihenfolge aufgerufen:  
  
1.  `ThisWorkbook_Shutdown`.  
  
2.  `Sheet1_Shutdown`.  
  
3.  `Sheet2_Shutdown`.  
  
4.  `Sheet3_Shutdown`.  
  
5.  Andere Blätter laut Reihenfolge.  
  
 Die Reihenfolge wird festgelegt, wenn das Projekt kompiliert wird. Wenn der Benutzer die Blätter zur Laufzeit anders anordnet, ändert sich dadurch nicht die Reihenfolge, in der die Ereignisse beim nächsten Öffnen oder Schließen der Arbeitsmappe ausgelöst werden.  
  
## VSTO\-Add\-In\-Projekte  
 Visual Studio stellt generierten Code in VSTO\-Add\-Ins bereit. Mit diesem Code werden zwei unterschiedliche Ereignisse ausgelöst: <xref:Microsoft.Office.Tools.AddInBase.Startup> und <xref:Microsoft.Office.Tools.AddInBase.Shutdown>.  
  
### Startup\-Ereignis  
 Das <xref:Microsoft.Office.Tools.AddIn.Startup>\-Ereignis wird ausgelöst, nachdem das VSTO\-Add\-In geladen und der gesamte Initialisierungscode in der Assembly ausgeführt wurde. Dieses Ereignis wird mit der `ThisAddIn_Startup`\-Methode in der generierten Codedatei behandelt.  
  
 Code im `ThisAddIn_Startup`\-Ereignishandler ist der erste Benutzercode, der ausgeführt wird, es sei denn, Ihr VSTO\-Add\-In setzt die <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A>\-Methode außer Kraft. In diesem Fall wird der `ThisAddIn_Startup`\-Ereignishandler nach <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> aufgerufen.  
  
 Fügen Sie im `ThisAdd-In_Startup`\-Ereignishandler keinen Code hinzu, wenn der Code erfordert, dass ein Dokument geöffnet ist. Fügen Sie stattdessen diesen Code einem Ereignis hinzu, welches durch die Office\-Anwendung ausgelöst wird, wenn vom Benutzer ein Dokument erstellt oder geöffnet wird. Weitere Informationen finden Sie unter [Zugreifen auf ein Dokument beim Starten der Office-Anwendung](../vsto/programming-vsto-add-ins.md#AccessingDocuments).  
  
 Weitere Informationen zur Startsequenz von VSTO\-Add\-Ins finden Sie unter [Architektur von VSTO-Add-Ins](../vsto/architecture-of-vsto-add-ins.md).  
  
### Shutdown\-Ereignis  
 Das <xref:Microsoft.Office.Tools.AddInBase.Shutdown>\-Ereignis wird ausgelöst, wenn die Anwendungsdomäne, in der Ihr Code geladen wird, entladen werden soll. Dieses Ereignis wird mit der `ThisAddIn_Shutdown`\-Methode in der generierten Codedatei behandelt. Dieser Ereignishandler ist der letzte Benutzercode, der beim Entladen des VSTO\-Add\-Ins ausgeführt wird.  
  
#### Shutdown\-Ereignis in Outlook\-VSTO\-Add\-Ins  
 Das <xref:Microsoft.Office.Tools.AddInBase.Shutdown>\-Ereignis wird nur ausgelöst, wenn der Benutzer das VSTO\-Add\-In in Outlook über das Dialogfeld "COM\-Add\-Ins" deaktiviert. Es wird nicht ausgelöst, wenn Outlook beendet wird. Wenn Sie über Code verfügen, der beim Beenden von Outlook ausgeführt werden muss, sollten Sie eines der folgenden Ereignisse behandeln:  
  
-   Das <xref:Microsoft.Office.Interop.Outlook.ApplicationEvents_11_Event.Quit>\-Ereignis des <xref:Microsoft.Office.Interop.Outlook.Application>\-Objekts.  
  
-   Das <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close>\-Ereignis des <xref:Microsoft.Office.Interop.Outlook.Explorer>\-Objekts.  
  
> [!NOTE]  
>  Sie können für Outlook erzwingen, dass das <xref:Microsoft.Office.Tools.AddInBase.Shutdown>\-Ereignis beim Beenden ausgelöst wird, indem Sie dies in der Registrierung ändern. Aber wenn ein Administrator diese Einstellung zurücksetzt, wird der Code, den Sie der `ThisAddIn_Shutdown`\-Methode hinzufügen, beim Beenden von Outlook nicht mehr ausgeführt. Weitere Informationen finden Sie unter [Shutdown\-Änderungen für Outlook 2010](http://go.microsoft.com/fwlink/?LinkID=184614).  
  
## Siehe auch  
 [Entwickeln von Office-Projektmappen](../vsto/developing-office-solutions.md)   
 [Gewusst wie: Erstellen von Office-Projekten in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programmieren von Anpassungen auf Dokumentebene](../vsto/programming-document-level-customizations.md)   
 [Programmieren von VSTO-Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Übersicht über Office-Projektvorlagen](../vsto/office-project-templates-overview.md)  
  
  