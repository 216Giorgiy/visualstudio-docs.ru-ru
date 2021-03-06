---
title: Общие сведения о значениях данных инструментирования | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,instrumentation
- instrumentation profiling method
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f10a3f434def1c96c2f096c4b299b47dd8aad9f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56620777"
---
# <a name="understand-instrumentation-data-values"></a>Общие сведения о значениях данных инструментирования

При профилировании с использованием *инструментированием* в Visual Studio записываются подробные сведения о времени для вызовов функций, строках и инструкциях в профилируемом приложении.

Метод инструментирования предусматривает вставку кода в начало и конец целевых функций профилируемого двоичного файла, а также до и после каждого вызова других функций из целевых. Вставленный код регистрирует следующую информацию:

- интервал между этим событием сбора и предыдущим;

- выполняла ли операционная система какие-либо операции в течение интервала. Например, операционная система могла выполнять чтение с диска или запись на диск либо переключаться с целевого потока на поток в другом процессе.

Для каждого из интервалов средства анализа профилировщика воссоздают стек вызовов на момент завершения интервала. Стек вызовов — это список функций, активных в процессоре на определенный момент времени. Выполняется код только одной функции (текущей функции); другие функции представляют собой цепочку вызовов функций, которая привела к вызову текущей функции (стек вызовов).

Для каждой из функций в стеке вызовов на момент регистрации интервала средства анализа профилировщика добавляют интервал к одному или нескольким из четырех значений данных функции. Средства анализа добавляют интервал к значению данных функции с учетом двух критериев.

- Произошел ли интервал в коде функции или в коде *дочерней функции* (функции, которая была вызвана данной функцией).

- Произошло ли в интервале событие операционной системы.

Значения данных для интервала функции или диапазона данных называются *Затраченное инклюзивное время*, *Затраченное эксклюзивное время*, *Инклюзивное время приложения* и *Эксклюзивное время приложения*.

- Все интервалы функции добавляются к значению затраченного инклюзивного времени.

- Если интервал произошел в коде функции, а не в коде дочерней функции, этот интервал добавляется к значению затраченного эксклюзивного времени для функции.

- Если в течение интервала не происходило событий операционной системы, этот интервал добавляется к значению инклюзивного времени приложения.

- Если в течение интервала не происходило событий операционной системы и интервал произошел в ходе выполнения кода функции (то есть не произошел в коде дочерней функции), этот интервал добавляется к значению эксклюзивного времени приложения.

В отчетах средств профилирования указываются совокупные значения показателей функций в ходе сеанса профилирования, а также в рамках процессов, потоков и двоичных файлов, которые использовались в ходе сеанса.

## <a name="elapsed-inclusive-values"></a>Затраченное инклюзивное время

Общее время, которое было затрачено на выполнение функции и ее дочерних функций.

Значения затраченного инклюзивного времени отражают интервалы, затраченные на выполнение кода самой функции, и интервалы, затраченные на выполнение дочерних функций целевой функции. Интервалы функции или ее дочерних функций, в течение которых происходило ожидание операционной системы, также учитываются в значении затраченного инклюзивного времени.

## <a name="elapsed-exclusive-values"></a>Затраченное эксклюзивное время

Общее время, которое было затрачено на выполнение функции, исключая время выполнения ее дочерних функций.

Значения затраченного эксклюзивного времени отражают интервалы, затраченные на выполнение кода самой функции, независимо от того, происходили ли в течение интервала события операционной системы. Значения затраченного инклюзивного времени не учитывают интервалы, затраченные на выполнение кода дочерних функций целевой функции.

## <a name="application-inclusive-values"></a>Инклюзивное время приложения

Общее время, которое было затрачено на выполнение функции и ее дочерних функций, исключая время обработки событий операционной системы.

В значениях инклюзивного времени приложения не учитываются интервалы, затраченные на обработку событий операционной системы. Значения инклюзивного времени приложения отражают все остальные интервалы, затраченные на выполнение кода функции, независимо от того, были эти интервалы затрачены на выполнение кода самой функции или кода дочерних функций целевой функции.

## <a name="application-exclusive-values"></a>Эксклюзивное время приложения

Время, которое было затрачено на выполнение кода функции, исключая время, затраченное на выполнение кода ее дочерних функций и обработку событий операционной системы.

Значения эксклюзивного времени приложения не отражают интервалы, затраченные на обработку событий операционной системы, и интервалы, затраченные на выполнение функций, вызванных целевой функцией. Значения эксклюзивного времени приложения отражают только те интервалы, которые были затрачены на выполнение кода самой функции, и не отражают интервалы, затраченные на обработку событий операционной системы.

## <a name="elapsed-inclusive-percent"></a>Затраченное инклюзивное время (в процентах)

Процентная доля значений затраченного инклюзивного времени в рамках сеанса профилирования, включая значения затраченного инклюзивного времени для функции, модуля, потока или процесса.

100 * затраченное инклюзивное время для функции / затраченное инклюзивное время сеанса

## <a name="elapsed-exclusive-percent"></a>Затраченное эксклюзивное время (в процентах)

Процентная доля значений затраченного инклюзивного времени в рамках сеанса профилирования, включая значения затраченного эксклюзивного времени для функции, модуля, потока или процесса.

100 * затраченное эксклюзивное время для функции / затраченное инклюзивное время сеанса

## <a name="application-inclusive-percent"></a>Инклюзивное время приложения (в процентах)

Процентная доля значений инклюзивного времени приложения в рамках сеанса профилирования, включая значения инклюзивного времени приложения для функции, модуля, потока или процесса.

100 * инклюзивное время приложения для функции / инклюзивное время приложения сеанса

## <a name="application-exclusive-percent"></a>Эксклюзивное время приложения (в процентах)

Процентная доля значений инклюзивного времени приложения в рамках сеанса профилирования, включая значения эксклюзивного времени приложения для функции, модуля, потока или процесса.

100 * эксклюзивное время приложения для функции / инклюзивное время приложения сеанса

## <a name="see-also"></a>См. также

[Анализ данных из средств оценки производительности](../profiling/analyzing-performance-tools-data.md)
[Практическое руководство. Выбор методов сбора данных](../profiling/how-to-choose-collection-methods.md)