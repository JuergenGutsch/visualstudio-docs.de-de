---
title: "Vorgehensweise: Hinzufügen eines Aktionsbereichs zu Word-Dokumenten oder Excel-Arbeitsmappen | Microsoft Docs"
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
- smart documents [Office development in Visual Studio], creating in Word
- smart documents [Office development in Visual Studio], adding controls
- actions panes [Office development in Visual Studio], creating in Word
- actions panes [Office development in Visual Studio], adding controls
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: d259442104cfbd6b072d0068ab5f2b4f182f027f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks"></a>Gewusst wie: Hinzufügen eines Aktionsbereichs zu Word-Dokumenten oder Excel-Arbeitsmappen
  Um ein Microsoft Office Word-Dokument oder einer Microsoft Excel-Arbeitsmappe einen Aktionsbereich hinzuzufügen, müssen Sie zunächst erstellen Sie ein Windows Forms-Benutzersteuerelement. Fügen Sie dann auf das Benutzersteuerelement an das <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> Eigenschaft von der `ThisDocument.ActionsPane` Feld (Wort) oder `ThisWorkbook.ActionsPane` Feld (Excel) in Ihrem Projekt.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Auf Ihrem Computer werden möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio angezeigt als die in den folgenden Anweisungen aufgeführten. Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="creating-the-user-control"></a>Erstellen des Benutzersteuerelements  
 Das folgende Verfahren zeigt, wie in einem Wort Benutzersteuerelement zu erstellen oder Excel-Projekt. Es fügt auch eine Schaltfläche auf das Benutzersteuerelement, das Text in das Dokument oder die Arbeitsmappe ausgibt, wenn darauf geklickt wird.  
  
#### <a name="to-create-the-user-control"></a>Um das Benutzersteuerelement zu erstellen.  
  
1.  Öffnen Sie das Projekt für Word oder Excel auf Dokumentebene in Visual Studio.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
3.  In der **neues Element hinzufügen** wählen Sie im Dialogfeld **Aktionsbereich-Steuerelement**, nennen Sie sie **HelloControl**, und klicken Sie auf **hinzufügen**.  
  
    > [!NOTE]  
    >  Sie können alternativ Hinzufügen einer **Benutzersteuerelement** Element aus, um das Projekt. Die Klassen generiert werden, indem Sie die **Aktionsbereich-Steuerelement** und **Benutzersteuerelement** Elemente sind funktional äquivalent.  
  
4.  Aus der **Windows Forms** auf der Registerkarte die **Toolbox** ziehen Sie eine **Schaltfläche** -Steuerelement auf das Steuerelement.  
  
    > [!NOTE]  
    >  Wenn das Steuerelement nicht im Designer sichtbar ist, doppelklicken klicken Sie auf **HelloControl** in **Projektmappen-Explorer**.  
  
5.  Fügen Sie den Code, der <xref:System.Windows.Forms.Control.Click> -Ereignishandler der Schaltfläche. Das folgende Beispiel zeigt Code für Microsoft Office Word-Dokument.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#12)]
     [!code-vb[Trin_VstcoreActionsPaneWord#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/HelloControl.vb#12)]  
  
6.  In c# müssen Sie einen Ereignishandler für das Schaltflächen-Klickereignis hinzufügen. Sie können diesen Code im Platzieren der `HelloControl` Konstruktor nach dem Aufruf von `IntializeComponent`.  
  
     Informationen über das Erstellen von Ereignishandlern finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern in Office-Projekten](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#13](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/HelloControl.cs#13)]  
  
## <a name="adding-the-user-control-to-the-actions-pane"></a>Hinzufügen des Benutzersteuerelements zum Aktionsbereich  
 Um den Aktionsbereich anzuzeigen, fügen Sie das Benutzersteuerelement an das <xref:Microsoft.Office.Tools.ActionsPane.Controls%2A> Eigenschaft von der `ThisDocument.ActionsPane` Feld (Wort) oder `ThisWorkbook.ActionsPane` Feld (Excel).  
  
#### <a name="to-add-the-user-control-to-the-actions-pane"></a>Der Aktionsbereich das Benutzersteuerelement hinzu  
  
1.  Fügen Sie folgenden Code, der `ThisDocument` oder `ThisWorkbook` Klasse als eine Deklaration auf Klassenebene (Fügen Sie diesen Code nicht auf eine Methode).  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#14)]
     [!code-vb[Trin_VstcoreActionsPaneWord#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#14)]  
  
2.  Fügen Sie den folgenden Code hinzu der `ThisDocument_Startup` -Ereignishandler des der `ThisDocument` Klasse oder die `ThisWorkbook_Startup` -Ereignishandler des der `ThisWorkbook` Klasse.  
  
     [!code-csharp[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/CSharp/Trin_VstcoreActionsPaneWordCS/ThisDocument.cs#15)]
     [!code-vb[Trin_VstcoreActionsPaneWord#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreActionsPaneWordVB/ThisDocument.vb#15)]  
  
## <a name="see-also"></a>Siehe auch  
 [Aktionsbereichsübersicht](../vsto/actions-pane-overview.md)   
 [Exemplarische Vorgehensweise: Einfügen von Text in ein Dokument aus einem Aktionsbereich](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)   
 [Vorgehensweise: Verwalten des Steuerelementlayouts in Aktionsbereichen](../vsto/how-to-manage-control-layout-on-actions-panes.md)   
 [Exemplarische Vorgehensweise: Einfügen von Text in ein Dokument aus einem Aktionsbereich](../vsto/walkthrough-inserting-text-into-a-document-from-an-actions-pane.md)  
  
  