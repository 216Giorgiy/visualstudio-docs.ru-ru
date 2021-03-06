---
title: DA0007. Избегайте использования исключений для потока управления | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAExceptionsThrown
- vs.performance.7
- vs.performance.rules.DA0007
- vs.performance.DA0007
ms.assetid: ee8ba8b5-2313-46c9-b129-3f3a2a232898
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2599282909c62e3a35702346f793dfd914c18ac4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54770838"
---
# <a name="da0007-avoid-using-exceptions-for-control-flow"></a>DA0007. Избегайте использования исключений для потока управления
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ИД правила | DA0007 |  
| Категория |. Использование .NET Framework |  
| Методы профилирования | Все |  
| Сообщение | Постоянно вызывается большое количество исключений. Рекомендуется сократить число используемых исключений в алгоритме программы.|  
| Тип сообщения | Предупреждение |  
  
 При профилировании с помощью выборки, памяти .NET или методов разрешения конфликтов ресурсов необходимо собрать минимум 25 выборок, чтобы активировать это правило.  
  
## <a name="cause"></a>Причина  
 Высокая частота вызовов обработчиков исключений .NET Framework в данных профилирования. Рекомендуется использовать другую логику потока управления для уменьшения числа вызываемых исключений.  
  
## <a name="rule-description"></a>Описание правила  
 Использование обработчиков исключений для перехвата ошибок и других событий, нарушающих выполнение программы, является хорошей практикой. Однако использование обработчиков исключений в алгоритме обычного выполнения программы может оказаться слишком затратным и этого следует избегать. Рекомендуется использовать исключения только в редких случаях, когда происходит что-то непредвиденное. Исключения не должны использоваться для возврата значений в ходе обычного потока выполнения программы. Во многих случаях можно избежать возникновения исключений, проверяя значения и используя условные конструкции для предотвращения выполнения операторов, вызывающих проблемы.  
  
 Дополнительные сведения см. в подразделе [Управление исключениями](http://go.microsoft.com/fwlink/?LinkID=177825) раздела **Глава 5. Улучшение производительности управляемого кода** в томе **Повышение производительности и масштабируемости приложений .NET** библиотеки **Шаблоны и практические рекомендации Майкрософт** на веб-сайте MSDN.  
  
## <a name="how-to-investigate-a-warning"></a>Изучение причин предупреждения  
 Дважды щелкните сообщение в окне "Список ошибок", чтобы перейти к представлению "Метки". Найдите столбец, содержащий измерения **Исключений CLR .NET(@ProcessInstance)\\Число исключений/сек**. Установите, есть ли какие-либо этапы выполнения программы, где обработка исключений происходит чаще. Используя профиль выборки, попытайтесь выявить операторы вызова исключений и блоки try/catch, которые являются причиной частых исключений. При необходимости добавьте операторы для перехвата блоков, чтобы понять, какие исключения обрабатываются наиболее часто. Там, где это возможно, замените часто выполняемые операторы вызова исключений или блоки перехвата обычными операторами управления и проверки значений.  
  
 Например, если вы обнаружите, что приложение часто обрабатывает исключение деления на ноль, добавьте в программу операторы для проверки знаменателей на нулевое значение. Это улучшит производительность приложения.
