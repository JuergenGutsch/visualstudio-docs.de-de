---
title: 'Ansicht der Aufrufer/Aufgerufenen: Konfliktdaten | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Caller/Callee view
ms.assetid: a18a1b1b-9b39-43c7-b1f3-708fd20376f6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 47e4f57ffac71d6fb4f1c3e8cd8176c80d9f002a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="caller--callee-view----contention-data"></a>Ansicht der Aufrufer/Aufgerufenen – Konfliktdaten
In der Ansicht der Aufrufer/Aufgerufenen werden Konfliktinformationen für eine ausgewählte Funktion und deren übergeordnete und untergeordnete Funktionen angezeigt. Die Aufrufer-/Aufgerufener-Ansicht enthält drei Raster.  
  
 **Aktuelle Funktion** wird im mittleren Raster angezeigt, und zeigt Konfliktinformationen für die ausgewählte Funktion an. Die Werte umfassen alle blockierenden Konflikte der Funktion.  
  
 **Funktionen, die die aktuelle Funktion aufgerufen haben** wird im obersten Raster angezeigt und gibt die einzelnen Beiträge der (übergeordneten) Aufruferfunktion zu den Werten der ausgewählten (aktuellen) Funktion an.  
  
 **Funktionen, die von der aktuellen Funktion aufgerufen wurden** wird im unteren Raster angezeigt, und gibt Konfliktinformationen für die aufgerufene Funktion (untergeordnete Funktion) der ausgewählten Funktion an, als die untergeordnete Funktion von der aktuellen Funktion aufgerufen wurde.  
  
