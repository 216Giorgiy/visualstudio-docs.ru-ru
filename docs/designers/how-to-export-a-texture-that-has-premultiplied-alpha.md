---
title: Как выполнить  Экспорт текстуры с предварительным умножением альфа-канала
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 05348afa-f079-4f53-a05b-ecd91d13adab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9a228b3f69730eee5fb1672e07a6eea74d18c71e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946877"
---
# <a name="how-to-export-a-texture-that-has-premultiplied-alpha"></a>Как выполнить  Экспорт текстуры с предварительным умножением альфа-канала

Конвейер содержимого изображения может генерировать из исходного изображения предварительно умноженные альфа-текстуры. Они намного проще в использовании и более стабильные, чем текстуры, которые не содержат предварительное умноженный альфа-канал.

В этом документе описаны следующие действия.

-   Настройка исходного изображения для обработки в конвейере содержимого изображения.

-   Настройка конвейера содержимого изображения для формирования предварительно умноженного альфа-канала.

## <a name="premultiplied-alpha"></a>Предварительно умноженный альфа-канал
 Предварительно умноженный альфа-канал обладает рядом преимуществ по сравнению с обычным альфа-каналом, который предварительно не умножен, поскольку он лучше представляет реальное взаимодействие света с физическими материалами, разделяя вклад пикселя текстуры в цвет (цвет, который он добавляет в сцену) от его полупрозрачности (объем основного цвета, который проходит через него). Ниже приведены некоторые преимущества использования предварительно умноженного альфа-канала.

-   Наложение предварительно умноженного альфа-канала представляет собой ассоциативную операцию; результат наложения друг на друга нескольких полупрозрачных текстур один и тот же, независимо от порядка их наложения.

-   Ввиду ассоциативной природы наложения предварительно умноженного альфа-канала упрощается многопроходный рендеринг прозрачных объектов.

-   С помощью предварительно умноженного альфа-канала и чисто аддитивное наложение (путем задания значения альфа-канала равным нулю), и наложение с линейной интерполяцией можно выполнять одновременно. Например, в системе частиц аддитивно наложенная частица огня может стать полупрозрачной частицей дыма, для наложения которой используется линейная интерполяция. Без предварительно умноженного альфа-канала частицы огня потребовалось бы нарисовать отдельно от частиц дыма, а затем изменить состояния отрисовки между вызовами Draw.

-   Сжатие текстур с предварительно умноженным альфа-каналом выполняется с более высоким качеством, чем текстур, в которых он не используется, и в них не наблюдается обесцвечивание краев (или эффекта ореола), которое может возникнуть при наложении текстур, в которых не используются предварительно умноженные альфа-каналы.

#### <a name="to-create-a-texture-that-uses-premultiplied-alpha"></a>Создание текстуры с предварительно умноженным альфа-каналом

1. Сначала создайте простейшую текстуру. Загрузите существующий файл изображения или создайте его, как описано в разделе [Практическое руководство. Создание простейшей текстуры](../designers/how-to-create-a-basic-texture.md).

2. Настройте файл текстуры так, чтобы он обрабатывался конвейером содержимого изображения. В области **Обозреватель решений** откройте контекстное меню файла текстуры и выберите **Свойства**. На странице **Свойства конфигурации** > **Общие** задайте для свойства **Тип элемента** значение **Конвейер содержимого изображения**. Убедитесь, что свойство **Содержимое** имеет значение **Да**, а свойство **Исключить из сборки** — значение **Нет**, а затем нажмите кнопку **Применить**. Откроется страница свойств конфигурации **конвейера содержимого изображения**.

3. Настройте конвейер содержимого изображения для формирования предварительно умноженного альфа-канала. На странице **Свойства конфигурации** > **Конвейер содержимого изображения** > **Общие** установите для свойства **Преобразование в формат с предварительным умножением альфа-канала** значение **Да (/generatepremultipliedalpha)**.

4. Нажмите кнопку **ОК** .

   Когда выполняется сборка проекта, конвейер содержимого изображения преобразует исходное изображение из рабочего формата в указанный вами выходной формат (в том числе создает предварительно умноженный альфа-канал) и сохраняет результат в выходной каталог проекта.