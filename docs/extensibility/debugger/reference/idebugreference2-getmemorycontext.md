---
title: IDebugReference2::GetMemoryContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2::GetMemoryContext
helpviewer_keywords: IDebugReference2::GetMemoryContext
ms.assetid: 47fc3827-07a0-4eee-b7f4-fc1c62e6b25c
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4af8e87bf30b06e6ca55c6bd006e907d80532f4d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugreference2getmemorycontext"></a>IDebugReference2::GetMemoryContext
Ruft eine Arbeitsspeicher-Kontext eines Verweises ab. Für zukünftige Verwendung reserviert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemoryContext (   
   IDebugMemoryContext2** ppMemory  
);  
```  
  
```csharp  
int GetMemoryContext (   
   out IDebugMemoryContext2 ppMemory  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppMemory`  
 [out] Gibt die [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) Objekt, das den Wert des Verweises zugeordneten Arbeitsspeicher darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt immer `E_NOTIMPL` zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)