|Spalte|description|  
|------------|-----------------|  
|**Type**|Der Kontext der Funktion:<br /><br /> -   **0** – die aktuelle Funktion<br />-   **1** – eine Funktion, die die aktuelle Funktion aufruft<br />-   **2** – eine Funktionen, die von der aktuellen Funktion aufgerufen wird<br /><br /> Nur in [VSPerfReport](../profiling/vsperfreport.md)-Befehlszeilenberichten.|  
|**Exklusive blockierte Zeit %**|– Bei einer aktuellen Funktion die Zeit, für die die Funktion vom Ausführen von Code im Funktionsrumpf abgehalten wurde. Dies umfasst nicht die blockierte Zeit für Funktionen, die von dieser Funktion aufgerufen wurden.<br />– Bei einer aufrufenden Funktion der Anteil der exklusiven blockierten Zeit der aktuellen Funktion, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />– Bei einer aufgerufenen Funktion die Zeit, während der diese Funktion ihren eigenen Code nicht ausführen konnte, als diese Funktion von der aktuellen Funktion aufgerufen wurde. Dies umfasst nicht die blockierte Zeit für untergeordnete Funktionen, die von dieser aufgerufenen Funktion aufgerufen wurden.|  
|**Exklusive blockierte Zeit %**|Der Anteil der gesamten blockierten Zeit bei der Profilerstellung, die der exklusiven blockierten Zeit für diese Funktion in diesem Kontext entspricht.|  
|**Exklusive Konflikte**|– Bei einer aktuellen Funktion die Anzahl der Blockierungen der Ausführung von Code im Funktionsrumpf durch diese Funktion. Dies umfasst nicht die Konflikte, die in Funktionen aufgetreten sind, die von dieser Funktion aufgerufen wurden.<br />– Bei einer aufrufenden Funktion die Anzahl von exklusiven Konflikten der aktuellen Funktion, die aufgetreten sind, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />– Bei einer aufgerufenen Funktion die Anzahl der Blockierungen der Ausführung des Codes dieser Funktion, als diese Funktion von der aktuellen Funktion aufgerufen wurde. Dies umfasst nicht die Konflikte, die in Funktionen auftraten, die von der aufgerufenen Funktion aufgerufen wurden.|  
|**Exklusive Konflikte %**|Der Anteil aller Konflikte bei der Profilerstellung, die als exklusive Ausnahmen dieser Funktion in diesem Kontext aufgetreten sind.|  
|**Funktionsadresse**|Die Funktionsadresse oder das Token.|  
|**Funktionsname**|Der vollqualifizierte Name der Funktion.|  
|**Inklusive blockierte Zeit**|– Bei einer aktuellen Funktion die Zeit, als diese Funktion oder eine von ihr aufgerufene andere Funktion nicht ausgeführt werden konnte. Dies umfasst die blockierte Zeit für Funktionen, die von der aktuellen Funktion aufgerufen wurden.<br />– Für eine aufrufende Funktion der Anteil der inklusiven blockierten Zeit für die aktuelle Funktion, die aufgetreten ist, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />– Bei einer aufgerufenen Funktion die Zeit, als diese Funktion oder eine der Funktionen, die von dieser Funktion aufgerufen wurden, nicht ausgeführt werden konnte, als diese Funktion von der aktuellen Funktion aufgerufen wurde. Diese umfasst die blockierte Zeit für Funktionen, die von dieser aufgerufenen Funktion aufgerufen wurden.|  
|**Inklusive blockierte Zeit %**|Der Anteil der gesamten blockierten Zeit bei der Profilerstellung, die der inklusiven blockierten Zeit für diese Funktion in diesem Kontext entspricht.|  
|**Inklusive Konflikte %**|– Bei einer aktuellen Funktion die Anzahl wie oft diese Funktion oder eine der von ihr aufgerufenen Funktionen nicht ausgeführt werden konnten. Umfasst die Konflikte in Funktionen, die von dieser Funktion aufgerufen wurden.<br />– Bei einer aufrufenden Funktion die Anzahl von vollständigen Konflikten der aktuellen Funktion, die aufgetreten sind, als diese Funktion die aktuelle Funktion aufgerufen hat.<br />– Bei einer aufgerufenen Funktion die Anzahl wie oft diese Funktion oder eine der Funktionen, die von dieser Funktion aufgerufen wurden, nicht ausgeführt werden konnten, als diese Funktion von der aktuellen Funktion aufgerufen wurde. Konflikte, die in Funktionen auftraten, die von der aufgerufenen Funktion aufgerufen wurden, werden einbezogen.|  
|**Inklusive Konflikte %**|Der Anteil aller Konflikte bei der Profilerstellung, die als exklusive Ausnahmen dieser Funktion in diesem Kontext aufgetreten sind.|  
|**Funktionszeilennummer**|Die Zeilennummer des Anfangs dieser Funktion in der Quelldatei.|  
|**Modulname**|Der Name des Moduls, das die Funktion enthält.|  
|**Modulpfad**|Der Pfad des Moduls, das die Funktion enthält.|  
|**Prozess-ID**|Die Prozess-ID (PID) des Prozesses, in dem die Konflikte aufgetreten sind.|  
|**Prozessname**|Der Prozessname.|  
|**Name der Stammfunktion**|Der Name der aktuellen Funktion. Nur in [VSPerfReport](../profiling/vsperfreport.md)-Befehlszeilenberichten.|  
|**Quelldatei**|Die Quelldatei, die die Definition der Funktion enthält.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Anpassen von Spalten in Berichtsansichten](../profiling/how-to-customize-report-view-columns.md)   
 [Ansicht der aufrufenden/aufgerufenen Funktionen](../profiling/caller-callee-view.md)   
 [Aufrufer-/Aufgerufener-Ansicht – Profiler-Samplingdaten](../profiling/caller-callee-view-sampling-data.md)   
 [Aufrufer-/Aufgerufener-Ansicht – .NET-Speicherinstrumentationsdaten im Profiler](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [Aufrufer-/Aufgerufener-Ansicht – .NET-Speichersamplingdaten im Profiler](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [Aufrufer-/Aufgerufener-Ansicht – Profiler-Instrumentationsdaten](../profiling/caller-callee-view-instrumentation-data.md)