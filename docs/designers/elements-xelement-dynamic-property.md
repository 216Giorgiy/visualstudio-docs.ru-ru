---
title: "Elements (динамическое свойство XElement) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: 2
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 9044821c2bfee0dba8ffa91f3d91afd565b8d957
ms.openlocfilehash: 24dc395f229ae79696df926630c7e72b5ad1672d
ms.lasthandoff: 02/22/2017

---
# <a name="elements-xelement-dynamic-property"></a>Elements (динамическое свойство XElement)
Получает индексатор, который используется для извлечения дочернего элемента текущего элемента с заданным развернутым именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Индексатор типа `IEnumerable<XElement> Item(String expandedName)`. Индексатор принимает развернутое имя нужных дочерних элементов и возвращает соответствующие дочерние элементы в коллекцию <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`.  
  
## <a name="remarks"></a>Примечания  
 Это свойство является аналогом метода <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> класса <xref:System.Xml.Linq.XContainer>.  
  
 Элементы в возвращаемой коллекции располагаются в порядке исходного XML-документа.  
  
 В данном свойстве используется отложенное выполнение.  
  
## <a name="see-also"></a>См. также  
 [XElement Class Dynamic Properties](../designers/xelement-class-dynamic-properties.md)  (Динамические свойства класса XElement)  
 [Elements (XElement Dynamic Property)](../designers/element-xelement-dynamic-property.md)  (Elements (Динамическое свойство XElement))  
 [Descendants (динамическое свойство XElement)](../designers/descendants-xelement-dynamic-property.md)
