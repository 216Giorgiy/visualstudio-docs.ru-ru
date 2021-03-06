---
title: VSInstr | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- performance tools, instrumentation
- instrumentation, VSInstr tool
- profiling tools,VSInstr
- command-line tools, instrumentation
- command line, tools
- VSInstr
- VSInstr tool
- performance tools, VSInstr tool
ms.assetid: 7b1334f7-f9b0-4a82-a145-d0607bfa8467
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8af9195c0e9b36f804e16bd8903cfcfcd094032d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56633893"
---
# <a name="vsinstr"></a>VSInstr
Средство VSInstr используется для инструментирования двоичных файлов. Для его вызова используется следующий синтаксис:

```cmd
VSInstr [/U] filename [/options]
```

 В приведенной ниже таблице описываются параметры средства VSInstr.

|Параметры|Описание|
|-------------|-----------------|
|**Help** или **?**|Вывод справки.|
|**U**|Запись перенаправленного вывода на консоль в кодировке Юникода. Этот параметр необходимо указывать первым.|
|`@filename`|Указание имени файла ответов, который содержит один параметр команды на строку.  Не используйте кавычки.|
|**OutputPath** `:path`|Указание целевого каталога для инструментированного образа. Если путь целевого каталога не указывается, исходный двоичный файл переименовывается посредством добавления расширения ORIG к имени файла и сохраняется в том же каталоге. Инструментирование выполняется для копии двоичного файла.|
|**Exclude** `:funcspec`|Указание спецификации функции, которую требуется исключить из инструментирования посредством зондов. Этот параметр удобен, если вставка зондов профилирования в функцию приводит к непредсказуемым или нежелательным результатам.<br /><br /> Не используйте параметры **Exclude** и **Include**, относящиеся к функциям в одном двоичном файле.<br /><br /> С помощью отдельных параметров **Exclude** можно указать несколько спецификаций функций.<br /><br /> `funcspec` определяется следующим образом:<br /><br /> [пространство_имен\<разделитель1>] [класс\<разделитель2>]функция<br /><br /> \<разделитель1> — это `::` для машинного кода и `.` для управляемого кода.<br /><br /> \<разделитель2> — это всегда `::`<br /><br /> Параметр **Exclude** поддерживается с покрытием кода.<br /><br /> Поддерживается подстановочный знак \*. Например, чтобы исключить все функции в пространстве имен, используйте следующий синтаксис:<br /><br /> MyNamespace::\*<br /><br /> С помощью команды **VSInstr /DumpFuncs** можно составить список функций в заданном двоичном файле.|
|**Include** `:funcspec`|Задание спецификации функции в двоичном файле, которую требуется инструментировать посредством зондов. Для всех других функций в двоичных файлах инструментирование не выполняется.<br /><br /> С помощью отдельных параметров **Include** можно указать несколько спецификаций функций.<br /><br /> Не используйте параметры **Include** и **Exclude**, относящиеся к функциям в одном двоичном файле.<br /><br /> Параметр **Include** не поддерживается с покрытием кода.<br /><br /> `funcspec` определяется следующим образом:<br /><br /> [пространство_имен\<разделитель1>] [класс\<разделитель2>]функция<br /><br /> \<разделитель1> — это `::` для машинного кода и `.` для управляемого кода.<br /><br /> \<разделитель2> — это всегда `::`<br /><br /> Поддерживается подстановочный знак \*. Например, чтобы включить все функции в пространстве имен, используйте следующий синтаксис:<br /><br /> MyNamespace::\*<br /><br /> С помощью команды **VSInstr /DumpFuncs** можно составить список функций в заданном двоичном файле.|
|**DumpFuncs**|Создает список функций в указанном образе. Инструментирование не выполняется.|
|**ExcludeSmallFuncs**|Исключает из инструментирования малозначимые функции, то есть малые функции, которые не вызывают других функций. Параметр **ExcludeSmallFuncs** позволяет сократить временные затраты на инструментирование и таким образом повысить скорость инструментирования.<br /><br /> При исключении малозначимых функций также уменьшается размер *VSP*-файла и время, необходимое для анализа данных.|
|**Mark:**{**Before**`&#124;`**After**`&#124;`**Top**`&#124;`**Bottom**}`,funcname,markid`|Вставляет метку профилирования (идентификатор, используемый для разделения данных в отчете), которую можно использовать для определения начала и конца диапазона данных в VSP-файле отчета.<br /><br /> **Before** — непосредственно перед точкой входа целевой функции.<br /><br /> **After** — непосредственно после точки выхода целевой функции.<br /><br /> **Top** — непосредственно после точки входа целевой функции.<br /><br /> **Bottom** — непосредственно перед каждой точкой возврата из целевой функции.<br /><br /> `funcname` — имя целевой функции.<br /><br /> `Markid` — положительное целое число (типа long), используемое в качестве идентификатора метки профилирования.|
|**Coverage**|Выполняет инструментирование покрытия кода. Возможно использование только со следующими параметрами: **Verbose**, **OutputPath**, **Exclude** и **Logfile**.|
|**Verbose**|Параметр **Verbose** используется для просмотра подробных сведений о процессе инструментирования.|
|**NoWarn** `[:[Message Number[;Message Number]]]`|Не выводить все или указанные предупреждения.<br /><br /> `Message Number` — номер предупреждения. Если значение `Message Number` не указано, запрещается вывод всех предупреждений.<br /><br /> Дополнительные сведения см. в разделе [Предупреждения средства VSInstr](../profiling/vsinstr-warnings.md).|
|**Control** `:{` **Thread** `&#124;` **Process** `&#124;` **Global** `}`|Задает уровень профилирования для следующих параметров управления сбором данных VSInstr:<br /><br /> **Start**<br /><br /> **StartOnly**<br /><br /> **Suspend**<br /><br /> **StopOnly**<br /><br /> **SuspendOnly**<br /><br /> **ResumeOnly**<br /><br /> **Thread** — указывает для функций управления сбором данных уровень потока. Профилирование запускается и останавливается только для текущего потока. Состояние профилирования других потоков не изменяется. THREAD является значением по умолчанию.<br /><br /> **Process** — указывает для функций управления сбором данных уровень процесса. Профилирование запускается и останавливается для всех потоков в текущем процессе. Состояние профилирования других процессов не изменяется.<br /><br /> **Global** — указывает для функций управления сбором данных глобальный уровень (межпроцессный).<br /><br /> Если уровень профилирования не задан, возникает ошибка.|
|**Start** `:{` **Inside** `&#124;` **Outside** `},funcname`|Ограничивает собираемые данные целевой функцией и дочерними функциями, вызываемыми этой функцией.<br /><br /> **Inside** — функция StartProfile вставляется непосредственно после точки входа в целевую функцию. Функция StopProfile вставляется непосредственно перед каждой точкой передачи управления из целевой функции.<br /><br /> **Outside** — функция StartProfile вставляется непосредственно перед каждым вызовом целевой функции. Функция StopProfile вставляется непосредственно после каждого вызова целевой функции.<br /><br /> `funcname` — имя целевой функции.|
|**Suspend** `:{` **Inside** `&#124;` **Outside** `},funcname`|Исключает сбор данных для целевой функции и дочерних функций, вызываемых этой функцией.<br /><br /> **Inside** — функция SuspendProfile вставляется непосредственно после точки входа в целевую функцию. Функция ResumeProfile вставляется непосредственно перед каждой точкой передачи управления из целевой функции.<br /><br /> **Outside** — функция SuspendProfile вставляется непосредственно перед точкой входа в целевую функцию. Функция ResumeProfile вставляется непосредственно после точки выхода из целевой функции.<br /><br /> `funcname` — имя целевой функции.<br /><br /> Если целевая функция содержит функцию StartProfile, функция SuspendProfile вставляется перед ней. Если целевая функция содержит функцию StopProfile, функция ResumeProfile вставляется после нее.|
|**StartOnly:** `{` **Before** `&#124;` **After** `&#124;` **Top** `&#124;` **Bottom** `},funcname`|Начинает сбор данных в ходе сеанса профилирования. При этом в указанном расположении вставляется API-функция StartProfile.<br /><br /> **Before** — непосредственно перед точкой входа целевой функции.<br /><br /> **After** — непосредственно после точки выхода целевой функции.<br /><br /> **Top** — непосредственно после точки входа целевой функции.<br /><br /> **Bottom** — непосредственно перед каждой точкой возврата из целевой функции.<br /><br /> `funcname` — имя целевой функции.|
|**StopOnly:**{**Before**`&#124;`**After**`&#124;`**Top**`&#124;`**Bottom**}`,funcname`|Прекращает сбор данных в ходе сеанса профилирования. При этом в указанном расположении вставляется функция StopProfile.<br /><br /> **Before** — непосредственно перед точкой входа целевой функции.<br /><br /> **After** — непосредственно после точки выхода целевой функции.<br /><br /> **Top** — непосредственно после точки входа целевой функции.<br /><br /> **Bottom** — непосредственно перед каждой точкой возврата из целевой функции.<br /><br /> `funcname` — имя целевой функции.|
|**SuspendOnly:**{**Before**`&#124;`**After**`&#124;`**Top**`&#124;`**Bottom**}`,funcname`|Прекращает сбор данных в ходе сеанса профилирования. При этом в указанном расположении вставляется API-функция SuspendProfile.<br /><br /> **Before** — непосредственно перед точкой входа целевой функции.<br /><br /> **After** — непосредственно после точки выхода целевой функции.<br /><br /> **Top** — непосредственно после точки входа целевой функции.<br /><br /> **Bottom** — непосредственно перед каждой точкой возврата из целевой функции.<br /><br /> `funcname` — имя целевой функции.<br /><br /> Если целевая функция содержит функцию StartProfile, функция SuspendProfile вставляется перед ней.|
|**ResumeOnly:**{**Before**`&#124;`**After**`&#124;`**Top**`&#124;`**Bottom**}`,funcname`|Начинает или возобновляет сбор данных в ходе сеанса профилирования.<br /><br /> Обычно используется для возобновления профилирования после его приостановки с помощью параметра **SuspendOnly**. При этом в указанном расположении вставляется API-функция ResumeProfile.<br /><br /> **Before** — непосредственно перед точкой входа целевой функции.<br /><br /> **After** — непосредственно после точки выхода целевой функции.<br /><br /> **Top** — непосредственно после точки входа целевой функции.<br /><br /> **Bottom** — непосредственно перед каждой точкой возврата из целевой функции.<br /><br /> `funcname` — имя целевой функции.<br /><br /> Если целевая функция содержит функцию StopProfile, функция ResumeProfile вставляется после нее.|

## <a name="see-also"></a>См. также
- [VSPerfMon](../profiling/vsperfmon.md)
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [VSPerfReport](../profiling/vsperfreport.md)
- [Предупреждения средства VSInstr](../profiling/vsinstr-warnings.md)
- [Представления отчетов о производительности](../profiling/performance-report-views.md)