---
title: Экспорт результатов нагрузочных тестов
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load tests, exporting results
- Load Test Results Repository
- load test results, exporting
ms.assetid: 716c2af5-8737-4d31-956f-a0273f7c5c0c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7bc496c4f6a445ffd43e992302457bdb92f3239a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55949867"
---
# <a name="how-to-export-load-test-results-from-a-repository"></a>Как выполнить  экспорт результатов нагрузочного тестирования из репозитория

При выполнении нагрузочного теста данные, собранные во время тестового запуска, сохраняются в репозитории результатов нагрузочных тестов. В репозитории результатов нагрузочных тестов содержатся данные счетчиков производительности и сведения о всех ошибках. Дополнительные сведения см. в статье [Управление результатами нагрузочного теста в репозитории результатов нагрузочного теста](../test/manage-load-test-results-in-the-load-test-results-repository.md).

Управление результатами нагрузочных тестов осуществляется в редакторе тестовой нагрузки с помощью диалогового окна **Открытие и обработка результатов нагрузочных тестов**. Результаты нагрузочных тестов можно открывать, импортировать, экспортировать и удалять.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-export-results-from-a-repository"></a>Чтобы экспортировать результаты из репозитория

1.  Из проекта веб-тестов производительности и нагрузочных тестов откройте нагрузочный тест.

2.  На встроенной панели инструментов нажмите кнопку **Открытие и управление результатами**.

     Откроется диалоговое окно **Открытие и обработка результатов нагрузочных тестов**.

3.  В поле **Введите имя контроллера для поиска результатов нагрузочных тестов** выберите контроллер. Выберите **\<Локальный> — Без контроллера>**, чтобы открыть результаты, сохраненные локально.

4.  В поле **Показать результаты следующего нагрузочного теста** выберите нагрузочный тест, результаты которого требуется просмотреть. Для просмотра всех результатов всех тестов выберите команду **\<Показать результаты для всех тестов>**.

     Если доступны результаты нагрузочного теста, они отображаются в списке **Результаты нагрузочного теста**. В этом списке содержатся столбцы **Время**, **Длительность**, **Пользователь**, **Выходной результат**, **Тест** и **Описание**. В столбце **Тест** отображается имя теста, а в столбце **Описание** — необязательное описание, добавленное перед запуском теста. В столбце **Описание** содержится краткое описание, введенное в области **Примечания к анализу** для данного результата.

5.  Выберите результат в списке **Результаты нагрузочного теста**. Чтобы выбрать несколько результатов и экспортировать их в один файл, используйте клавишу **SHIFT**, клавишу **CTRL** или обе эти клавиши.

6.  Выберите пункт **Экспорт**.

     Будет открыто диалоговое окно **Результаты экспорта нагрузочных тестов**.

7.  В поле **Имя файла** введите имя и нажмите кнопку **Сохранить**.

     Результаты экспортируются в архивный файл.

    > [!NOTE]
    > После появления результатов диалоговое окно **Открытие и обработка результатов нагрузочных тестов** остается открытым.

## <a name="see-also"></a>См. также

- [Управление результатами нагрузочного теста в репозитории результатов нагрузочного теста](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Практическое руководство. удаление результатов нагрузочного тестирования из репозитория](../test/how-to-delete-load-test-results-from-a-repository.md)
- [Анализ результатов нагрузочных тестов](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Практическое руководство. импорт результатов нагрузочного тестирования в репозиторий](../test/how-to-import-load-test-results-into-a-repository.md)