---
title: Как выполнить Выбор событий выборки | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.sampling
helpviewer_keywords:
- clock cycles sample event
- sample events, choosing
- profiling tools, sample events
- page faults sample event
- system calls sample event
- performance counter sample event
- performance tools, sample events
ms.assetid: ce7cb734-80ac-4930-a4ef-e24395e1cc07
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3d3562f446ebbc5f6e24ce9911ff9e09daa04e55
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621322"
---
# <a name="how-to-choose-sampling-events"></a>Как выполнить Выбор событий выборки
По умолчанию средства профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] собирают данные о производительности с интервалом, заданным как число циклов процессора, используемых профилируемым процессом. По умолчанию число циклов в одном интервале — 10 000 000, что приблизительно соответствует 0,01 секунды для процессора 1 ГГц. Вы можете изменить число циклов в интервале и событие выборки. Доступны следующие события выборки:

-   циклы синхронизации — для проблем, связанных с ЦП;

-   ошибки страниц — для проблем, связанных с памятью;

-   системные вызовы — для проблем, связанных с вводом-выводом;

-   счетчик производительности — счетчики ЦП для незначительных проблем производительности.

> [!IMPORTANT]
>  При сборе данных о памяти .NET (операции выделения, время жизни объектов или все вместе) с помощью метода выборки все заданные пользователем события выборки игнорируются и для сбора данных используются соответствующие события выделения памяти или сборки мусора (или оба события).

### <a name="to-select-a-sample-event"></a>Выбор события выборки

1.  В **обозревателе производительности**щелкните правой кнопкой мыши сеанс производительности, а затем выберите **Свойства**.

2.  В окне **Страницы свойств** щелкните пункт **Выборка**.

3.  В раскрывающемся списке **Событие выборки** выберите событие выборки, которое вы хотите использовать для профилирования приложения.

    > [!NOTE]
    >  Представление **Доступные счетчики производительности** доступно только при выборе в раскрывающемся списке **Событие выборки** события **Счетчик производительности**.

4.  При выборе события **Счетчик производительности** выберите конкретный счетчик ЦП в элементе управления иерархического представления **Доступные счетчики производительности**.

    -   Счетчики в узле **Переносимые события** доступны для всех типов процессоров.

    -   Счетчики в узле **События платформы** определяются конкретным процессором на текущем компьютере и могут быть недоступны для процессоров других типов.

5.  При выборе события выборки значение интервала выборки по умолчанию отображается в текстовом поле **Интервал выборки**. При необходимости можно ввести нужное значение в этом текстовом поле.

## <a name="see-also"></a>См. также
- [Настройка сеансов анализа производительности](../profiling/configuring-performance-sessions.md)
- [Практическое руководство. Выбор методов сбора данных](../profiling/how-to-choose-collection-methods.md)
- [Счетчики ЦП и Windows](../profiling/cpu-and-windows-counters.md)
- [Общие сведения о значениях выборочных данных](../profiling/understanding-sampling-data-values.md)
- [Профилирование из командной строки](../profiling/using-the-profiling-tools-from-the-command-line.md)