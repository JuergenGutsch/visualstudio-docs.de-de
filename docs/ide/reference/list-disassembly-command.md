---
title: "Befehl „Disassembly auflisten“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c6a704ac783f4efc300de26c2a5e987f82fc2e9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="list-disassembly-command"></a>Befehl "Disassemblierung auflisten"
Startet den Debugprozess und ermöglicht es, die Behebung von Fehlern festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## <a name="switches"></a>Schalter  
 Jeder Schalter kann sowohl mit der vollständigen als auch mit der Kurzform aufgerufen werden.  
  
 /count: `number` [oder] /c: `number` [oder] /length: `number` [oder] /l: `number`  
 Dies ist optional. Anzahl der anzuzeigenden Anweisungen. Der Standardwert ist 8.  
  
 /endaddress: `expression` [oder] /e: `expression`  
 Dies ist optional. Adresse, an der die Disassemblierung beendet wird.  
  
 /codebytes:`yes`|`no` [oder] /bytes:`yes`|`no` [oder] /b:`yes`|`no`  
 Dies ist optional. Gibt an, ob Codebytes angezeigt werden sollen. Der Standardwert ist `no`sein.  
  
 /source:`yes`|`no` [oder] /s:`yes`|`no`  
 Dies ist optional. Gibt an, ob Quellcode angezeigt werden soll. Der Standardwert ist `no`sein.  
  
 /symbolnames:`yes`|`no` [oder] /names:`yes`|`no` [oder] /n:`yes`|`no`  
 Dies ist optional. Gibt an, ob Symbolnamen angezeigt werden sollen. Der Standardwert ist `yes`sein.  
  
 [/linenumbers:`yes`|`no`]  
 Dies ist optional. Ermöglicht das Anzeigen von dem Quellcode zugeordneten Zeilennummern. Der Schalter „/source“ muss den Wert `yes` haben, um den Schalter „/linenumbers“ zu verwenden.  
  
## <a name="example"></a>Beispiel  
  
```  
>Debug.ListDisassembly  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Befehl „Aufrufliste auflisten“](../../ide/reference/list-call-stack-command.md)   
 [Befehl „Threads auflisten“](../../ide/reference/list-threads-command.md)   
 [Visual Studio-Befehle](../../ide/reference/visual-studio-commands.md)   
 [Befehlsfenster](../../ide/reference/command-window.md)   
 [Such-/Befehlsfeld](../../ide/find-command-box.md)   
 [Visual Studio-Befehlsaliase](../../ide/reference/visual-studio-command-aliases.md)