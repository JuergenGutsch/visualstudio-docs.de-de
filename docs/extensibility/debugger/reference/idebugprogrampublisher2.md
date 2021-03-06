---
title: IDebugProgramPublisher2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramPublisher2
helpviewer_keywords: IDebugProgramPublisher2 interface
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 20f5fe710cc05425263245c9a78ff804aca2ac20
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogrampublisher2"></a>IDebugProgramPublisher2
Diese Schnittstelle ermöglicht es, ein Debugging-Modul (DE) oder benutzerdefinierte Port Lieferanten zum Debuggen von Programmen zu registrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Visual Studio implementiert diese Schnittstelle zum Registrieren von Programmen, die gedebuggt wird, um für mehrere Prozesse Debuggen sichtbar zu machen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Aufrufen von COM `CoCreateInstance` funktionieren mit `CLSID_ProgramPublisher` zum Abrufen dieser Schnittstelle (siehe Beispiel). Ein DE oder einen benutzerdefinierten Port Lieferanten verwendet diese Schnittstelle zum Registrieren von Programm-Knoten, die alle gedebuggten Programme darstellen.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Diese Schnittstelle implementiert, die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|Stellt einen Knoten für die Anwendung zur Verfügung des- und die Sitzung Debug-Manager (SDM).|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|Entfernt einen Programm-Knoten an, sodass er nicht mehr verfügbar ist.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|Stellt ein Programm des-und die SDM zur Verfügung.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|Entfernt ein Programm an, damit es nicht mehr verfügbar ist.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|Setzt ein Flag gibt an, dass ein Debugger vorhanden ist.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle stellt Programme und Programm Knoten zur Verfügung (d. h. "veröffentlicht") für die Verwendung von des- und die Sitzung Debug-Manager (SDM). Um veröffentlichte Programme und Programm Knoten zuzugreifen, verwenden Sie die [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) Schnittstelle. Dies ist die einzige Möglichkeit, die Visual Studio erkennt, dass eine Anwendung gedebuggt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie Instanziieren der Herausgeber des Programms und registrieren einen Programm-Knoten. Dies ist das Lernprogramm entnommen [Veröffentlichen der Anwendung Knoten](http://msdn.microsoft.com/en-us/d0100e02-4e2b-4e72-9e90-f7bc11777bae).  
  
```cpp  
// This is how m_srpProgramPublisher is defined in the class definition:  
// CComPtr<IDebugProgramPublisher2> m_srpProgramPublisher.  
  
void CProgram::Start(IDebugEngine2 * pEngine)  
{  
    m_spEngine = pEngine;  
  
    HRESULT hr = m_srpProgramPublisher.CoCreateInstance(CLSID_ProgramPublisher);  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to create the program publisher: 0x%x.", hr);  
        return;  
    }  
  
    // Register ourselves with the program publisher. Note that  
    // CProgram implements the IDebgProgramNode2 interface, hence  
    // the static cast on "this".  
    hr = m_srpProgramPublisher->PublishProgramNode(  
        static_cast<IDebugProgramNode2*>(this));  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to publish the program node: 0x%x.", hr);  
        m_srpProgramPublisher.Release();  
        return;  
    }  
  
    ATLTRACE("Added program node.\n");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Core-Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)