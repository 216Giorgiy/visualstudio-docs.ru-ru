---
title: 'Конструктор рабочих процессов - как: выполнить отладку XAML в конструкторе рабочих процессов'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: cdbf5fa21c8fcf9069db9a7348d4ed576fc342c5
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065887"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Практическое руководство. выполнить отладку XAML в конструкторе рабочих процессов

Рабочие процессы определены в терминах XAML. Представление пользовательского интерфейса рабочего процесса построено на основе дерева XAML, определяющего рабочий процесс. Процесс отладки аналогична отладке рабочих процессов в конструкторе рабочих процессов. Например при отладке XAML, локальные переменные, Контрольные значения и потоков windows работать так же, как в конструкторе рабочих процессов отладки. Помимо этого, представление стека вызовов при отладке XAML является линейным иерархическим представлением потока выполнения для рабочего процесса.

> [!NOTE]
> Если код языка XAML для рабочего процесса расположен в той же сборке, что и действия, часть имен классов, относящихся к сборке, не включается. Без этой части имен класса (действия) код языка XAML не может быть загружен во время выполнения. Не рекомендуется определять действия в том же пространстве имен, что и основной проект; в противном случае код языка XAML необходимо изменить вручную после изменения в конструкторе.

## <a name="to-debug-workflow-xaml"></a>Отладка рабочего процесса XAML

1. Откройте проект рабочего процесса или действия в Visual Studio.

2. Установите точку останова в действии, необходимо выполнить отладку, как описано в разделе [как: Установите точки останова в рабочих процессах](../workflow-designer/how-to-set-breakpoints-in-workflows.md).

3. Щелкните правой кнопкой мыши XAML-файл, содержащий определение рабочего процесса и выберите **Просмотр кода**. Будет отображена точка останова на той же строке, что и объявление элемента XAML действия, где была установлена точка останова в режиме конструктора.

4. Вызовите отладчик, как описано в разделе [отладки рабочих процессов](debugging-workflows-with-the-workflow-designer.md).

5. Когда выполнение кода достигнет одной из заданных точек останова, то элемент XAML, связанный с этой точкой останова, будет выделен. Для перемещения к следующей точке останова, используйте **F10** или **F11** ключ.

## <a name="see-also"></a>См. также

- [Практическое руководство. Задание точек останова в рабочих процессах](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Отладка рабочих процессов](debugging-workflows-with-the-workflow-designer.md)