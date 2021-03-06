---
title: Анализ кода R
description: Работа со встроенной поддержкой анализа данных для R в Visual Studio, в том числе параметры анализа.
ms.date: 07/02/2018
ms.topic: conceptual
f1_keywords:
- vs.toolsoptionspages.text_editor.r.lint
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: aecf9d95fb8a3b2cda659e2694bff145424e150b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55920474"
---
# <a name="lint-r-code-in-visual-studio"></a>Анализ кода R в Visual Studio

Анализатор кода позволяет обнаружить потенциальные ошибки, а также проблемы форматирования и другой шум в файлах кода, например ненужное пустое пространство. Кроме того, использование анализатора кода помогает установить определенные соглашения по написанию кода, например соглашения, касающиеся имен идентификаторов. Такие соглашения полезны при реализации командного проекта и в других ситуациях, когда требуется совместная работа.

Инструменты R для Visual Studio (RTVS) включают встроенные возможности анализа кода R с разнообразными параметрами для их настройки, описанными в этой статье. Эти параметры находятся в разделе **Инструменты** > **Параметры** > **Текстовый редактор** > **R** > **Анализ кода**.

По умолчанию анализ кода отключен. Чтобы включить его, задайте для параметра **Все** > **Включить анализ кода** значение **True**.

Если этот параметр включен, анализ кода применяется в редакторе по мере ввода. Проблемы подчеркиваются зеленой волнистой линией. Например, на следующем рисунке RTVS выявил шесть проблем при анализе кода, в том числе использование `=` вместо `<-` для присваивания, нехватку пробелов вокруг аргументов функции, использование регистра Pascal, написание идентификаторов целиком прописными буквами, а также использование точки с запятой. Наведите указатель мыши на проблему, чтобы увидеть описание.

![Примеры выходных данных анализатора кода для кода R](media/linting-01.png)

Вы можете часто изменять параметры анализатора кода в соответствии с требованиями проекта или файла. Например, в примере кода из Интернет-курса может использоваться `=` вместо `<-` вместе с идентификаторами в стиле Pascal. Для такого кода будут отображаться частые предупреждения анализатора о найденных ошибках, так как это флаги для параметров анализатора по умолчанию. Во время работы с этим кодом можно отключить такие параметры, чтобы не тратить время на исправление каждого вхождения.

## <a name="assignment-group"></a>Группа присваивания

| Параметр | Значение по умолчанию | Результат анализа кода |
| --- | --- | --- |
| **Принудительное использование \<-** | **True** | Определяет, когда `<-` не используется для присваивания. |

## <a name="naming-group"></a>Группа именования

Эти параметры помечают идентификаторы, не использующие принятые соглашения об именовании:

| Параметр | Значение по умолчанию | Результат анализа кода |
| --- | --- | --- |
| **Помечать camelCase** | **False** | Помечает идентификаторы, использующие camelCase. |
| **Помечать длинные имена** | **False** | Помечает идентификаторы, имена которых превышают значение параметра **Максимальная длина имени**. |
| **Помечать многоточия** | **True** | Помечает идентификаторы, использующие многоточия. |
| **Помечать PascalCase** | **True** | Помечает идентификаторы, использующие PascalCase. |
| **Помечать snake_case** | **False** | Помечает идентификаторы, использующие символы подчеркивания. |
| **Помечать ПРОПИСНЫЕ** | **True** | Помечает идентификаторы, целиком написанные прописными буквами. |
| **Максимальная длина имени** | **32** | Длина для параметра **Помечать длинные имена**. |

## <a name="spacing-group"></a>Группа пробелов

Все эти параметры по умолчанию имеют значение **True**. Они позволяют настроить в коде анализ проблем с пробелами: пробелы после имен функций, вокруг запятых, вокруг операторов, положение открывающих и закрывающих фигурных скобок, пробел перед "(" и внутри "()".

## <a name="statements-group"></a>Группа операторов

| Параметр | Значение по умолчанию | Результат анализа кода |
| --- | --- | --- |
| **Несколько** | **True** | Выявляет, когда на одной строке находится множество операторов. |
| **Точки с запятой** | **True** | Выявляет использование точек с запятой. |

## <a name="text-group"></a>Группа текста

| Параметр | Значение по умолчанию | Результат анализа кода |
| --- | --- | --- |
| **Ограничение длины строки** | **False** | Указывает, должен ли анализатор кода помечать строки, длина которых превышает значение параметра **Максимальная длина строки**. |
| **Максимальная длина строки** | **80** | Задает длину строки для параметра **Ограничение длины строки**. |

## <a name="whitespace-group"></a>Группа пустого пространства

Все эти параметры по умолчанию имеют значение **True**. Они позволяют настроить в коде анализ проблем с пустым пространством: использование табуляции и двойных кавычек, пустые строки в конце и пробелы в конце.