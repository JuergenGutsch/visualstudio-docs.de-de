---
title: "Gewusst wie: Instrumentieren einer dynamisch kompilierten ASP.NET-Webanwendung und Sammeln von Speicherdaten &#252;ber die Profiler-Befehlszeile | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2cdd9903-39db-47e8-93dd-5e6a21bc3435
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Gewusst wie: Instrumentieren einer dynamisch kompilierten ASP.NET-Webanwendung und Sammeln von Speicherdaten &#252;ber die Profiler-Befehlszeile
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie mit den Befehlszeilentools der [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]\-Profilerstellungstools und der Instrumentationsmethode ausführliche Daten zur .NET\-Speicherbelegung und zur Objektlebensdauer einer dynamisch kompilierten [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Webanwendung gesammelt werden.  
  
> [!NOTE]
>  Die Befehlszeilentools der Profilerstellungstools befinden sich im Unterverzeichnis "\\Team Tools\\Performance Tools" des [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]\-Installationsverzeichnisses.  Auf 64\-Bit\-Computern sind 64\-Bit\- und 32\-Bit\-Versionen der Tools verfügbar.  Um die Profiler\-Befehlszeilentools zu verwenden, müssen Sie den Toolpfad der PATH\-Umgebungsvariable des Eingabeaufforderungsfensters oder dem Befehl selbst hinzufügen.  Weitere Informationen finden Sie unter [Angeben des Pfads zu Tools für die Befehlszeile](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Um Leistungsdaten von einer [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Webanwendung zu erfassen, ändern Sie die Datei "web.config" der Zielanwendung, damit die dynamisch kompilierten Anwendungsdateien mithilfe des Tools [VSInstr.exe](../profiling/vsinstr.md) instrumentiert werden können.  Danach können Sie mit dem Tool [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) den Server konfigurieren, auf dem die [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Webanwendung gehostet wird, und die Profilerstellung für den .NET\-Arbeitsspeicher aktivieren, indem Sie die entsprechenden Umgebungsvariablen festlegen und den Computer neu starten.  
  
 Starten Sie den Profiler, und führen Sie dann die Zielanwendung aus, um Daten zu erfassen.  Während der Profiler an die Anwendung angefügt ist, können Sie die Erfassung anhalten und fortsetzen. Schließen Sie nach dem Erfassen der entsprechenden Daten die Anwendung, schließen Sie den Arbeitsprozess von Internetinformationsdienste \(IIS\), und schließen Sie dann den Profiler.  
  
 Stellen Sie nach dem Abschluss der Profilerstellung den ursprünglichen Status der Datei "web.config" und des Webservers wieder her.  
  
## Konfigurieren der ASP.NET\-Anwendung und des Webservers  
  
#### So konfigurieren Sie die ASP.NET\-Anwendung und den Webserver  
  
1.  Ändern Sie die Datei "web.config" der Zielanwendung.  Siehe [Gewusst wie: Bearbeiten von Web.Config\-Dateien zur Instrumentierung und Profilerstellung für dynamisch kompilierte ASP.NET\-Webanwendungen](../profiling/how-to-modify-web-config-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications.md).  
  
2.  Öffnen Sie eine Eingabeaufforderung auf dem Computer, auf dem die Webanwendung gehostet wird.  
  
3.  Initialisieren Sie die Umgebungsvariablen für die Profilerstellung.  Geben Sie Folgendes ein:  
  
     **VSPerfClrEnv \/globaltracegc**  
  
     \- oder \-  
  
     **VSPerfClrEnv \/globaltracegclife**  
  
    -   **\/globaltracegc** aktiviert die Sammlung von Daten zur Speicherbelegung.  
  
    -   **\/globaltracegclife** aktiviert die Sammlung von Daten zur Speicherbelegung und zur Objektlebensdauer.  
  
4.  Starten Sie den Computer neu.  
  
## Ausführen der Profilerstellungssitzung  
  
#### So erstellen Sie ein Profil für die ASP.NET\-Webanwendung  
  
1.  Starten Sie den Profiler.  Geben Sie Folgendes ein:  
  
     **VSPerfCmd** [\/start](../profiling/start.md)**:trace** [\/output](../profiling/output.md)**:**`OutputFile` \[`Options`\]  
  
    -   Mit der **\/start:trace**\-Option wird der Profiler initialisiert.  
  
    -   Die **\/output:**`OutputFile`\-Option ist bei **\/start** erforderlich.  Das `OutputFile`\-Objekt gibt den Namen und Speicherort der Profilerstellungs\-Datendatei \(.vsp\) an.  
  
     Sie können jede der folgenden Optionen zusammen mit der **\/start:trace**\-Option verwenden.  
  
    > [!NOTE]
    >  Die **\/user**\-Option und die **\/crosssession**\-Option sind normalerweise für ASP.NET\-Anwendungen erforderlich.  
  
    |Option|**Beschreibung**|  
    |------------|----------------------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|Gibt die optionale Domäne und den Benutzernamen des Kontos an, das den [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Arbeitsprozess besitzt.  Diese Option ist erforderlich, wenn der Prozess als ein Benutzer ausgeführt wird, der nicht der angemeldete Benutzer ist.  Der Name wird in der Spalte "Benutzername" auf der Registerkarte "Prozesse" des Windows Task\-Managers aufgeführt.|  
    |[\/crosssession](../profiling/crosssession.md)|Aktiviert die Profilerstellung für Prozesse in anderen Sitzungen.  Diese Option ist erforderlich, wenn die Anwendung in einer anderen Sitzung ausgeführt wird.  Die Sitzungs\-ID ist auf der Registerkarte "Prozesse" in der Spalte "Sitzungs\-ID" des Windows Task\-Managers aufgeführt.  **\/CS** kann als Abkürzung für **\/crosssession** angegeben werden.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|Startet den Profiler mit angehaltener Datensammlung.  Mit [\/globalon](../profiling/globalon-and-globaloff.md) setzen Sie die Profilerstellung fort.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Sammelt Informationen aus dem in `Config` angegebenen Prozessorleistungsindikator.  Informationen zu Leistungsindikatoren werden den Daten hinzugefügt, die bei jedem Profilerstellungsereignis gesammelt werden.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Gibt einen Windows\-Leistungsindikator an, dessen Daten während der Profilerstellung gesammelt werden sollen.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|Diese Option kann nur in Kombination mit **\/wincounter** verwendet werden.  Gibt die Anzahl von Millisekunden zwischen Ereignissen bei der Datensammlung mit Windows\-Leistungsindikatoren an.  Der Standardwert ist 500 ms.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|Gibt ein ETW\-Ereignis \(Ereignisablaufverfolgung für Windows\) an, dessen Daten während der Profilerstellung gesammelt werden sollen.  ETW\-Ereignisse werden in einer separaten Datei \(.etl\) gesammelt.|  
  
2.  Starten Sie die [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Webanwendung auf die gewohnte Weise.  
  
## Steuern der Datenauflistung  
 Während die Zielanwendung ausgeführt wird, können Sie die Datensammlung steuern, indem Sie das Schreiben von Daten in die Profiler\-Datendatei mit **VSPerfCmd.exe**\-Optionen starten und beenden.  Durch das Steuern der Datensammlung können Sie Daten zu einem bestimmten Teil der Programmausführung sammeln, z. B. zum Starten oder Schließen der Anwendung.  
  
#### So starten und beenden Sie die Datensammlung  
  
-   Mit den folgenden Optionspaaren wird die Datensammlung gestartet und beendet.  Geben Sie jede Option in einer eigenen Befehlszeile an.  Sie können die Datensammlung mehrmals aktivieren und deaktivieren.  
  
    |Option|**Beschreibung**|  
    |------------|----------------------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|Startet \(**\/globalon**\) oder beendet \(**\/globaloff**\) die Datensammlung für alle Prozesse.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|Startet \(**\/processon**\) oder beendet \(**\/processoff**\) die Datensammlung für den mit der Prozess\-ID \(`PID`\) angegebenen Prozess.|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [\/threadoff](../profiling/threadon-and-threadoff.md)**:**`TID`|Startet \(**\/threadon**\) oder beendet \(**\/threadoff**\) die Datensammlung für den mit der Thread\-ID \(`TID`\) angegebenen Thread.|  
  
-   Sie können auch die [\/mark](../profiling/mark.md)\-Option von **VSPerfCmd.exe** verwenden, um eine Profilmarkierung in die Datendatei einzufügen.  Der **\/mark**\-Befehl fügt einen Bezeichner, einen Zeitstempel und eine optionale benutzerdefinierte Textzeichenfolge hinzu.  Mit Markierungen können die Daten in Profilerberichten und Datenansichten gefiltert werden.  
  
## Beenden der Profilerstellungssitzung  
 Um eine Profilerstellungssitzung zu beenden, schließen Sie die [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Zielwebanwendung, beenden Internetinformationsdienste \(IIS\), um den profilierten Prozess zu beenden, und schließen dann den Profiler.  Starten Sie danach IIS neu.  
  
#### So beenden Sie eine Profilerstellungssitzung  
  
1.  Schließen Sie die [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Webanwendung.  
  
2.  Schließen Sie den [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Arbeitsprozess, indem Sie Internetinformationsdienste \(IIS\) zurücksetzen.  Geben Sie Folgendes ein:  
  
     **IISReset \/stop**  
  
3.  Schließen Sie den Profiler.  Geben Sie Folgendes ein:  
  
     **VSPerfCmd** [\/shutdown](../profiling/shutdown.md)  
  
4.  Starten Sie IIS neu.  Geben Sie Folgendes ein:  
  
     **IISReset \/start**  
  
## Wiederherstellen der Anwendung und der Computerkonfiguration  
 Wenn Sie alle Profilerstellungsvorgänge abgeschlossen haben, ersetzen Sie die Datei "web.config", löschen die Umgebungsvariablen für die Profilerstellung und starten den Computer neu, um den ursprünglichen Zustand des Servers und der [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]\-Anwendung wiederherzustellen.  
  
#### So stellen Sie die Anwendung und die Computerkonfiguration wieder her  
  
1.  Ersetzen Sie die Datei "web.config" durch eine Kopie der ursprünglichen Datei.  
  
2.  \(Optional\)  Löschen Sie die Umgebungsvariablen für die Profilerstellung.  Geben Sie Folgendes ein:  
  
     **VSPerfCmd \/globaloff**  
  
3.  Starten Sie den Computer neu.  
  
## Siehe auch  
 [Profilerstellung für ASP.NET\-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [.NET\-Arbeitsspeicherdatenansichten](../profiling/dotnet-memory-data-views.md)