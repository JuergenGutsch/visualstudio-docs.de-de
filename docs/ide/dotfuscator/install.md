---
title: Installation von Dotfuscator Community Edition (CE) | Microsoft-Dokumentation
ms.date: 2017-06-22
ms.devlang: dotnet
ms.technology: vs-ide-general
ms.topic: article
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, protection, community edition, obfuscation, .NET, kostenlos, Visual Studio 2017, installieren
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator installer
- Dotfuscator setup
- install Dotfuscator
- installing Dotfuscator
- set up Dotfuscator
description: "Finden Sie heraus, wie Sie Dotfuscator Community Edition, der in Visual Studio 2017 beinhaltet ist, kostenlos herunterladen können."
ms.assetid: f2146651-e24a-4e24-ade8-8ddee8ff4e43
author: Joe-Sewell-PreEmptive
manager: ghogen
ms.openlocfilehash: 6e3151a7ce26fcc998df7fbce1cefda54249a384
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="install-dotfuscator-community-edition-ce"></a>Installation von Dotfuscator Community Edition (CE)

Visual Studio 2017 kann jetzt reibungsloser installiert werden.
Deshalb wird Dotfuscator Community Edition (Dotfuscator CE) standardmäßig nicht installiert.
Es ist jedoch einfach, Dotfuscator CE nachträglich zu installieren.

> [!NOTE]
> Zusätzlich zu Dotfuscator CE, das mit Versionen von Visual Studio ausgeliefert wird, veröffentlicht auch PreEmptive Solutions in regelmäßigen Abständen aktualisierte Versionen auf ihrer Website.
> Wenn Sie die **aktuellste Version** direkt herunterladen möchten, statt sie mit Visual Studio zu installieren, **[klicken Sie hier, um zur „Downloads“-Seite von Dotfuscator zu gelangen][download]**.

## <a name="within-visual-studio"></a>In Visual Studio

Sie können Dotfuscator CE von der Visual Studio-IDE installieren:

1. Geben Sie `dotfuscator` in die **Schnellstart**-Suchleiste (STRG+Q) ein. <br/> <br/> ![](media/install_from_vs_12.png) <br/> <br/>
2. Wählen Sie in den angezeigten Schnellstartergebnisse unter der Überschrift *Installieren* **PreEmptive Protection – Dotfuscator (Individual Component) (PreEmptive Protection – Dotfuscator (Einzelne Komponente))** aus.
  * Wenn stattdessen unter der Überschrift *Menüs* **Extras – PreEmptive Protection – Dotfuscator** angezeigt wird, ist Dotfuscator CE bereits installiert. Weitere Informationen zum Gebrauch finden Sie [auf der „Erste Schritte“-Seite des vollständigen Dotfuscator CE-Benutzerhandbuchs][get-started].
3. Ein Fenster für den Visual Studio-Installer wird geöffnet – schon so voreingestellt, dass Dotfuscator CE installiert wird.
  * Möglicherweise müssen Sie Administratoranmeldeinformationen eingeben, damit Sie fortfahren können.
4. Schließen Sie alle Instanzen der Visual Studio-IDE. <br/> <br/> ![](media/install_from_vs_345.png) <br/> <br/>
5. Klicken Sie im Visual Studio-Installer auf *Installieren*.

Sobald die Installation abgeschlossen ist, können Sie Dotfuscator CE verwenden. Weitere Informationen finden Sie [auf der „Erste Schritte“-Seite des vollständigen Dotfuscator CE-Benutzerhandbuchs][get-started].

## <a name="during-visual-studio-installation"></a>Während der Installation von Visual Studio

Wenn Sie Visual Studio 2017 noch nicht installiert haben, können Sie den Installer von [Visual Studio-Website][2017-install] herunterladen.
Wenn Sie diesen ausführen, zeigt er Installationsoptionen für die ausgewählte Visual Studio-Edition an.

![](media/install_ui.png)

Anschließend können Sie Dotfuscator CE als einzelne Komponente von Visual Studio 2017 installieren:

1. Wählen Sie die Registerkarte **Einzelne Komponenten** aus.
2. Setzen Sie unter *Codetools* ein Häkchen bei dem Element *PreEmptive Protection – Dotfuscator*.<br/> <br/> ![](media/install_individually_12.png) <br/> <br/>
3. Im Panel *Zusammenfassung* wird *PreEmptive Protection – Dotfuscator* im Bereich *Einzelne Komponenten* angezeigt. <br/> <br/> ![](media/install_individually_3.png) <br/> <br/>
4. Alle weiteren Installationseinstellungen können Sie Ihrer Umgebung entsprechend vornehmen.
5. Wenn alles für die Installation von Visual Studio vorbereitet ist, klicken Sie auf die Schaltfläche *Installieren*.

Sobald die Installation abgeschlossen ist, können Sie Dotfuscator CE verwenden. Weitere Informationen finden Sie [auf der „Erste Schritte“-Seite des vollständigen Dotfuscator CE-Benutzerhandbuchs][get-started].

## <a name="see-also"></a>Siehe auch

[Dieses Thema im vollständigen Dotfuscator CE-Benutzerhandbuch][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[2017-install]: https://www.visualstudio.com/downloads/#vs-2017
[get-started]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[download]: https://www.preemptive.com/products/dotfuscator/downloads

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_install.html
