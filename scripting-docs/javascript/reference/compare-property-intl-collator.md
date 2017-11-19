---
title: "Свойство Compare (Intl.Collator) | Документы Microsoft"
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
ms.assetid: 59f274dc-6e52-4344-8d5c-b9f0000b66e0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bfd222ac8d2c94efe279177e7f4d8ffdf850f44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="compare-property-intlcollator"></a>Свойство compare (Intl.Collator)
Возвращает функцию, которая сравнивает две строки с помощью средства упорядочивания порядок сортировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```JavaScript  
collatorObj.compare  
```  
  
#### <a name="parameters"></a>Параметры  
 `collatorObj`  
 Обязательный. Имя `Collator` объект, используемый для сравнения.  
  
## <a name="remarks"></a>Примечания  
 Функции, возвращенной методом `compare` свойство принимает два аргумента, `x` и `y`и возвращает результат сравнения языковому стандарту `x` и `y` , используя параметры, указанные в `Collator` объект.  
  
 Результат сравнения будет:  
  
-   -1, если `x` перед `y` в порядке сортировки.  
  
-   0 (нуль), если `x` равен `y` в порядке сортировки.  
  
-   1, если `x` после `y` в порядке сортировки.  
  
## <a name="example"></a>Пример  
 В следующем примере создается `Collator` объекта и выполняет сравнение.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE-u-co-phonebk"]);  
  
if (console && console.log) {  
    console.log(co.compare("a", "b")); // Returns -1  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Collator` объекты для сортировки массива. В этом примере показаны различия определенного языкового стандарта.  
  
```JavaScript  
var co1 = new Intl.Collator(["de-DE-u-co-phonebk"]);  
var co2 = new Intl.Collator(["de-DE"]);  
var co3 = new Intl.Collator(["en-US"]);  
  
var arr = ["ä", "ad", "af", "a"];  
  
if (console && console.log) {  
    console.log(arr.sort(co1.compare));  // Returns a,ad,ä,af  
    console.log(arr.sort(co2.compare));  // Returns a,ä,ad,af  
    console.log(arr.sort(co3.compare));  // Returns a,ä,ad,af  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Collator` объект для поиска строки.  
  
```JavaScript  
// String to search  
var arr = ["ä", "ad", "af", "a"];  
// String searched for  
var s = "af";  
  
var co = new Intl.Collator("de-DE", { usage: "search" });  
var matches = arr.filter(function (i) {  
    return co.compare(i, s) === 0;  
});  
  
if (console && console.log) {  
    console.log(matches);  // Returns af  
}  
```  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Объект Intl.Collator](../../javascript/reference/intl-collator-object-javascript.md)