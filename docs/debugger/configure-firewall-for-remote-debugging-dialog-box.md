---
title: "Konfigurieren der Firewall für Remotedebuggen Dialogfeld | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.firewallconfiguration
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Configure Firewall for Remote Debugging dialog box
- remote debugging, configuring firewalls
- firewalls, configuring for remote debugging
ms.assetid: 5dff3393-fdeb-4129-a2f6-31f653107a82
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d945926a08a59fb37e5467591957ee3dcf661b9b
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2018
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>Firewall für Remotedebuggen konfigurieren (Dialogfeld)
Dieses Dialogfeld wird angezeigt, wenn von der Windows-Firewall Daten blockiert werden, die der Debugger über das Netzwerk empfangen soll. Um das Remotedebuggen fortzusetzen, müssen Sie der Firewall Ausnahmen hinzufügen und Ports öffnen, damit der Debugger Informationen empfangen kann.  
  
> [!CAUTION]
>  Wenn Sie Ports in der Firewall öffnen, ist der Computer unter Umständen Sicherheitsrisiken ausgesetzt, die sonst von der Firewall blockiert werden. Durch das Öffnen einer Lücke für das Remotedebuggen wird die Blockierung der Ports 4020 und 4021 in Visual Studio 2015 aufgehoben. In anderen Versionen von Visual Studio werden andere Portnummern verwendet. Weitere Informationen finden Sie unter [-Remotedebugger – Portzuweisungen](../debugger/remote-debugger-port-assignments.md). Zusätzlich wird dem Debugger ermöglicht, weitere Ports zu öffnen. Weitere Informationen finden Sie unter [der Windows-Firewall für Remotedebuggen konfigurieren](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Remotedebugging Abbrechen**  
 Mit dieser Option wird der Remotedebugversuch abgebrochen. Die Sicherheitseinstellungen des Computers bleiben bestehen.  
  
 **Blockierung für aufheben Sie Remotedebugging von Computern im lokalen Netzwerk (Subnetz)**  
 Mit dieser Option wird das Remotedebuggen der Computer im lokalen Subnetz aktiviert. Dadurch können Sicherheitslücken in den Computern des Subnetzes entstehen, die Firewall wird jedoch weiterhin Informationen von außerhalb des Subnetzes blockieren.  
  
 **Blockierung für aufheben Sie Remotedebugging von einem beliebigen computer**  
 Mit dieser Option wird das Remotedebuggen von jedem möglichen Computer aus dem Netzwerk aktiviert. Diese Einstellung ist am unsichersten.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggersicherheit](../debugger/debugger-security.md)   
 [Remotedebuggen](../debugger/remote-debugging.md)  
 [Referenz zur Debugger-Benutzeroberfläche](../debugger/debugging-user-interface-reference.md)