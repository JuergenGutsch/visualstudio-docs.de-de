---
title: IDebugComPlusSymbolProvider2::IsAddressSequencePoint | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugComPlusSymbolProvider2::IsAddressSequencePoint
- IsAddressSequencePoint
ms.assetid: 89b27c57-5295-428b-8229-a402500d8cd3
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b6c3fc4743ca66f490813324b3183dbd8632a802
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcomplussymbolprovider2isaddresssequencepoint"></a>IDebugComPlusSymbolProvider2::IsAddressSequencePoint
Bestimmt, ob die angegebene Debug-Adresse ein Sequenzpunkt ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsAddressSequencePoint(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int IsAddressSequencePoint(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAddress`  
 [in] Debuggen Sie die Adresse, die durch dargestellt ist die [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Debug-Adresse ein Sequenzpunkt ist, gibt `S_OK`ist, andernfalls gibt `S_FALSE`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Implementierung dieser Methode für eine **CDebugSymbolProvider** -Objekt, das macht die [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md) Schnittstelle.  
  
```cpp  
HRESULT CDebugSymbolProvider::IsAddressSequencePoint(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    METHOD_ENTRY( CDebugSymbolProvider::LoadSymbol );  
  
    IfFalseGo( pAddress, E_INVALIDARG );  
  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsSequencePoint( address.addr.addr.addrMethod.tokMethod,  
                                   address.addr.addr.addrMethod.dwVersion,  
                                   address.addr.addr.addrMethod.dwOffset ))  
    {  
  
        // S_FALSE indicates this is not a sequence point  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::LoadSymbol, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)