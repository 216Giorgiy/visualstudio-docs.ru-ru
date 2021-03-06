---
title: Класс иерархия символьных типов | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], class hierarchies
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ece5c23a04901eaf0c17e7dfbf59f1ce7c5ccfa2
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58979436"
---
# <a name="class-hierarchy-of-symbol-types"></a>Иерархия классов символьных типов
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

В следующей таблице описаны символьных типов в иерархии классов.  
  
## <a name="symbol-types"></a>Типы символов  
  
|Тип символа|Описание|  
|-----------------|-----------------|  
|[UDT](../../debugger/debug-interface-access/udt.md)|Символ, используемый для представления каждого класса, структуры и объединения.|  
|[Enum (SDK для доступа к интерфейсу отладки)](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|Символ для перечислимых типов.|  
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|Символ для типов указателей.|  
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|Символ для типов массивов.|  
|[BaseType](../../debugger/debug-interface-access/basetype.md)|Символ для базовых типов|  
|[Typedef (SDK для доступа к интерфейсу отладки)](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|Символ, который вводит имена для других типов.|  
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|Символ, используемый для каждого базового класса определяемого пользователем типа (UDT).|  
|[Friend (SDK для доступа к интерфейсу отладки)](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|Символ для дружественные классы и дружественных функций.|  
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|Символ для каждой подписи уникальные функции.|  
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|Символ для каждого параметра функции.|  
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|Символ для размера виртуальной таблицы.|  
|[VTable](../../debugger/debug-interface-access/vtable.md)|Символ для виртуальную таблицу.|  
|[CustomType](../../debugger/debug-interface-access/customtype.md)|Символ для типа поставщика.|  
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|Символ для типа, определенного в метаданных.|  
|[Измерение](../../debugger/debug-interface-access/dimension.md)|Символ для измерений массива.|  
  
> [!NOTE]
>  Каждый символ может иметь свойства, которые содержат сведения о символ, а также ссылки на другие символы. Эти свойства перечислены в разделах отдельных символов.  
  
## <a name="see-also"></a>См. также  
 [Перечисление CV_access_e](../../debugger/debug-interface-access/cv-access-e.md)   
 [Лексическая иерархия символьных типов](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Символы и теги символов](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)
