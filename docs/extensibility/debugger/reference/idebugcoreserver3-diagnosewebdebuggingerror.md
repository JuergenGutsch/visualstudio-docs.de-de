---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords: IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4b93a82bfd79abe6400e8e1bb213b00154fbbf16
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Versuche, um zu bestimmen, warum ein Auto-attach fehlgeschlagen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszUrl`  
 [in] Wird derzeit nicht verwendet. sollte immer auf einen null-Wert festgelegt werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben. Im folgenden sind die anderen typische Rückgabecodes:  
  
|Code|Beschreibung|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Kann nicht bestimmen, warum der Remoteserver nicht mit dem Debuggen beginnen.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Kann nicht auf dem Remoteserver, möglicherweise aufgrund unzureichender Berechtigungen debuggen, oder weil das DEBUG-Verb nicht aktiviert ist.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Der Webserver wurde gesperrt und blockiert das DEBUG-Verb ist erforderlich, um Debuggen zu aktivieren.|  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)