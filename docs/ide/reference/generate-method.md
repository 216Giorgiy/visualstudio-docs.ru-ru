---
title: Создание метода
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: d815b638033e16796c90a362207b820bfe7cc57d
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55933526"
---
# <a name="generate-a-method-in-visual-studio"></a>Создание метода в Visual Studio

Область применения этого формирования кода:

- C#

- Visual Basic

**Что?** Позволяет немедленно добавить метод в класс.

**Когда?** Вы представляете новый метод и хотите правильно его объявить автоматически.

**Зачем?** Вы можете объявить метод и параметры перед их использованием, но эта функция позволяет создать объявление автоматически.

## <a name="how-to"></a>Практические советы

1. Поместите курсор в строку с красной волнистой линией. Она указывает пока несуществующий метод.

   - C#:

       ![Выделенный код C#](media/method-highlight-cs.png)

   - Visual Basic:

       ![Выделенный код VB](media/method-highlight-vb.png)

2. Затем выполните одно из следующих действий:

   - **Клавиатура**
      - Нажмите клавиши **CTRL**+**.** чтобы открыть меню **Быстрые действия и рефакторинг**.
   - **Мышь**
      - Щелкните правой кнопкой мыши и выберите меню **Быстрые действия и рефакторинг**.
      - Наведите указатель мыши на красную волнистую линию и щелкните появившийся значок ![лампочка с ошибкой](media/error-bulb.png) , который отображается.
      - Нажмите кнопку ![лампочка с ошибкой](media/error-bulb.png) , который отображается в левом поле, если текстовый курсор уже находится в строке выбора с красной волнистой линией.

      ![Создание метода — предварительный просмотр](media/method-preview-cs.png)

3. Выберите **Создать метод** в раскрывающемся меню.

   > [!TIP]
   > Щелкните ссылку **Просмотреть изменения** в нижней части окна предварительного просмотра, [чтобы просмотреть все будущие изменения](../../ide/preview-changes.md), прежде чем выбрать элементы.

   Метод создается со всеми параметрами, выведенными из его использования.

   - C#:

       ![Результат создания метода C#](media/method-result-cs.png)

   - Visual Basic:

       ![Результат создания метода VB](media/method-result-vb.png)

## <a name="see-also"></a>См. также

- [Создание кода](../code-generation-in-visual-studio.md)
- [Просмотр изменений](../../ide/preview-changes.md)