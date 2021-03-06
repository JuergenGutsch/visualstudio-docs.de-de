---
title: Steuerelementereignissen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 15f9eff023fa875499881eb05a0795b0eaa83842
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="control-events"></a>Steuerelementereignisse
Sie müssen die Ereignisse während der gesteuerte Ausführung des Programms senden. Alle Ereignisse gesendet werden, mithilfe der [IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md) -Schnittstelle und Attribute, die Sie implementieren müssen die [IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md) Methode.  
  
## <a name="additional-methods"></a>Zusätzliche Methoden  
 Einige Ereignisse erfordern die Implementierung von zusätzlichen Methoden wie folgt:  
  
-   Senden der [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) Schnittstelle, die bei der Initialisierung der Debugging-Modul (DE) erfordert, dass Sie zum Implementieren der [IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md) Methode.  
  
-   Steuerung der Ausführung erfordert die Implementierung des Steuerelementereignisse wie das [IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md) und[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) Schnittstellen. **IDebugBreakEvent2** ist nur für die asynchrone Unterbrechung erforderlich.  
  
-   Einzelschritt in Funktionen erfordert die Implementierung der [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) Schnittstelle und die zugehörigen Methoden.  
  
 Ableiten von Haltepunkten Ereignisse erfordern Implementierung der [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md), [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md), und [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) Schnittstellen, als auch die [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) und [EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) Methoden.  
  
 Asynchrone ausdrucksauswertung erfordert, dass Sie zum Implementieren der [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) Schnittstelle und die zugehörige [IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md) [und GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) Methoden.  
  
 Synchrone Ereignisse erforderlich ist, implementieren die [IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md) Methode.  
  
 Für das Modul Zeichenfolge-Stil Ausgabe zu schreiben, müssen Sie implementieren die [IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md) Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführungssteuerung und Zustandsauswertung](../../extensibility/debugger/execution-control-and-state-evaluation.md)