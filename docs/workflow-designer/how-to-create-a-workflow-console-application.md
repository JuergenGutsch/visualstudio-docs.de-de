---
title: "Vorgehensweise: erstellen eine Konsolenanwendung für Workflows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: fcadbe113e92c761559161bdd8a7eba6e95937d3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-workflow-console-application"></a>Vorgehensweise: Erstellen einer Konsolenanwendung für Workflows
Mit [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] können Sie Workflows zum Ausführen von Systemprozessen oder menschlichen Prozessen erstellen. Der [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] stellt die Entwurfsoberfläche zum Erstellen dieser Workflows bereit. Der [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] kann verwendet werden, um Workflows in [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zu erstellen, oder er kann in andere Anwendungen integriert werden, die den Designer neu hosten.  
  
 In diesem Thema wird beschrieben, wie der [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] verwendet wird, um einen Workflow in einer Konsolenanwendung zu erstellen.  
  
### <a name="to-create-a-workflow-console-application"></a>So erstellen Sie eine Konsolenanwendung für Workflows  
  
1.  Starten Sie [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
2.  Auf der **Datei** Sie im Menü **neu**, und wählen Sie dann **Projekt...** .  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **installierte Vorlagen** klicken Sie im Bereich **Workflow** entweder aus der **Visual C#-** oder **Visual Basic** Gruppierungen, abhängig von Ihrer bevorzugter Sprache.  
  
4.  Wählen Sie im mittleren Bereich **Workflowkonsolenanwendung**.  
  
5.  In der **Namen** Geben Sie einen beschreibenden Namen für das Projekt in der es einfach identifizieren zu können.  
  
6.  In der **Speicherort** Geben Sie das Verzeichnis, in dem Sie das Projekt gespeichert werden soll, oder klicken möchten **Durchsuchen** navigieren.  
  
7.  In der **Lösung** Geben Sie den Namen für die neue Projektmappe. Klicken Sie auf **OK** zum Erstellen der Anwendung.  
  
    > [!NOTE]
    >  Wenn Sie einer vorhandenen Projektmappe eine workflowkonsolenanwendung hinzufügen möchten, öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klicken Sie mit der mit der rechten Maustaste auf die Projektmappe in **Projektmappen-Explorer**, und wählen Sie **hinzufügen**, klicken Sie dann  **Neues Projekt...**  So öffnen die **neues Projekt** (Dialogfeld). Fahren Sie wie oben in dieser Prozedur beschrieben fort.  
  
8.  Die Projektvorlage erstellt eine Workflowdefinition in XAML, und die Konsolenanwendungsdefinition ist in Quellcode. Der [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] wird geöffnet und zeigt den Canvas für den Workflow an, den Sie erstellt haben.  
  
9. Um einen Workflow zu verfassen, ziehen Sie Aktivitäten oder andere Workflowelemente von der **Toolbox** auf die Entwurfsoberfläche in Ihrem Workflow.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines Workflowprojekts](../workflow-designer/creating-a-workflow-project.md)