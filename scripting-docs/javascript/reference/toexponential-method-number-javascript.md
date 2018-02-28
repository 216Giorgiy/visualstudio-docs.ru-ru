---
title: "Метод toExponential (Number) (JavaScript) | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- toExponential
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toExponential method
ms.assetid: 7c4a6d84-3c1f-4cc4-a67d-7753e5d4ed66
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fff2f2bc0c443fa9308c8d01dcea42a3cec9ff04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="toexponential-method-number-javascript"></a>Метод toExponential (Number) (JavaScript)
Представляет число в экспоненциальном представлении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
numObj. toExponential([fractionDigits])  
```  
  
## <a name="parameters"></a>Параметры  
 `numObj`  
 Обязательный. Объект **номер** объекта.  
  
 `fractionDigits`  
 Необязательно. Количество цифр после десятичной запятой. Должен быть в диапазоне 0 - 20, включительно.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает строковое представление числа в экспоненциальном представлении. Строка содержит одну цифру перед десятичной запятой и может содержать `fractionDigits` цифры после него.  
  
 Если `fractionDigits` не указан, `toExponential` метод возвращает количество цифр, необходимые для уникального определения числа.  
  
## <a name="example"></a>Пример  
  
```JavaScript  
var num = new Number(123);  
var exp = num.toExponential();  
document.write(exp);  
document.write("<br/>");  
  
num = new Number(123.456);  
exp = num.toExponential(5);  
document.write(exp);  
  
// Output:   
// 1.23e+2  
// 1.23456e+2  
```  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Применяется к**: [число объектов](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>См. также  
 [Метод toFixed (Number)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [Метод toPrecision (Number)](../../javascript/reference/toprecision-method-number-javascript.md)