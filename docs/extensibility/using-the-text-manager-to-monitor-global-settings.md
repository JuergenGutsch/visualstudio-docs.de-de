---
title: "Verwenden die Text-Manager zum Überwachen von globaler Einstellungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 00716142e7f91d01fbc81c5d25b378065cb44f92
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>Verwenden die Text-Manager zum Überwachen von globaler Einstellungen
Wenn Sie einen Editor Core implementieren, müssen Sie die Änderungen an globalen Einstellungen sind überwachen, da diese Änderungen auf Ihre Instanz des Editors auswirken können. Sie können die Änderungen durch Überwachen von Ereignissen, die ausgelöst wird, durch den TextManager nachverfolgen. Beispielsweise, wenn Sie eine globale Einstellung für die Darstellung oder Verhalten einer Komponente in die Core-Editor, z. B. seine dokumentdatenobjekt angeben Text-Manager speichert diese Informationen und wird für alle betroffenen Clients kommuniziert.  
  
## <a name="text-manager-functions"></a>Text-Manager-Funktionen  
 Der Text-Manager löst Ereignisse für eine Reihe von Einstellungen, einschließlich der folgenden:  
  
-   Gibt an, ob ein Puffer Quellcodeverwaltungssystem ist  
  
-   Gewusst wie: für Datei änderungsbenachrichtungen  
  
-   Gewusst wie: Nachverfolgen von welche Ansichten bestimmte Puffer zugeordnet sind.  
  
-   Voreinstellungen für die farbliche Kennzeichnung von Text  
  
-   Registerkarte im Vergleich zu Speicherplatz-Voreinstellungen  
  
 Voreinstellungen, die für eine bestimmte Sprache eindeutig sind, werden nicht vom TextManager verwaltet. Diese Einstellungen müssen von jeder Sprachdienst verwaltet werden.  
  
 Ereignisbenachrichtigung für den TextManager wird bereitgestellt, indem die <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> Schnittstelle. Implementieren Sie diese Schnittstelle auf Ihrem Client Objekt zum Behandeln von Ereignissen ausgelöst, die Text-Manager. Sie registrieren für diese Ereignisse mithilfe der <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> Schnittstelle für den TextManager.  
  
## <a name="see-also"></a>Siehe auch  
 [In der Core-Editor](../extensibility/inside-the-core-editor.md)   
 [Editor-Funktionen](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)