---
title: Verschiedenes, XML, Text-Editor, Dialogfeld "Optionen" | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4773bf87e89bd504b477d9a1a31dfe961a3f29ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>Verschiedenes, XML, Texteditor, Dialogfeld "Optionen"
In diesem Dialogfeld können Sie die Einstellungen für die automatische Vervollständigung und die Schemaeinstellungen für den XML-Editor ändern. Sie erreichen die **Optionen** (Dialogfeld), aus der **Tools** Menü.  
  
> [!NOTE]
>  Diese Einstellungen sind verfügbar, wenn Sie auswählen der **Text-Editor** Ordner, der **XML** Ordner, und klicken Sie dann die **Sonstiges** option die **Optionen** (Dialogfeld).  
  
## <a name="auto-insert"></a>Automatisch einfügen  
 **Tags schließen**  
 Wenn die automatische Vervollständigung aktiviert ist, fügt der Editor automatisch ein Endtag hinzu, wenn Sie zum Schließen eines Starttags eine spitze Klammer rechts (>) eingeben (sofern das Tag nicht bereits geschlossen ist). Dies ist das Standardverhalten.  
  
 Die Vervollständigung eines leeren Elements hängt nicht von der Einstellung für die automatische Vervollständigung ab. Sie können ein leeres Element immer automatisch vervollständigen, indem Sie einen umgekehrten Schrägstrich (/) eingeben.  
  
 **Attributanführungszeichen**  
 Beim Erstellen von XML-Attributen fügt der Editor die `=" "`-Zeichen ein und platziert das Caretzeichen (^) innerhalb der doppelten Anführungszeichen.  
  
 Standardmäßig ausgewählt.  
  
 **Namespacedeklarationen**  
 Vom Editor werden im Bedarfsfall automatisch Namespacedeklarationen eingefügt.  
  
 Standardmäßig ausgewählt.  
  
 **Sonstige Markups (Kommentare, CDATA)**  
 Kommentare, CDATA-, DOCTYPE-, Verarbeitungsanweisungen und sonstige Markupdeklarationen werden automatisch vervollständigt.  
  
 Standardmäßig ausgewählt.  
  
## <a name="network"></a>Netzwerk  
 **DTDs und Schemata automatisch herunterzuladen**  
 Schemata und DTDs (Document Type Definitions) werden von HTTP-Speicherorten automatisch heruntergeladen. Dieses Feature verwendet System.Net, wobei die automatische Erkennung des Proxyservers aktiviert ist.  
  
 Standardmäßig ausgewählt.  
  
## <a name="outlining"></a>Gliedern  
 **Beim Öffnen von Dateien in Gliederungsmodus wechseln**  
 Aktiviert beim Öffnen einer Datei die Gliederungsfunktion.  
  
 Standardmäßig ausgewählt.  
  
## <a name="caching"></a>Zwischenspeicherung  
 **Schemas**  
 Gibt den Speicherort des Schemacaches an. Die Schaltfläche zum Durchsuchen (**...** ) Öffnet die **Verzeichnis durchsuchen** Dialogfeld am Speicherort aktuellen Schemacaches. Sie können ein anderes Verzeichnis auswählen, oder wählen Sie einen Ordner, klicken Sie im Dialogfeld mit der rechten Maustaste, und wählen Sie **öffnen** zu sehen, was in das Verzeichnis ist.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumenteigenschaften, Eigenschaftenfenster](../xml-tools/xml-document-properties-properties-window.md)   
 [Komponenten des XML-Editors](../xml-tools/xml-editor-components.md)