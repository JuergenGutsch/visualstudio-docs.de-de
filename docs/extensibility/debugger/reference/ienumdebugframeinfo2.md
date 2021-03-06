---
title: IEnumDebugFrameInfo2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFrameInfo2
helpviewer_keywords: IEnumDebugFrameInfo2
ms.assetid: 994e30ad-435a-4f9e-9272-d96d9e01099c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fce74b91512ee22eda7ce8c3e61de0ac03636d2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugframeinfo2"></a>IEnumDebugFrameInfo2
Diese Schnittstelle listet [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) Strukturen.  
  
## <a name="syntax"></a>Syntax  
  
```  
IEnumDebugFrameInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debugging-Modul (DE) implementiert diese Schnittstelle, um eine Liste von Strukturen zu bieten, die die aktuelle Aufrufliste beschreibt.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Visual Studio-Aufrufe [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) zum Abrufen dieser Schnittstelle, sobald ein Haltepunkt Ausnahme oder ein Stillstand auftritt in einem Programm, das gerade gedebuggt wird.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Die folgende Tabelle zeigt die Methoden der `IEnumDebugFrameInfo2`.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Nächste](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)|Ruft eine angegebene Anzahl von [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) Strukturen in eine Enumerationsfolge.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugframeinfo2-skip.md)|Überspringt die angegebene Anzahl von [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) Strukturen in eine Enumerationsfolge.|  
|[Zurücksetzen](../../../extensibility/debugger/reference/ienumdebugframeinfo2-reset.md)|Setzt ein Enumerationsfolge auf den Anfang zurück.|  
|[Klon](../../../extensibility/debugger/reference/ienumdebugframeinfo2-clone.md)|Erstellt einen Enumerator, der den gleichen Enumeration Status als der aktuelle Enumerator enthält.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)|Ruft die Anzahl der [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) Strukturen in einen Enumerator.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Studio ruft diese Schnittstelle ab, als der erste Schritt zur Behandlung von ein Haltepunkt, eine Ausnahme oder ein vom Benutzer generierte anhalten, auf das derzeit debuggte Programm. Die Liste der [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) Strukturen darstellt, die aktuelle Aufrufliste, rufen Sie mit der aktuellen Funktionsaufruf am Anfang der Liste und die älteste Funktion am Ende der Liste. Jede `FRAMEINFO` stellt einen Stapelrahmen, der einen Kontext, in dem Ausdrücke ausgewertet werden können, und erläutert, lokale Variablen, dar.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)