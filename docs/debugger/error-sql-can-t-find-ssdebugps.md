---
title: "Fehler: SQL können &#39; t Find SSDEBUGPS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0e45c70d8186a178bafe6544bf83dcec1ed35d9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Fehler: SQL können &#39; t Find SSDEBUGPS
SSDEBUGPS.dll ist die Hostkomponente von SQL Server-Debuggen.  
  
 Dieser Fehler tritt beim Versuch auf, das Debuggen zu starten, und zeigt an, dass die angegebene Datei nicht auf dem [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)]-Computer ist. Mögliche Ursachen sind: Entweder wurde Remotedebuggen-Setup nie ausgeführt, oder diese Datei wurde gelöscht.  
  
 Es gibt zwei Möglichkeiten zum Beheben dieses Fehlers: indem Sie Remotedebuggen-Setup erneut ausführen und kopieren die Datei auf die [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] Computer.  
  
 Zum Remotedebuggen-Setup erneut ausführen, befolgen Sie die Anweisungen unter [Remotedebuggen](../debugger/remote-debugging.md).  
  
 Wenn Sie eine Kopie von ssdebugps.dll finden können, können Sie kopieren sie auf der [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] Computer. Wenn die Datei vorhanden ist, finden Sie sie im Verzeichnis \Programme\Gemeinsame Dateien\Microsoft Shared\SQL-Debuggen. Sie finden es vielleicht auf einem anderen [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] Computer oder auf einem Computer mit [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)] installiert.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>So kopieren Sie SSDEBUGPS.dll auf den SQL Server 2005-Computer  
  
1.  Kopieren Sie die Datei in das Verzeichnis mit dem gleichen Namen und Pfad auf dem [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] Computer.  
  
2.  Registrieren Sie ihn durch Öffnen einer **Eingabeaufforderung**, und den folgenden Befehl ausführen:  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```