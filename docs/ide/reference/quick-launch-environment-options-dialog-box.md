---
title: "Schnellstart, Umgebung, Dialogfeld „Optionen“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0f71cca51a27c8ed9d6467d99425d4d3b721d195
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="quick-launch-environment-options-dialog-box"></a>Schnellstart, Umgebung, Dialogfeld „Optionen“
Sie können **Schnellstart** verwenden, um Aktionen für IDE-Objekte wie Optionen, Vorlagen oder Menüs schnell zu suchen und auszuführen. Sie können **Schnellstart** nicht zur Suche nach Code und Symbolen verwenden. Das Suchfeld **Schnellstart** befindet sich rechts oben in der Menüleiste und kann mit der Tastenkombination STRG+Q aufgerufen werden. Geben Sie einfach die Suchzeichenfolge im Feld ein. Verwenden Sie "@@", um nach Zeichenfolgen zu suchen, die @ enthalten.  
  
 **Schnellstart** ist standardmäßig aktiviert, wenn Sie Visual Studio installieren. Auf der Menüleiste können Sie **Schnellstart** darstellen oder ausblenden, indem Sie **Extras** und **Optionen** auswählen. Erweitern Sie den Knoten **Umgebungen**, und wählen Sie dann **Schnellstart** aus. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Schnellstart aktivieren**. Sie können auf dieser Seite auch Suchkategorien aktivieren oder deaktivieren.  
  
## <a name="category-list"></a>Kategorieliste  
 Es gibt vier Kategorien von Schnellstart-Suchergebnissen: **Zuletzt verwendet**, **Menüs**, **Optionen** und **Geöffnete Dokumente**. Außerdem wird die Anzahl von Elementen pro Kategorie angezeigt. Um die Suchergebnisse nach Kategorie zu durchlaufen, drücken Sie die Tastenkombination STRG+Q. So werden alle Ergebnisse der nächsten Kategorie angezeigt. Nach Anzeigen der letzten Kategorie können Sie mit STRG+Q einige Ergebnisse aus jeder Kategorie aufrufen. Mit STRG+UMSCHALT+Q können Sie in umgekehrter Reihenfolge durch die Kategorien navigieren. Wählen Sie den Kategorienamen aus, um alle Suchergebnisse aus einer Kategorie anzuzeigen.  
  
 Sie können die folgenden Tastenkombinationen verwenden, um die Suche auf bestimmte Kategorien einzuschränken.  
  
|Kategorie|Verknüpfung|Verknüpfungsbeschreibung|  
|--------------|--------------|--------------------------|  
|Zuletzt verwendet|@mru<br /><br /> Beispiel: `@mru font`|Zeigt bis zu fünf Elemente der Liste **Zuletzt verwendet** an.|  
|Menüs|@menu<br /><br /> Beispiel: `@menu font`|Schränkt die Suche auf Menüelemente ein.|  
|Optionen|@opt<br /><br /> Beispiel: `@opt font`|Schränkt die Suche auf Einstellungen im Dialogfeld **Optionen** ein.|  
|Dokumente|@doc<br /><br /> Beispiel: `@doc font`|Schränkt die Suche auf Dateinamen und Pfade der geöffneten Dokumente ein, die den Suchkriterien entsprechen. Der Text in den Dateien selbst wird nicht durchsucht.|  
  
> [!NOTE]
>  Die Tastenkombinationen können auf der Seite **Tastatur** im Dialogfeld **Optionen** unter **Allgemein** geändert werden.  
  
## <a name="show-previous-results"></a>Vorherige Ergebnisse anzeigen  
 Standardmäßig wird der eingegebene Suchbegriff nicht zwischen Suchsitzungen beibehalten. Die Suchzeichenfolge wird gelöscht, wenn Sie nach einem Begriff suchen. Bewegen Sie den Cursor außerhalb des Bereichs **Schnellstart** und dann wieder zurück. Um die Suchergebnisse beizubehalten, wechseln Sie in das Dialogfeld **Optionen**, wählen Sie **Schnellstart** aus, und aktivieren Sie dann das Kontrollkästchen **Suchergebnisse aus vorherigen Suchen anzeigen, wenn Schnellstart aktiviert ist** . Wenn Sie das nächste Mal eine Suche ausführen, verlassen Sie den Schnellstartbereich, und kehren Sie dahin zurück. Der Schnellstart behält den zuletzt verwendeten Suchbegriff bei und zeigt auch die Suchergebnisse an.  
  
 Die neuesten Tipps und Tricks für die Verwendung von **Schnellstart** finden Sie im [Visual Studio-Blog](http://go.microsoft.com/fwlink/?LinkId=236054).  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Elemente der Benutzeroberfläche (Visual Studio)](../../ide/reference/general-user-interface-elements-visual-studio.md)   
 [Dialogfeld „Umgebungsoptionen“](../../ide/reference/environment-options-dialog-box.md)