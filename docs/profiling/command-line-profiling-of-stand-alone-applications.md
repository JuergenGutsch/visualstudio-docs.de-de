---
title: "Profilerstellung für eigenständige Anwendungen über die Befehlszeile | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dd2b50ae03263cd072143481a91679663f126c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>Profilerstellung für eigenständige Anwendungen über die Befehlszeile
In diesem Abschnitt werden die Prozeduren und die Optionen zum Erfassen von Leistungsdaten für eigenständige (Client-)Anwendungen unter Verwendung der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]-Profilerstellungstools über die Befehlszeile beschrieben.  
  
## <a name="common-tasks"></a>Allgemeine Aufgaben  
  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Sammeln von Anwendungsstatistikdaten:** Sammeln Sie Leistungsstatistikdaten mit der Samplingmethode. Datensampling ist beim Analysieren von CPU-Auslastungsproblemen und zum Verständnis der allgemeinen Leistungsmerkmale einer Anwendung hilfreich.|-   [Sammeln von Anwendungsstatistiken durch Sampling](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Sammeln ausführlicher Zeitsteuerungsdaten:** Sammeln Sie ausführliche Zeitsteuerungsinformationen mit der Instrumentationsmethode. Instrumentationsdaten sind beim Analysieren von E/A-Problemen und für die detaillierte Analyse von Anwendungsszenarios hilfreich.|-   [Sammeln ausführlicher Zeitsteuerungsdaten mithilfe der Instrumentation](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**Sammeln von .NET-Arbeitsspeicherdaten:** Sammeln Sie mit Sampling oder Instrumentation Daten zur .NET-Speicherbelegung, die Auskunft über die Größe und Anzahl zugeordneter Objekte geben. Sie können auch Objektlebensdauerdaten sammeln, die die Größe und Anzahl von Objekten angeben, die in jeder Garbage Collection-Generation freigegeben werden.|-   [Sammeln von .NET Framework-Arbeitsspeicherdaten](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Sammeln von Parallelitätsdaten:** Sammeln Sie mit der Parallelitätsmethode Ressourcenkonfliktdaten und Threadaktivitätsdaten, die Auskunft über CPU-Auslastung, Threadkonflikte, Threadmigration, Synchronisierungsverzögerungen, überlappende E/A-Bereiche und andere Systemereignisse geben.|-   [Sammeln von Parallelitätsdaten](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**Hinzufügen von Ebeneninteraktionsdaten:** Sie können Leistungsdaten zu synchronen ADO.NET-Aufrufen der Anwendung hinzufügen, die an eine Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]-Datenbank erfolgt sind. Das Hinzufügen von Ebeneninteraktionsdaten zu einer Profilerstellung erfordert bestimmte Verfahren der Befehlszeilenprofilerstellungstools.|-   [Hinzufügen von Ebeneninteraktionsdaten über die Befehlszeile](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**Probieren Sie es aus:** Verwenden Sie schrittweise Prozeduren bei der Profilerstellung für eine Beispielclientanwendung durch die Verwendung der Sampling- oder Instrumentationsmethode.|-   [Exemplarische Vorgehensweise: Profilerstellung über die Befehlszeile mit Sampling](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [Exemplarische Vorgehensweise: Profilerstellung über die Befehlszeile mit Instrumentation](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>Verwandte Aufgaben  
  
|Aufgabe|Verwandter Inhalt|  
|----------|---------------------|  
|**Profilerstellung für ASP.NET-Anwendungen**|-   [Profiling ASP.NET Web Applications (Profilerstellung für ASP.NET-Webanwendungen)](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**Profilerstellung für Dienste**|-   [Profilerstellungsdienste](../profiling/command-line-profiling-of-services.md)|