---
title: "Set-Methode (Uint16Array) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 5bfbc50b-d786-4c0d-918a-ae1241a32626
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# Set-Methode (Uint16Array)
Legt einen Wert oder ein Wertearray fest.  
  
## Syntax  
  
```javascript  
uint16Array.set(index, value);  
uint16Array.set(array, offset);  
  
```  
  
## Parameter  
 `index`  
 Der Index des festzulegenden Speicherorts.  
  
 `value`  
 Der festzulegende Wert.  
  
 `array`  
 Ein typisiertes oder nicht typisiertes, festzulegendes Array von Werten.  
  
 `offset`  
 Der Index im aktuellen Array, an dem die Werte geschrieben werden sollen.  
  
## Hinweise  
 Wenn das Eingabearray ein TypedArray ist, können die beiden Arrays das gleiche zugrunde liegende ArrayBuffer verwenden.  In diesem Fall werden die Werte so festgelegt, als ob alle Daten zunächst in einen temporären Puffer kopiert werden, der sich mit keinem der Arrays überschneidet, und anschließend die Daten aus dem temporären Puffer in das aktuelle Array kopiert werden.  
  
 Wenn der Offset plus die Länge des angegebenen Arrays außerhalb des Bereichs für das aktuelle TypedArray liegt, wird eine Ausnahme ausgelöst.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie das erste Element des Arrays festgelegt wird.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint16Array(buffer.byteLength / 2);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## Anforderungen  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]