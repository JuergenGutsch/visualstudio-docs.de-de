---
title: Set-Methode (Map) (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 31ee71a0-b09d-442a-9e02-825accf94ffa
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a84a5b2714fde55fba03d581faa851d7245e001
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-map-javascript"></a>set-Methode (Map) (JavaScript)
Fügt einer Zuordnung ein neues Element hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```JavaScript  
mapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>Parameter  
 `mapObj`  
 Erforderlich. Ein `Map`-Objekt.  
  
 `key`  
 Erforderlich. Der Schlüssel für das neue Element.  
  
 `value`  
 Erforderlich. Der Wert des hinzuzufügenden Elements.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Gibt das `Map`-Objekt zurück, das das neue Schlüssel-Wert-Paar enthält.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert mithilfe eines vorhandenen Schlüssels zur Auflistung hinzufügen, ersetzt der neue Wert den alten Wert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie einer `Map` Member hinzufügen und sie dann abrufen.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// black  
// red  
// 2  
```  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]