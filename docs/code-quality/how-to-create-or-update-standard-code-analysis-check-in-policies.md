---
title: 'Vorgehensweise: Erstellen oder Aktualisieren von Standardeincheckrichtlinien Analyse in der Eincheckrichtlinien | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.policyeditor
helpviewer_keywords:
- code analysis, migrating check-in policy
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d0fba16ee285faeafdc37fc38e6b5bb0a0725a46
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>Gewusst wie: Erstellen oder Aktualisieren von Standardeincheckrichtlinien für die Codeanalyse

Sie können anfordern, dass die Codeanalyse für alle Codeprojekte in einem Teamprojekt mit der Eincheckrichtlinie für die Analyse ausgeführt werden. Codeanalyse erfordern, kann die Qualität des Codes verbessern, die in die CodeBase eingecheckten.

> [!NOTE]
> Diese Funktion ist nur verfügbar, wenn Sie Team Foundation Server verwenden.

Eincheckrichtlinien für die Analyse in den teamprojekteinstellungen festgelegt werden und gelten für jedes Codeprojekt im Teamprojekt. Codeanalysen werden für Codeprojekte in der Projektdatei (XXPROJ) für das Codeprojekt konfiguriert. Codeanalysen werden auf dem lokalen Computer ausgeführt. Wenn Sie aktivieren die Eincheckrichtlinie für die Analyse, Dateien in einem Projekt mit Code, die eingecheckt werden werden, nachdem die letzte Bearbeitung kompiliert müssen und eine Codeanalyse ausgeführt werden, mindestens enthält müssen die Regeln in den teamprojekteinstellungen auf dem Computer ausgeführt werden, in c Es wurden ändert.

- Für verwalteten Code, Sie der Eincheckrichtlinie festgelegt, indem eine *Regelsatz* , die eine Teilmenge der Codeanalyseregeln enthält.

- Für C/C++-Code erfordert die Eincheckrichtlinie an, dass alle Codeanalyseregeln ausgeführt werden. Sie können die Präprozessordirektiven deaktivieren bestimmte Regeln für die einzelnen Codeprojekte in Ihrem Teamprojekt hinzufügen.

Nachdem Sie eine Eincheckrichtlinie für verwalteten Code angeben, können Teammitglieder ihre codeanalyseeinstellungen für Codeprojekte an den Richtlinieneinstellungen des Team-Projekt synchronisieren.

### <a name="to-open-the-check-in-policy-editor"></a>Öffnen des Editors-Eincheckrichtlinie

1. In Team Explorer mit der Maustaste den Namen des Teamprojekts, zeigen Sie auf **Teamprojekteinstellungen**, und klicken Sie dann auf **Quellcodeverwaltung**.

1. In der **Quellcodeverwaltung** wählen Sie im Dialogfeld die **Eincheckrichtlinie** Registerkarte.

1. Führen Sie einen der folgenden Schritte aus:

    - Klicken Sie auf **hinzufügen** um eine neue Richtlinie zu erstellen.

    - Doppelklicken Sie auf den vorhandenen **Codeanalyse** Element in der **Richtlinientyp** Liste, um die Richtlinie zu ändern.

### <a name="to-set-policy-options"></a>Richtlinienoptionen festlegen

Aktivieren Sie oder deaktivieren Sie die folgenden Optionen:

    |Option|Beschreibung|  
    |------------|-----------------|  
    |**Erzwingen Sie Check-in, um nur die Dateien enthalten, die Teil der aktuellen Projektmappe sind.**|Codeanalyse kann nur auf Dateien in Projektmappen- und Projektdateien Konfigurationsdateien angegebene ausgeführt. Diese Richtlinie stellt sicher, dass der gesamte Code, der Teil einer Projektmappe ist analysiert wird.|  
    |**C/C++-Codeanalyse erzwingen (/ analyze)**|Erfordert, dass alle C- oder C++-Projekte erstellt werden, mit der / analyze (Compileroption), um die Codeanalyse ausgeführt werden, bevor sie eingecheckt werden können.|  
    |**Codeanalyse für verwalteten Code erzwingen**|Erfordert, dass alle verwalteten Projekte Codeanalyse ausführen und erstellen, bevor sie eingecheckt werden können.|

### <a name="to-specify-a-managed-rule-set"></a>Um einen verwalteten Regelsatz anzugeben.

- Aus der **diesen Regelsatz ausführen** aufzulisten, verwenden Sie eine der folgenden Methoden:

    - Wählen Sie einen Microsoft-standard-Regelsatz.

    - Klicken Sie zum Auswählen eines benutzerdefinierten Regelsatzes auf  **\<Regelsatz auswählen aus der Quellcodeverwaltung... >**, und geben Sie dann auf den Versionskontrollpfad des Regelsatzes im Browser Steuerelement Quelle. Die Syntax von einem Pfad in der Versionskontrolle lautet:

    - **$/** `TeamProjectName` **/** `VersionControlPath`

    - Weitere Informationen zum Erstellen und Implementieren einer benutzerdefinierten Eincheckrichtlinie-Regel festgelegt ist, finden Sie unter [Implementieren von benutzerdefinierten Eincheckrichtlinien für verwalteten Code](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md).

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Eincheckrichtlinien für die Codeanalyse](../code-quality/creating-and-using-code-analysis-check-in-policies.md)