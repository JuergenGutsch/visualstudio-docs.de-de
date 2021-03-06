---
title: Visual Studio-Debugger-Erweiterbarkeits | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
caps.latest.revision: "32"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c5b5943dc8087a22e1bdfb94ae6d0d10335c174a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-debugger-extensibility"></a>Visual Studio-Debugger-Erweiterbarkeit
Visual Studio enthält einen vollständig interaktiven Quelle Code-Debugger bietet eine leistungsfähige und einfach zu verwendende Tool zum Nachverfolgen von Fehlern im Programm. Der Debugger hat vollständige Unterstützung von Visual Basic, c#, C/C++- und JavaScript. Allerdings bei der [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], d. h. von der [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453), anderen Programmiersprachen können im Debugger mit den gleichen umfangreichen Funktionen unterstützt werden.  
  
 Die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debugger (d. h. der Benutzeroberfläche) gemeinsamen Front-End der Komponenten zum Remotedebuggen, die, spezifisch für die Sprache, die gedebuggt wird wiederum sind, ist. Für neue Sprachen unterstützen, die erforderlich ist, indem die [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debugger ist es die erforderlichen Back-End-Komponenten, z. B. ein Debugging-Modul (DE) zu erstellen. Wo ist die [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] ins Spiel.  
  
 Die [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] enthält eine vollständige Referenz für alle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Elemente, die zum Erstellen einer neuen DE erforderlich. Darüber hinaus stehen Beispiele und Lernprogramme, mit deren Hilfe werden Ihnen den Einstieg erleichtern.  
  
 Ein End-to-End-Beispiel eines Projektsystems Sprache mit debugging-Unterstützung finden Sie unter der [IronPython-Beispiel](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089).  
  
 In den folgenden Abschnitten wird beschrieben, wie den Debugger mit Erweitern der [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erste Schritte](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 Beschreibt, was [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debuggen Angebote und wie Sie das SDK zu installieren.  
  
 [Erstellen eines benutzerdefinierten Debugmoduls](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Dokumentiert die benutzerdefinierten DE-Prozess, von der Vorbereitung Ihrer Anwendung für eine DE zum Trennen der Deutschland.  
  
 [Schreiben Sie eine CLR-Ausdrucksauswertung](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 Erläutert, ob Sie eine ausdrucksauswertung schreiben müssen.  
  
 [Auswählen einer Implementierungsstrategie für das Debugmodul](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 Erläutert, wie Ihre DE implementieren.  
  
 [Referenz](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 Dokumente der [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Debuggen-API.  
  
 [Beispiele](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 Enthält Links zu einem ausdrucksauswertung (Beispiel) common Language Runtime und ein Beispiel für die Debug-Modul.
