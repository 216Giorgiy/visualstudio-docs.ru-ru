---
title: Свойства сеанса анализа производительности | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,properties
- property pages,Profiling Tools
- performance tools, performance session properties
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77da53856e0562d036fade431dd0deba0376fe9f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56624975"
---
# <a name="performance-session-properties"></a>Свойства сеанса анализа производительности

В окне **Сеанс производительности** можно настраивать параметры профилирования приложения. В нем также хранятся отчеты, созданные для сеанса профилирования.

**Сеанс анализа производительности** создается либо посредством запуска **мастера производительности**, либо вручную. **Сеанс производительности** отображается в **обозревателе производительности** после того, как был создан **сеанс производительности**.

Чтобы просмотреть свойства **сеанса производительности**, найдите имя сеанса в окне **Обозреватель производительности**, щелкните его правой кнопкой мыши и выберите пункт **Свойства**.

Ниже перечислены страницы свойств сеанса анализа производительности.

## <a name="general"></a>Общие

Эти параметры позволяют выбрать метод профилирования, добавить коллекцию объектов .NET и данные о времени существования, указать соглашения о наименовании и местоположение файла отчета по умолчанию.

Дополнительные сведения:

[Практическое руководство. Выбор методов сбора данных](../profiling/how-to-choose-collection-methods.md)

[Сбор данных о выделении памяти для объектов .NET и времени их жизни](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)

- [Практическое руководство. Настройка параметров имени файла с данными о производительности](../profiling/how-to-set-performance-data-file-name-options.md)

## <a name="launch"></a>Launch

Эти параметры позволяют выбирать двоичные файлы из списка и указывать порядок запуска двоичных файлов.

Дополнительные сведения см. в разделе [Как Определение двоичного файла для запуска](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="sampling"></a>Дискретизация

Эти параметры позволяют выбрать событие выборки и интервал выборки при профилировании с выборкой. Событие выборки используется для сбора данных профилирования через определенный интервал времени. Например, если событием выборки являются такты процессора и для интервала выборки задано значение 10 000 000, то данные профилирования собираются через каждые 10 миллионов тактов процессора. Можно выбрать один из четырех типов событий выборки, указанных ниже.

- Циклы синхронизации — для проблем, связанных с ЦП.
- Ошибки страниц — для проблем, связанных с памятью.
- Системные вызовы — для проблем, связанных с вводом-выводом.
- Счетчики производительности — для проблем производительности нижнего уровня.
- На основе доступных счетчиков производительности можно определять дополнительные события выборки.

Дополнительные сведения см. в разделе [Как Выбор событий выборки](../profiling/how-to-choose-sampling-events.md)

## <a name="binary"></a>Binary
Эти параметры позволяют указать, следует ли переместить инструментированный двоичный файл в другое местоположение. Например, если при профилировании файла *My.DLL* не требуется перемещать инструментированный двоичный файл, то создается резервная копия файла *My.DLL* с именем *My.Orig.DLL*. Затем в файл *My.DLL* вставляются зонды для сбора данных. Если пользователь решит переместить инструментированный двоичный файл, то исходный двоичный файл не переименовывается, а инструментированный двоичный файл копируется в указанное местоположение.

Дополнительные сведения см. в разделе [Как Определение двоичного файла для запуска](../profiling/how-to-specify-the-binary-to-start.md)

## <a name="tier-interactions"></a>Взаимодействия уровня

Дополнительные сведения см. в разделе [Сбор данных взаимодействия уровней](../profiling/collecting-tier-interaction-data.md).

## <a name="instrumentation"></a>Инструментирование

Эти параметры позволяют собирать данные о производительности кода JScript на веб-страницах [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] и указать в полях **События до инструментирования** и **События после инструментирования** любые события, которые должны происходить до или после процесса инструментирования.

Дополнительные сведения:

[Практическое руководство. Профилирование кода JavaScript в веб-страницах](../profiling/how-to-profile-javascript-code-in-web-pages.md)

[Практическое руководство. Указание команд, предваряющих инструментирование, и команд после инструментирования](../profiling/how-to-specify-pre-and-post-instrument-commands.md)

## <a name="cpu-counters"></a>Счетчики ЦПУ

Эти параметры позволяют собирать данные о счетчиках производительности ЦП при использовании для профилирования метода инструментирования. Переносимые счетчики производительности доступны независимо от архитектуры и изготовителя ЦП. Платформенные события относятся к конкретным архитектурам и изготовителям ЦП. Дополнительные сведения об аппаратных счетчиках производительности в соответствующей документации по процессору.

Дополнительные сведения см. в разделе [Как Сбор данных счетчиков производительности ЦП](../profiling/how-to-collect-cpu-counter-data.md)

## <a name="windows-events"></a>события Windows;

Во время профилирования можно собирать данные от поставщиков трассировки событий. Просматривать эти данные можно с помощью параметра `/calltrace` средства командной строки *VSPerfReport.exe*. Дополнительные сведения о трассировке событий Windows (ETW) см. в разделе [О трассировке событий](http://go.microsoft.com/fwlink/?linkid=90752).

Дополнительные сведения:

[Практическое руководство. Сбор данных трассировки событий Windows](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)

[VSPerfReport](../profiling/vsperfreport.md)

## <a name="windows-counters"></a>Счетчики Windows

Этот параметр позволяет собирать данные счетчиков монитора производительности Windows. Чтобы их собрать, установите флажок **Сбор счетчиков производительности Windows**. Интервал сбора можно указать в поле **Интервал сбора**. Можно также задать параметры **Категория счетчика** и **Экземпляр**. Доступны некоторые счетчики монитора производительности Windows по умолчанию.

 Дополнительные сведения см. в разделе [Как Сбор данных счетчиков производительности Windows](../profiling/how-to-collect-windows-counter-data.md).

## <a name="advanced"></a>Дополнительно

Эти настройки позволяют добавлять параметры процесса инструментирования, указывая один или несколько параметров средства профилирования [VSInstr](../profiling/vsinstr.md). Если в приложении используются несколько версий, можно также задать версию среды CLR для профилирования.

Дополнительные сведения:

[Практическое руководство. Определение среды выполнения .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)

[Практическое руководство. Определение дополнительных параметров инструментирования](../profiling/how-to-specify-additional-instrumentation-options.md)

## <a name="see-also"></a>См. также

[Обзоры](../profiling/overviews-performance-tools.md)
[Настройка сеансов анализа производительности](../profiling/configuring-performance-sessions.md)
[Управление сбором данных](../profiling/controlling-data-collection.md)