---
title: "Свойство constructor (Boolean) | Microsoft Docs"
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
ms.assetid: b67ca875-23c6-4687-a5ce-1cdd25d1c923
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# Свойство constructor (Boolean)
Указывает функцию, которая создает объект типа Boolean.  
  
## Синтаксис  
  
```  
  
boolean.constructor([[value])  
```  
  
#### Параметры  
 `boolean`  
 Имя объекта Boolean.  
  
 `value`  
 Необязательный.  Задает значение объекта Boolean.  Это может быть число 1 или 0 или строка "true" или "false".  
  
## Заметки  
 Свойство `constructor` содержит ссылку на функцию, которая создает экземпляры объекта Boolean.  
  
## Пример  
 В следующем примере кода демонстрируется использование свойства constructor.  
  
```javascript  
var x = new Boolean("true");  
  
if (x.constructor == Boolean)  
    document.write("Object is a Boolelan.");  
  
// Output:  
// Object is a Boolean.  
  
```  
  
## Требования  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]