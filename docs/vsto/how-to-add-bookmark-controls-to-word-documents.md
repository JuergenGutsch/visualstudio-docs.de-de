---
title: "Vorgehensweise: Hinzufügen von Lesezeichen-Steuerelementen zu Word-Dokumenten | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VST.Bookmark.Dialog
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Bookmark control, adding to documents
- Create Bookmark Control dialog box
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 2ebe8536887f2f60876b64407ffb96cdaf4618c9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-bookmark-controls-to-word-documents"></a>Gewusst wie: Hinzufügen von Bookmark-Steuerelementen zu Word-Dokumenten
  In Projekten auf Dokumentebene können Sie dem Dokument in Ihrem Projekt zur Entwurfs- oder Laufzeit <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente hinzufügen. In VSTO-Add-In-Projekten können Sie einem beliebigen geöffneten Dokument zur Laufzeit <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente hinzufügen.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 In diesem Thema werden die folgenden Aufgaben beschrieben:  
  
-   [Hinzufügen von Lesezeichen-Steuerelementen zur Entwurfszeit](#designtime)  
  
-   [Hinzufügen von Lesezeichen-Steuerelementen zur Laufzeit in einem Projekt auf Dokumentebene](#runtimedoclevel)  
  
-   [Hinzufügen von Lesezeichen-Steuerelementen zur Laufzeit in einem VSTO-Add-In-Projekt](#runtimeaddin)  
  
 Weitere Informationen zu <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelementen finden Sie unter [Bookmark Control](../vsto/bookmark-control.md).  
  
##  <a name="designtime"></a> Adding Bookmark Controls at Design Time  
 Es gibt mehrere Möglichkeiten, wie Sie einem Dokument in einem Projekt auf Dokumentebene zur Entwurfszeit <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente hinzufügen können:  
  
-   Die **Toolbox**von Visual Studio.  
  
     Sie können das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement aus der **Toolbox** in Ihr Dokument ziehen. Möglicherweise entscheiden Sie sich für diese Möglichkeit, falls Sie die **Toolbox** bereits zum Hinzufügen von Windows Forms-Steuerelementen zu Ihrem Dokument verwenden.  
  
-   In Word.  
  
     Sie können Ihrem Dokument das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement auf die gleiche Weise wie das systemeigene Lesezeichen hinzufügen. Der Vorteil dieser Vorgehensweise besteht darin, dass Sie das Steuerelement bei der Erstellung benennen können.  
  
-   Im Fenster **Datenquellen** .  
  
     Sie können das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement vom Fenster **Datenquellen** auf Ihr Dokument ziehen. Dies ist hilfreich, wenn Sie das Steuerelement gleichzeitig an Daten binden möchten. Sie können das Hoststeuerelement auf die gleiche Weise hinzufügen wie das Windows Forms-Steuerelement aus dem Fenster **Datenquellen** . Weitere Informationen finden Sie unter [Data Binding and Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
#### <a name="to-add-a-bookmark-control-to-a-document-from-the-toolbox"></a>So fügen Sie einem Dokument ein Lesezeichen-Steuerelement aus der Toolbox hinzu  
  
1.  Öffnen Sie die **Toolbox** , und klicken Sie auf die Registerkarte **Word-Steuerelemente** .  
  
2.  Ziehen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement auf das Dokument.  
  
     Das Dialogfeld **Lesezeichen hinzufügen** wird angezeigt.  
  
3.  Wählen Sie den Text oder andere Elemente aus, die Sie in das Lesezeichen einschließen möchten.  
  
4.  Klicken Sie auf **OK**.  
  
     Wenn Sie nicht den Standardnamen für das Lesezeichen beibehalten möchten, können Sie den Namen im Fenster **Eigenschaften** ändern.  
  
#### <a name="to-add-a-bookmark-control-to-a-document-in-word"></a>So fügen Sie einem Dokument in Word ein Lesezeichen-Steuerelement hinzu  
  
1.  Platzieren Sie den Cursor in dem Dokument, das im [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] -Designer gehostet wird, an der Stelle, an der Sie das Lesezeichen hinzufügen möchten, oder wählen Sie den Text aus, der vom Lesezeichen eingeschlossen werden soll.  
  
2.  Klicken Sie auf der Registerkarte **Einfügen** des Menübands in der Gruppe **Links** auf die Schaltfläche **Lesezeichen** .  
  
3.  Geben Sie im Dialogfeld **Lesezeichen** den Namen des neuen Lesezeichens ein, und klicken Sie auf **Hinzufügen**.  
  
##  <a name="runtimedoclevel"></a> Adding Bookmark Controls at Run Time in a Document-Level Project  
 Sie können einem Dokument zur Laufzeit <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente programmgesteuert hinzufügen, indem Sie die Methoden der <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> -Eigenschaft der `ThisDocument` -Klasse im Projekt verwenden. Es gibt zwei Methodenüberladungen, mit denen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement auf die folgenden Weisen hinzufügen können:  
  
-   Fügen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> in einem angegebenen Bereich hinzu.  
  
-   Fügen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> hinzu, das auf einem systemeigenen Lesezeichen im Dokument basiert (d. h. ein <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dynamisch erstellte <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente werden nicht dauerhaft im Dokument gespeichert, wenn das Dokument geschlossen ist. Ein systemeigenes <xref:Microsoft.Office.Interop.Word.Bookmark> verbleibt jedoch im Dokument. Beim nächsten Öffnen des Dokuments können Sie ein auf einem systemeigenen Lesezeichen basierendes <xref:Microsoft.Office.Tools.Word.Bookmark> neu erstellen. Weitere Informationen finden Sie unter [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-to-a-document-programmatically"></a>So fügen Sie einem Dokument ein Lesezeichen-Steuerelement programmgesteuert hinzu  
  
1.  Fügen Sie im `ThisDocument_Startup` -Ereignishandler Ihres Projekts den folgenden Code ein, um das <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement dem ersten Absatz des Dokuments hinzuzufügen.  
  
     [!code-csharp[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/CSharp/trin_vstcorehostcontrolsword/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreHostControlsWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsWordVB/ThisDocument.vb#1)]  
  
    > [!NOTE]  
    >  Wenn Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement von einem vorhandenen <xref:Microsoft.Office.Interop.Word.Bookmark>erstellen möchten, verwenden Sie die <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> -Methode und übergeben das vorhandene <xref:Microsoft.Office.Interop.Word.Bookmark>.  
  
##  <a name="runtimeaddin"></a> Adding Bookmark Controls at Run Time in an VSTO Add-in project  
 Sie können einem beliebigen geöffneten Dokument mithilfe eines VSTO-Add-Ins zur Laufzeit programmgesteuert <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente hinzufügen. Zu diesem Zweck generieren Sie ein <xref:Microsoft.Office.Tools.Word.Document> -Hostelement, das auf einem geöffneten Dokument basiert, und verwenden dann die Methoden der <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> -Eigenschaft dieses Hostelements. Es gibt zwei Methodenüberladungen, mit denen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelement auf die folgenden Weisen hinzufügen können:  
  
-   Fügen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> in einem angegebenen Bereich hinzu.  
  
-   Fügen Sie ein <xref:Microsoft.Office.Tools.Word.Bookmark> hinzu, das auf einem systemeigenen Lesezeichen im Dokument basiert (d. h. ein <xref:Microsoft.Office.Interop.Word.Bookmark>).  
  
 Dynamisch erstellte <xref:Microsoft.Office.Tools.Word.Bookmark> -Steuerelemente werden nicht dauerhaft im Dokument gespeichert, wenn das Dokument geschlossen ist. Ein systemeigenes <xref:Microsoft.Office.Interop.Word.Bookmark> verbleibt jedoch im Dokument. Beim nächsten Öffnen des Dokuments können Sie ein auf einem systemeigenen Lesezeichen basierendes <xref:Microsoft.Office.Tools.Word.Bookmark> neu erstellen. Weitere Informationen finden Sie unter [Persisting Dynamic Controls in Office Documents](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
 Weitere Informationen zum Generieren von Hostelementen in VSTO-Add-in-Projekten finden Sie unter [Erweitern von Word-Dokumenten und Excel-Arbeitsmappen in VSTO-Add-ins zur Laufzeit](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
#### <a name="to-add-a-bookmark-control-at-a-specified-range"></a>So fügen Sie ein Lesezeichen-Steuerelement in einem angegebenen Bereich hinzu  
  
1.  Verwenden Sie die <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> -Methode, und übergeben Sie den <xref:Microsoft.Office.Interop.Word.Range> an der Stelle, an der Sie das <xref:Microsoft.Office.Tools.Word.Bookmark>hinzufügen möchten.  
  
     Im folgenden Codebeispiel wird ein neues <xref:Microsoft.Office.Tools.Word.Bookmark> am Anfang des aktiven Dokuments hinzugefügt. Um dieses Beispiel zu verwenden, führen Sie den Code vom `ThisAddIn_Startup` -Ereignishandler in einem Word-VSTO-Add-In-Projekt aus.  
  
     [!code-vb[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#4)]
     [!code-csharp[Trin_WordAddInDynamicControls#4](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#4)]  
  
#### <a name="to-add-a-bookmark-control-that-is-based-on-a-native-bookmark-control"></a>So fügen Sie ein Lesezeichen-Steuerelement hinzu, das auf einem systemeigenen Lesezeichen-Steuerelement basiert  
  
1.  Verwenden Sie die <xref:Microsoft.Office.Tools.Word.ControlCollection.AddBookmark%2A> -Methode, und übergeben Sie das vorhandene <xref:Microsoft.Office.Interop.Word.Bookmark> , das Sie als Grundlage für das neue <xref:Microsoft.Office.Tools.Word.Bookmark>verwenden möchten.  
  
     Im folgenden Codebeispiel wird ein neues <xref:Microsoft.Office.Tools.Word.Bookmark> basierend auf dem ersten <xref:Microsoft.Office.Interop.Word.Bookmark> im aktiven Dokument erstellt. Um dieses Beispiel zu verwenden, führen Sie den Code vom `ThisAddIn_Startup` -Ereignishandler in einem Word-VSTO-Add-In-Projekt aus.  
  
     [!code-vb[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#5)]
     [!code-csharp[Trin_WordAddInDynamicControls#5](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisieren von Word mithilfe von erweiterten Objekten](../vsto/automating-word-by-using-extended-objects.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Hinzufügen von Steuerelementen zu Office-Dokumenten zur Laufzeit](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Programmieren von Anpassungen auf Dokumentebene](../vsto/programming-document-level-customizations.md)   
 [Vorgehensweise: Ändern der Größe von Bookmark-Steuerelementen](../vsto/how-to-resize-bookmark-controls.md)  
  
  