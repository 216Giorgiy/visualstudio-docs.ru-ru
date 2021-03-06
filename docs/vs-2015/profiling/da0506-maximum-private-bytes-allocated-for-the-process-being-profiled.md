---
title: DA0506. Максимальное число байт исключительного пользования, распределенное для профилируемого процесса | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DA0506
- vs.performance.DA0506
- vs.performance.506
ms.assetid: e9c43554-9a85-4d98-9fa4-3b19986e7b62
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 97d1cacccc2fdd6abbd13aace1de71b28975779e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767495"
---
# <a name="da0506-maximum-private-bytes-allocated-for-the-process-being-profiled"></a>DA0506. Максимальное число байт исключительного пользования, распределенное для профилируемого процесса
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ИД правила | DA0506 |  
| Категория | Наблюдение за ресурсами |  
| Метод профилирования | Все |  
| Сообщение | Эти сведения были собраны только для информации. Счетчик байт исключительного пользования процесса измеряет объем виртуальной памяти, распределенный профилируемым процессом. Полученное значение является максимальным значением, зафиксированным в течение всех интервалов измерения.|  
| Тип правила | Сведения |  
  
 При профилировании с помощью выборки, памяти .NET или методов разрешения конфликтов ресурсов необходимо собрать минимум 10 выборок, чтобы активировать это правило.  
  
## <a name="rule-description"></a>Описание правила  
 В этом сообщении указывается максимальный объем виртуальной памяти (в байтах), выделяемой процессом в данный момент (байт исключительного пользования). Байты исключительного пользования представляют области виртуальной памяти, которые были выделены процессом и доступ к которым могут получить только потоки, выполняющиеся внутри процесса.  
  
 Для 32-разрядных процессов, выполняющихся на 32-разрядном компьютере, верхний предел участка исключительного пользования адресного пространства процесса — 2 ГБ. С помощью переключателя [/3 GB](http://go.microsoft.com/fwlink/?LinkId=177831) Boot.ini 32-разрядные процессы могут получить до 3 ГБ виртуальной памяти. 32-разрядный процесс, который выполняется на 64-разрядном компьютере, может получить до 4 ГБ виртуальной памяти исключительного пользования.  
  
 64-разрядный процесс, который выполняется на 64-разрядном компьютере, может получить до 8 ТБ виртуальной памяти исключительного пользования.  
  
 Значение в отчете является максимальным по всем интервалам измерения, в которых профилируемый процесс был активным.  
  
 Для получения дополнительных сведений об адресных пространствах процессов см. раздел [Виртуальное адресное пространство](http://go.microsoft.com/fwlink/?LinkId=177832) в документации по управлению памятью Windows.  
  
## <a name="how-to-use-rule-data"></a>Использование данных правила  
 Это значение используется для сравнения производительности разных версий или сборок программы или для анализа производительности приложения в различных сценариях профилирования.  
  
 Максимальное значение счетчика байтов исключительного пользования процесса, приближающееся к архитектурному ограничению размера адресного пространства процесса, может вызывать исключения нехватки памяти. Дополнительные сведения см. в разделе [Исследование проблем, связанных с использованием памяти](http://go.microsoft.com/fwlink/?LinkID=177833) в журнале MSDN Magazine.
