---
title: "Свойство byteOffset (Float32Array) | Microsoft Docs"
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
ms.assetid: 9417c741-d307-404b-8d37-22f0d184a0d7
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Свойство byteOffset (Float32Array)
Только для чтения.  Смещение данного массива от начала его ArrayBuffer в байтах, зафиксированное во время создания.  
  
## Синтаксис  
  
```javascript  
var arrayOffset = float32Array.byteOffset;  
```  
  
## Пример  
 В следующем примере показано, как получить смещение массива.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            alert(floatArr.byteOffset);  
        }  
    }  
  
```  
  
## Требования  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]