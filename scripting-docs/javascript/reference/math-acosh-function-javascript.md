---
title: "Функция Math.acosh (JavaScript) | Microsoft Docs"
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
ms.assetid: 881dd2a0-36a5-403b-a3dc-523d8e1e1317
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# Функция Math.acosh (JavaScript)
Возвращает гиперболический арккосинус \(или обратный гиперболический косинус\) числа.  
  
## Синтаксис  
  
```  
Math.acosh(number)  
```  
  
#### Параметры  
 Обязательный аргумент `number` является числовым выражением.  
  
## Возвращаемое значение  
 Обратный гиперболический косинус аргумента `number` в радианах.  
  
## Пример  
 В следующем примере кода показано, как использовать функцию `acosh`.  
  
```javascript  
var v1 = Math.acosh(3);  
vary v2 = Math.acosh(-1);  
  
document.write(v1);  
document.write("</br>");  
document.write(v2);  
  
// Output:  
// 1.762747174039086  
// NaN  
  
```  
  
## Заметки  
 **Применение**: [Объект Math](../../javascript/reference/math-object-javascript.md)  
  
## Требования  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## См. также  
 [Функция Math.acos](../../javascript/reference/math-acos-function-javascript.md)   
 [Функция Math.asin](../../javascript/reference/math-asin-function-javascript.md)   
 [Функция Math.atan](../../javascript/reference/math-atan-function-javascript.md)   
 [Функция Math.cos](../../javascript/reference/math-cos-function-javascript.md)   
 [Функция Math.sin](../../javascript/reference/math-sin-function-javascript.md)   
 [Функция Math.tan](../../javascript/reference/math-tan-function-javascript.md)   
 [Объект Math](../../javascript/reference/math-object-javascript.md)