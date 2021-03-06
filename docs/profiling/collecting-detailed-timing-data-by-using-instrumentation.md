---
title: Сбор подробных сведений о времени с помощью инструментирования | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9bd897d6b986b1d0c7a06a36a58eb88ba929bfc4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617578"
---
# <a name="collect-detailed-timing-data-by-using-instrumentation"></a>Сбор подробных сведений о времени с помощью инструментирования
Метод инструментирования средств профилирования [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] позволяет внедрить код профилирования в копию модуля. Во время профилирования код записывает все входы, выходы и вызовы функций в модуле. Метод инструментирования целесообразно использовать для сбора подробных сведений о разделе кода и для понимания влияния операций ввода-вывода на производительность приложения.

 Метод инструментирования можно задать с помощью одной из приведенных ниже процедур.

-   На первой странице мастера профилирования выберите пункт **Инструментирование**.

-   На панели инструментов **обозревателя производительности** в списке **Метод** щелкните пункт **Инструментирование**.

-   На странице **Общие** диалогового окна свойств сеанса анализа производительности выберите **Инструментирование**.

## <a name="common-tasks"></a>Типичные задачи
 Дополнительные параметры можно указать в диалоговом окне _Сеанс производительности_**страницы свойств** сеанса анализа производительности. Чтобы открыть это диалоговое окно, выполните указанные ниже действия.

- В **обозревателе производительности**щелкните правой кнопкой мыши имя сеанса анализа производительности и выберите пункт **Свойства**.

  В задачах в приведенной ниже таблице описываются параметры, которые можно задать в диалоговом окне _Сеанс производительности_**страницы свойств** при профилировании с помощью метода инструментирования.

|Задача|Связанное содержимое|
|----------|---------------------|
|На странице **Общие** добавьте данные по выделению памяти .NET и времени существования и укажите сведения об именовании для создаваемого файла данных профилирования (VSP).|-   [Сбор данных о выделении памяти для объектов .NET и времени их жизни](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Практическое руководство. Настройка параметров имени файла с данными о производительности](../profiling/how-to-set-performance-data-file-name-options.md)|
|При наличии в решении нескольких проектов исполняемых файлов (EXE) выберите на странице **Запуск** запускаемое приложение и порядок запуска.|-   [Практическое руководство. Определение двоичного файла для запуска](../profiling/how-to-specify-the-binary-to-start.md)|
|На странице **Двоичные файлы** укажите расположение для инструментированных копий модулей. По умолчанию исходные двоичные файлы перемещаются в папку для резервного копирования.|-   [Практическое руководство. Перемещение инструментированных двоичных файлов](../profiling/how-to-relocate-instrumented-binaries.md)|
|На странице **Взаимодействие уровней** добавьте данные вызова ADO.NET в сеанс профилировщика.|-   [Сбор данных о взаимодействии уровней](../profiling/collecting-tier-interaction-data.md)|
|На странице **Инструментирование** исключите профилирование небольших функций, чтобы уменьшить накладные расходы, связанные с профилированием, выполните профилирование кода JavaScript на веб-страницах ASP.NET и задайте команды, которые необходимо выполнить в командной строке перед началом процесса инструментирования и по его завершении.|-   [Практическое руководство. Исключение и включение малых функций при инструментировании](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Практическое руководство. Профилирование кода JavaScript в веб-страницах](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Практическое руководство. Указание команд, предваряющих инструментирование, и команд после инструментирования](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|
|На странице **Счетчики ЦП** выберите один или несколько счетчиков производительности процессора, значения которых будут добавляться в данные профилирования.|-   [Практическое руководство. Сбор данных счетчиков производительности ЦП](../profiling/how-to-collect-cpu-counter-data.md)|
|На странице **События Windows** выберите одно или несколько событий трассировки Windows, которые необходимо собирать с данными выборки.|-   [Практическое руководство. Сбор данных трассировки событий Windows](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|
|На странице **Счетчики Windows** выберите один или несколько счетчиков производительности операционной системы, значения которых будут добавляться в данные профилирования в качестве меток.|-   [Практическое руководство. Сбор данных счетчиков производительности Windows](../profiling/how-to-collect-windows-counter-data.md)|
|На странице **Дополнительно** задайте дополнительные параметры, которые необходимо передать в программу инструментирования VSInstr, например параметры для включения или исключения определенных функций.|-   [Практическое руководство. Определение дополнительных параметров инструментирования](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Практическое руководство. Ограничение инструментирования указанными функциями](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [VSInstr](../profiling/vsinstr.md)|