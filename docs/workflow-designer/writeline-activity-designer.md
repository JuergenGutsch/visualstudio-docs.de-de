---
title: "WriteLine-Aktivitätsdesigner | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 3f531539737389938a7ff0a757235d8c5c2af263
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="writeline-activity-designer"></a>WriteLine-Aktivitätsdesigner
Die **WriteLine** Aktivitäts-Designer dient zum Erstellen und Konfigurieren einer <xref:System.Activities.Statements.WriteLine> Aktivität.  
  
## <a name="the-writeline-activity"></a>Die WriteLine-Aktivität  
 Die <xref:System.Activities.Statements.WriteLine>-Aktivität schreibt Text in ein angegebenes <xref:System.IO.TextWriter>-Objekt. Wenn kein <xref:System.IO.TextWriter> angegeben wird, schreibt <xref:System.Activities.Statements.WriteLine> den Text in die Konsole.  
  
### <a name="using-the-writeline-activity-designer"></a>Verwenden des WriteLine-Aktivitätsdesigners  
 Die **WriteLine** Aktivitäts-Designer finden Sie in der **primitive** Kategorie der **Toolbox**, die erfolgt durch Klicken auf die **Toolbox**auf der Registerkarte die [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (Wählen Sie alternativ **Symbolleiste** aus der **Ansicht** Menüs oder STRG + ALT + X drücken.)  
  
 Die **WriteLine** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** gezogen und auf die [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] -Oberfläche ablegen, wo Aktivitäten normalerweise platziert werden, z. B. in einem <xref:System.Activities.Statements.Sequence>. Daraufhin wird eine <xref:System.Activities.Statements.WriteLine>-Aktivität mit dem <xref:System.Activities.Activity.DisplayName%2A>-Standardwert WriteLine erstellt. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **WriteLine** Aktivitäts-Designer oder in der **DisplayName** Feld des Eigenschaftenrasters.  
  
### <a name="the-writeline-properties"></a>Die WriteLine-Eigenschaften  
 In der folgenden Tabelle werden die <xref:System.Activities.Statements.WriteLine>-Eigenschaften aufgeführt, und es wird beschrieben, wie sie im Designer verwendet werden. Diese Eigenschaften können im Eigenschaftenraster, einige davon auf der [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]-Designeroberfläche bearbeitet werden.  
  
|Eigenschaftenname|Erforderlich|Verwendung|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der Anzeigename der <xref:System.Activities.Statements.WriteLine>-Aktivität. Der Standardwert lautet WriteLine. Obwohl der <xref:System.Activities.Activity.DisplayName%2A>-Wert nicht zwingend erforderlich ist, wird empfohlen, einen Anzeigenamen zu verwenden.|  
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Der zu schreibende Text. Geben Sie zum Festlegen der Eigenschaft einen Visual Basic-Ausdruck in der **Text** Feld der **WriteLine** -Aktivitätsdesigner oder im Eigenschaftenraster.|  
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|Die <xref:System.IO.TextWriter>-Instanz, an die die <xref:System.Activities.Statements.WriteLine>-Aktivität den <xref:System.Activities.Statements.WriteLine.Text%2A>-Text ausgibt. Der Standardwert ist die Konsole.|  
  
## <a name="see-also"></a>Siehe auch  
 [Primitive Typen](../workflow-designer/primitives-activity-designers.md)   
 [Zuweisen](../workflow-designer/assign-activity-designer.md)   
 [Verzögerung](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)