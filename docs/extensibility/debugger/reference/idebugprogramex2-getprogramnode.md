---
title: IDebugProgramEx2::GetProgramNode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEx2::Attach
helpviewer_keywords: IDebugProgramEx2::Attach
ms.assetid: 1545ffbf-1422-4b5d-9bb9-314ba8665041
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a0d4f697bff8d46bbfb856441034a379796b9851
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramex2getprogramnode"></a>IDebugProgramEx2::GetProgramNode
Ruft die einem Programm zugeordneten Programm Knoten ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetProgramNode(   
   IDebugProgramNode2** ppProgramNode  
);  
```  
  
```csharp  
int GetProgramNode(   
   out IDebugProgramNode2 ppProgramNode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppProgramNode`  
 [out] Gibt eine [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) Objekt, das mit diesem Programm zugeordneten Programm Knoten darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)