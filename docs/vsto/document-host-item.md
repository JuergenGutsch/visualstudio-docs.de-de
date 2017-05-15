---
title: "Dokumenthostelement"
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
  - "Dokumente [Office-Entwicklung in Visual Studio]"
  - "Dokumente [Office-Entwicklung in Visual Studio], Dokumenthostelement"
  - "Dokument-Hostelemente"
  - "Word [Office-Entwicklung in Visual Studio], Word-Dokumente"
  - "Word [Office-Entwicklung in Visual Studio]"
  - "Word-Dokumente"
  - "Hostelemente [Office-Entwicklung in Visual Studio], Dokument"
ms.assetid: 4c1963f2-e88e-4c68-9f3d-13dedebddde4
caps.latest.revision: 47
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# Dokumenthostelement
  Das <xref:Microsoft.Office.Tools.Word.Document> Hostelement ist ein Typ, der den <xref:Microsoft.Office.Interop.Word.Document>\-Typ aus der primären Interopassembly für Word erweitert. Das <xref:Microsoft.Office.Tools.Word.Document>\-Hostelement stellt die gleichen Eigenschaften, Methoden und Ereignisse wie ein <xref:Microsoft.Office.Interop.Word.Document>\-Objekt bereit, es macht jedoch auch zusätzliche Ereignisse verfügbar und fungiert als Container für Hoststeuerelemente und Windows Forms\-Steuerelemente.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 In Projekten auf Dokumentebene gibt es ein <xref:Microsoft.Office.Tools.Word.Document>\-Standardhostelement, das das Dokument im Projekt darstellt. In VSTO\-Add\-In\-Projekten können Sie <xref:Microsoft.Office.Tools.Word.Document>\-Hostelemente zur Laufzeit generieren.  
  
## Grundlegendes zum Dokumenthostelement in Projekten auf Dokumentebene  
 Verwenden Sie die `ThisDocument`\-Klasse, um auf das Dokument im Projekt zuzugreifen. Wenn Sie ein Projekt auf Dokumentebene erstellen, generiert Visual Studio die `ThisDocument`\-Klasse, die als Kommunikationsverbindung zwischen Word und dem Anpassungscode dient. Über die `ThisDocument`\-Klasse erhalten Sie Zugriff auf Member des <xref:Microsoft.Office.Tools.Word.Document>\-Hostelements, um grundlegende Aufgaben in der Anpassung auszuführen, z. B. das Ausführen von Code, wenn das Dokument geöffnet bzw. geschlossen wird. Sie können die Klasse auch verwenden, um dem Dokument Steuerelemente hinzuzufügen. Sie können Steuerelemente an Daten binden, Benutzerinformationen abfragen und auf Benutzeraktionen reagieren, indem Sie verschiedene Gruppen von Steuerelementen kombinieren und Code schreiben. Weitere Informationen finden Sie unter [Programmieren von Anpassungen auf Dokumentebene](../vsto/programming-document-level-customizations.md).  
  
 Die `ThisDocument`\-Klasse stellt einen Ausgangspunkt bereit, an dem Sie mit dem Schreiben von Code im Projekt beginnen können. Da die Klasse die gleichen Eigenschaften, Methoden und Ereignisse wie das <xref:Microsoft.Office.Interop.Word.Document>\-Objekt in der primären Interop\_Assembly für Word bereitstellt, können Sie auch mit `ThisDocument` auf das Word\-Objektmodell zugreifen. Weitere Informationen finden Sie unter [Übersicht über das Word-Objektmodell](../vsto/word-object-model-overview.md).  
  
### Einschränkungen des Dokumenthostelements in Projekten auf Dokumentebene  
 Ein Projekt auf Dokumentebene kann nur ein <xref:Microsoft.Office.Tools.Word.Document>\-Hostelement \(die `ThisDocument`\-Klasse\) enthalten. Sie können dem Projekt zur Entwurfszeit keine neuen <xref:Microsoft.Office.Tools.Word.Document>\-Hostelemente hinzufügen, und Sie können zur Laufzeit von einer Anpassung auf Dokumentebene keine neuen <xref:Microsoft.Office.Tools.Word.Document>\-Hostelemente erstellen.  
  
 Wenn Sie zur Laufzeit ein neues Word\-Dokument erstellen, ist es vom Typ <xref:Microsoft.Office.Interop.Word.Document>. Da es kein Hostelement ist, kann es keine Hoststeuerelemente bzw. Windows Forms\-Steuerelemente enthalten. Weitere Informationen über das Erstellen von Dokumenten zur Laufzeit finden Sie unter [Gewusst wie: Programmgesteuertes Erstellen neuer Dokumente](../vsto/how-to-programmatically-create-new-documents.md).  
  
## Grundlegendes zu Dokument\-Hostelemente in Projekten auf Anwendungsebene  
 In VSTO\-Add\-In\-Projekten können Sie für jedes Dokument, das in Word geöffnet ist, zur Laufzeit ein <xref:Microsoft.Office.Tools.Word.Document>\-Hostelement erstellen. Sie können das <xref:Microsoft.Office.Tools.Word.Document>\-Hostelement verwenden, um dem zugeordneten Dokument Steuerelemente hinzuzufügen, oder um Ereignisse zu behandeln, die für <xref:Microsoft.Office.Interop.Word.Document>\-Objekte nicht verfügbar sind.  
  
 Verwenden Sie zum Generieren eines <xref:Microsoft.Office.Tools.Word.Document>\-Hostelements die GetVstoObject\-Methode. Weitere Informationen finden Sie unter [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-Ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## Siehe auch  
 [Übersicht über Hostelemente und Hoststeuerelemente](../vsto/host-items-and-host-controls-overview.md)   
 [Automatisieren von Word mithilfe von erweiterten Objekten](../vsto/automating-word-by-using-extended-objects.md)   
 [Übersicht über das Word-Objektmodell](../vsto/word-object-model-overview.md)   
 [Programmgesteuerte Einschränkungen von Hostelementen und Hoststeuerelementen](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-Ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  