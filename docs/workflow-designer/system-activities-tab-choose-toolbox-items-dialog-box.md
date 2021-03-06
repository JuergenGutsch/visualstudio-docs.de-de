---
title: "System.Activities (Registerkarte), wählen Sie im Dialogfeld \"Elemente\" Toolbox | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES_COMPONENTS
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES COMPONENTS
ms.assetid: cef390cd-eeda-42e6-9d2e-18c8325a4f06
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: ba4078a903c1e30b968928e13c8d160c898bbf0d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemactivities-tab-choose-toolbox-items-dialog-box"></a>System.Activities (Registerkarte), Toolboxelemente auswählen (Dialogfeld)
Diese Registerkarte die **Toolboxelemente auswählen** Dialogfeld zeigt eine Liste von [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] Aktivitäten, Vorlagen und Elemente, die Ihnen zur Verfügung. Um diese Liste anzuzeigen, wählen Sie **Toolboxelemente auswählen** aus der **Tools** Menü oder über das Kontextmenü der **Toolbox** auswählen und **Elemente auswählen**zum Anzeigen der **Toolboxelemente** (Dialogfeld), und wählen Sie dann seine **System.Activities** Registerkarte. Voreingestellt enthält die Liste Workflowaktivitäten aus den Assemblys System.Activities, System.ServiceModel.Activities und System.Activities.Core.Presentation; allerdings nur die vom System bereitgestellten Aktivitäten und Aktivitäten durch andere Assemblys, die angezeigt wird, im hinzugefügten der **Toolbox** sind standardmäßig aktiviert. Kürzlich hinzugefügte Aktivitäten werden automatisch markiert und werden in der **Toolbox** beim Klicken auf **OK** auf das Dialogfeld. Diese Elemente auch angezeigt, der **Toolbox** in einer neuen Kategorie, die dem Namespace entspricht, in dem die Aktivität/Element/Vorlage befindet.  
  
> [!WARNING]
>  Wenn Sie versuchen, eine Assembly hinzuzufügen, die keine Workflowaktivitäten enthält, wird ein Dialogfeld mit einer Fehlermeldung angezeigt, die besagt, dass die Assembly keine Aktivitäten enthält.  
  
 Dieses Dialogfeld ist Projekt bezogen und somit die **System.Activities** Registerkarte weiterhin in eigenständigen XAML- oder einem Projekttyp für außerhalb des Workflows angezeigt.  
  
 Die Filterung wird auf jeder Registerkarte ausgeführt. Dies bedeutet, es ist nicht möglich, Workflow-Aktivitäten durch Hinzufügen der **.NET Komponente** Registerkarte. Sie müssen über hinzugefügt werden die **System.Activities** Registerkarte selbst.  
  
 Deaktivieren Sie alle Elemente, die Sie nicht in anzeigen möchten die **Toolbox** in diesem Dialogfeld Tab oder alternativ Sie können dazu die **löschen** Kontextmenüoption "in der **Toolbox** und Verweises auf die Assembly wird nicht entfernt das Element aus der **Toolbox**.  
  
 Durch Ziehen und Ablegen im Designer wird die Aktivität instanziiert und die Assembly, die das Element enthält, automatisch der Liste von Assemblys hinzugefügt, auf die verwiesen wird. Außerdem gilt, wenn die Aktivität auf eine Assembly C verweist, wird C nicht der Liste von Assemblys, auf die verwiesen wird, hinzugefügt. Assembly C muss im globalen Assemblycache oder im gleichen Verzeichnis wie Aktivität b sein Im Fall eigenständige muss die Assembly im GAC oder den überprüfungspfaden von VS vorhanden sein. Nur dann können Sie die Aktivität auf die Workflow-Designer-Oberfläche ziehen und dort ablegen.  
  
 **Toolbox** -Einstellungen werden standardmäßig als Benutzeroptionen gespeichert daher beim nächsten Öffnen, wenn die **Toolbox**, die benutzerdefinierte Liste von Workflowaktivitäten angezeigt. Ein Nebeneffekt hiervon ist, wenn Sie bestimmte Elemente Ihrer Domäne, hinzugefügt haben die **Toolbox** über die **Toolboxelemente auswählen** (Dialogfeld), dann weiterhin auf diese Elemente finden bei der Arbeit einem Konsolenanwendung für Workflows auch. Wenn Sie nicht, um sie anzuzeigen möchten, klicken Sie dann mithilfe des Kontextmenüs löschen oder deaktivieren Sie diese über die **Toolboxelemente** (Dialogfeld), wie zuvor angemerkt.  
  
 Die Spalten in diesem Dialogfeld enthalten die folgenden Informationen:  
  
 Name  
 Führt die Namen der Workflowaktivitäten auf, die aktuell auf dem lokalen Computer registriert sind.  
  
 Namespace  
 Zeigt die Hierarchie der Namespaces der .NET Framework-Klassenbibliothek an, welche die Struktur der Aktivität definiert.  
  
 Assemblyname  
 Zeigt den Namen und die Version der .NET Framework-Assembly an, die die Aktivität enthält.  
  
 Verzeichnis  
 Zeigt den Speicherort der .NET Framework-Assembly an, die die Workflowaktivitäten enthält. Der Standardspeicherort für alle Assemblys ist der globale Assemblycache.  
  
 Klicken Sie zum Sortieren der aufgeführten Komponenten auf eine beliebige Spaltenüberschrift.