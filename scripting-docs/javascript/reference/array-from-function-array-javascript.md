---
title: Array.From-Funktion (Array) (JavaScript) | Microsoft Docs
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
ms.assetid: 1bf59a99-f860-4c4d-b4c6-d5f1f946a490
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a240cb439942bfeb6b4c9a1febb4d24cef1c5c18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2017
---
# <a name="arrayfrom-function-array-javascript"></a>Array.from-Funktion (Array) (JavaScript)
Gibt ein Array aus einem arrayähnlichen oder iterierbaren Objekt zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
Array.from (arrayLike [ , mapfn [ , thisArg ] ] );  
```  
  
#### <a name="parameters"></a>Parameter  
 `arrayLike`  
 Erforderlich. Ein arrayähnliches oder iterierbares Objekt.  
  
 `mapfn`  
 Dies ist optional. Eine Zuordnungsfunktion zum Aufrufen der einzelnen Elemente in `arrayLike`.  
  
 `thisArg`  
 Dies ist optional. Gibt das `this`-Objekt in der Zuordnungsfunktion an.  
  
## <a name="remarks"></a>Hinweise  
 Der `arrayLike`-Parameter muss entweder ein Objekt mit indizierten Elementen und einer `length`-Eigenschaft oder ein iterierbares Objekt sein, z. B. ein `Set`-Objekt.  
  
 Die optionale Zuordnungsfunktion wird für jedes Element im Array aufgerufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Array aus einer Auflistung von DOM-Elementknoten zurückgegeben.  
  
```JavaScript  
var elemArr = Array.from(document.querySelectorAll('*'));  
var elem = elemArr[0]; // elem contains a reference to the first DOM element  
  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Array von Zeichen zurückgegeben.  
  
```JavaScript  
var charArr = Array.from("abc");  
// charArr[0] == "a";  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Array von Objekten zurückgegeben, die in der Auflistung enthalten sind.  
  
```JavaScript  
var setObj = new Set("a", "b", "c");  
var objArr = Array.from(setObj);  
// objArr[1] == "b";   
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Verwendung der Pfeilsyntax und eine Zuordnungsfunktion, um den Wert von Elementen zu ändern.  
  
```JavaScript  
var arr = Array.from([1, 2, 3], x => x * 10);  
// arr[0] == 10;  
// arr[1] == 20;  
// arr[2] == 30;  
```  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]