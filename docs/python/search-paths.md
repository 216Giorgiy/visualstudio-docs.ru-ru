---
title: Как используются пути поиска Python
description: В Visual Studio реализованы более конкретные способы указания путей поиска для сред и проектов, позволяющие избежать использования переменных уровня системы.
ms.date: 03/13/2019
ms.topic: conceptual
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 37ce9d7b1853dfecc9e0ec33ca08c3c3fa0571e0
ms.sourcegitcommit: 0e22ead8234b2c4467bcd0dc047b4ac5fb39b977
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59365344"
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Как пути поиска Python используются в Visual Studio

При стандартном использовании Python переменная среды `PYTHONPATH` (или `IRONPYTHONPATH` и т. д.) предоставляет путь поиска по умолчанию для файлов модулей. То есть, когда вы используете инструкцию `from <name> import...` или `import <name>`, в Python выполняется поиск совпадающего имени в следующих расположениях в указанном порядке:

1. Встроенные модули Python.
1. Папка с кодом Python, который вы используете.
1. Расположение по пути поиска модуля, определенное в переменной среды. (См. сведения в разделах о [пути поиска модуля](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) и [переменных среды](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) в основной документации Python.)

Тем не менее Visual Studio игнорирует переменную среды для пути поиска, даже если она задана для всей системы. На самом деле она не учитывается именно *из-за* того, что задана для всей системы, так как в этом случае возникают некоторые вопросы, на которые нельзя ответить автоматически: для какого окружения предназначены указанные модули — для Python 2.7 или Python 3.6+? нужно ли переопределять стандартные модули библиотеки и знает ли разработчик о подобном поведении или это попытка атаки.

Таким образом, в Visual Studio можно напрямую указать пути поиска как в окружениях, так и в проектах. Код, который выполняется или отлаживается в Visual Studio, получает пути поиска из переменной `PYTHONPATH` (и других ее аналогов). Если вы добавляете пути поиска, Visual Studio проверяет библиотеки в этих расположениях и при необходимости создает для них базы данных IntelliSense (Visual Studio 2017 версии 15.5 и более ранних версий; это может занять некоторое время в зависимости от числа библиотек).

Чтобы добавить путь поиска, в **обозревателе решений** разверните узел проекта, щелкните правой кнопкой мыши элемент **Пути поиска** и выберите **Добавить папку для пути поиска**.

::: moniker range="vs-2017"
![Команда "Добавить папку в путь поиска" для параметра "Пути поиска" в обозревателе решений](media/search-paths-command.png)
::: moniker-end
::: moniker range=">=vs-2019"
![Команда "Добавить папку в путь поиска" для параметра "Пути поиска" в обозревателе решений](media/search-paths-command-2019.png)
::: moniker-end

Эта команда отображает браузер, в котором можно выбрать включаемую папку.

Если ваша переменная среды `PYTHONPATH` уже включает в себя требуемые папки, для ускорения процесса используйте команду **Добавить PYTHONPATH в путь поиска**.

После добавления папок в пути поиска Visual Studio использует эти пути для любой среды, связанной с проектом. (Если окружение создано на основе Python 3, может произойти ошибка при попытке добавить путь поиска для модулей Python 2.7.)

Файлы с расширением *ZIP* или *EGG* также можно добавить в качестве путей поиска. Для этого нужно выбрать **Добавить ZIP-архив в путь поиска**. Как и при использовании папок, содержимое этих файлов проверяется и предоставляется для IntelliSense.

## <a name="see-also"></a>См. также

- [Управление окружениями Python в Visual Studio](managing-python-environments-in-visual-studio.md)
- [Выбор интерпретатора для проекта](selecting-a-python-environment-for-a-project.md)
- [Использование файла requirements.txt для зависимостей](managing-required-packages-with-requirements-txt.md)
- [Справочная информация по вкладкам окна "Окружения Python"](python-environments-window-tab-reference.md)
