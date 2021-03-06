---
title: Server (Visual Studio SDK) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 404048e37f0a95ac1425250cfdcd098c4eb7f59d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servers-visual-studio-sdk"></a>Server (Visual Studio SDK)
Im Hinblick auf die Architektur des Debuggers einen **Server**:  
  
-   Ist ein Container für Ports und Port Lieferanten und wird verwendet, um mit der Sitzungs-Manager (SDM) Ports und Port Lieferanten kommunizieren und Debuggen von Modulen.  
  
-   Können Sie anhand des Namens identifiziert und die Ports und Port Lieferanten auflisten.  
  
-   Dargestellt durch eine [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) -Schnittstelle, die nur von Visual Studio (eine Instanz eines Servers für jede Instanz von Visual Studio ausgeführt wird) implementiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Ports](../../extensibility/debugger/ports.md)   
 [Port-Lieferanten](../../extensibility/debugger/port-suppliers.md)   
 [Debugger-Konzepte](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)