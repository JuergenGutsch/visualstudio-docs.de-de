---
title: "Persist-Aktivitätsdesigners | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 3bd0ef80e5255a828ad31ebfa2398ff6f8b1a1e8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="persist-activity-designer"></a>Persist-Aktivitätsdesigners
Die **Persist** Aktivitäts-Designer dient zum Erstellen und Konfigurieren einer <xref:System.Activities.Statements.Persist> Aktivität.  
  
## <a name="the-persist-activity"></a>Die Persist-Aktivität  
 Wenn möglich, speichert die <xref:System.Activities.Statements.Persist>-Aktivität einen Workflow auf dem Datenträger. Die <xref:System.Activities.Statements.Persist>-Aktivität kann nicht in einem Bereich ohne Persistenz ausgeführt werden, z. B. innerhalb einer <xref:System.Activities.Statements.TransactionScope>-Aktivität. Wenn Sie eine <xref:System.Activities.Statements.Persist>-Aktivität in einem Bereich ohne Persistenz verwenden, wird zur Laufzeit eine Ausnahme ausgelöst.  
  
### <a name="using-the-persist-activity-designer"></a>Verwenden des Persist-Aktivitätsdesigners  
 Die **Persist** Aktivitäts-Designer finden Sie in der **Runtime** Kategorie von der **Toolbox**, die erfolgt durch Klicken auf die **Toolbox** Registerkarte "(Wählen Sie alternativ **Toolbox** aus der **Ansicht** Menüs oder STRG + ALT + X.)  
  
 Die **Persist** Aktivitäts-Designer gezogen werden kann, aus der **Toolbox** gezogen und auf die [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] -Oberfläche ablegen, wo Aktivitäten normalerweise platziert werden, z. B. in einem <xref:System.Activities.Statements.Sequence>. Dies erstellt eine <xref:System.Activities.Statements.Persist> -Aktivität mit dem standardmäßigen **DisplayName** -Standardwert Persist. Die <xref:System.Activities.Activity.DisplayName%2A> kann im Header des bearbeitet werden die **Persist** Aktivitäts-Designer oder in der **DisplayName** Feld des Eigenschaftenrasters.  
  
### <a name="the-persist-properties"></a>Die Persist-Eigenschaften  
 In der folgenden Tabelle werden die <xref:System.Activities.Statements.Persist>-Eigenschaften aufgeführt, und es wird beschrieben, wie sie im Designer verwendet werden. Diese Eigenschaften können im Eigenschaftenraster bearbeitet werden, einige davon können auch auf der [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]-Oberfläche bearbeitet werden.  
  
|Eigenschaftenname|Erforderlich|Verwendung|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Der Anzeigename der <xref:System.Activities.Statements.Persist>-Aktivität. Der Standardwert lautet Persist. Obwohl der Anzeigename nicht unbedingt erforderlich ist, wird empfohlen, einen Anzeigenamen zu verwenden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Common Language Runtime](../workflow-designer/runtime-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)