---
title: Управление видимостью значка или декоратора
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7cfe6ce02b03ed69435f8056ccd340b92f9eb5a4
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60046283"
---
# <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Управление видимостью значка или декоратора
Объект *декоратор* значок или строку текста, который отображается на фигуре в доменный язык (DSL). Можно внести декоратора отображаются и исчезают в зависимости от состояния свойства в модели. Например в форму, представляющую человека, можно создать различные значки, которые отображаются в зависимости от пола человека, число дочерних объектов и т. д.

## <a name="controlling-the-visibility-of-an-icon-or-decorator"></a>Управление видимостью значка или декоратора
 В следующей процедуре предполагается, что уже определена фигуры и его сопоставление с классом домена. Дополнительные сведения см. в разделе [способ определения доменного языка](../modeling/how-to-define-a-domain-specific-language.md).

#### <a name="to-control-the-visibility-of-an-icon-or-text-decorator"></a>Для управления видимостью декоратора значка или текста

1. В схеме определения DSL добавьте в класс фигуры, значки или декораторов текста, которые нужно отобразить.

   1. Щелкните правой кнопкой мыши фигуру класса, выберите пункт **добавить**и выберите требуемый тип класса decorator.

   2. Задайте декоратор **позиции** свойство. Несколько декораторов может иметь ту же позицию. Например может иметь значки для мужчин и женщин, общий доступ к той же позиции.

   3. Задайте **значок по умолчанию** свойство декоратор значок.

2. Выберите карту элементов схемы, который является серую линию между классом фигуры и классом домена в схеме определения DSL.

3. В окне сведения о DSL в **сопоставления декораторов** выберите декоратор. Например MaleDecorator.

4. Проверьте **фильтр видимости** поле.

5. Если свойство домена, который должен управлять видимостью в классе домена немедленно, оставьте **путь к свойству фильтра** пустым.

    В противном случае щелкните стрелку раскрывающегося меню и перейдите к связи или класса, где находится свойство.

   - Чтобы избежать отчет об ошибке, следует не перемещаться по связи с «*» в средстве навигации.

6. Задайте **свойство фильтра** свойству домена. Например пол.

7. В **записи видимости** добавьте значения этого свойства домена, для которого должны быть видимыми декоратора. Например, Мужской.

8. Повторите шаги для каждого значка.

9. **Преобразовать все шаблоны**, построения и запуска и открыть диаграммы тестирования.

10. При изменении значения свойства управления декораторы следует появляются и исчезают.

    Часто требуется видимость управляются более сложная формула, чем простой набор значений. Например появится значок зависят от числа ссылок определенного типа или сделать его зависят от того число-к определенному диапазону. В этом случае используйте следующую процедуру.

#### <a name="to-control-the-visibility-of-a-decorator-based-on-a-formula"></a>Для управления видимостью декоратора на основе формулы

1. Добавьте в класс домена рассчитываемое свойство домена. В **свойства** окна, задайте следующие значения:

     **IsBrowsable =**`False`**-это скрывает свойство от пользователя**

     **Тип =**`Calculated`**-это означает, что будет предоставлять код, который вычисляет его значение**

     **Имя** например **DecoratorControl**

     **Тип** = `Boolean`

     Дополнительные сведения см. в разделе [вычисляемые и пользовательские свойства хранилища](../modeling/calculated-and-custom-storage-properties.md).

2. Сделайте свойство управлять видимостью декоратора.

    1. Выберите карту элементов схемы, которой это серая линия из доменного класса на фигуру. В **подробные сведения о DSL** открытое окно **DecoratorMap** вкладки.

    2. Проверьте **фильтр видимости** поле.

    3. В **свойство фильтра**, выберите свойство элемента управления **DecoratorControl**.

    4. В разделе **записи видимости**, введите `True`.

3. Нажмите кнопку **преобразовать все шаблоны** в **обозревателе решений** панели инструментов.

4. Нажмите кнопку **построить решение** на **построения** меню.

5. Дважды щелкните отчет об ошибке, которое отображается: "*Вашкласс* содержит определения для GetDecoratorControlValue...».

     Откроется редактор текста на Dsl\GeneratedCode\DomainClasses.cs. Выше выделенную ошибку, комментарий, который запрашивает, следует добавить метод.

6. Обратите внимание на то, пространство имен, класс и метод, отсутствуют.  Например, Company.FamilyTree.Person.GetDecoratorControlValue().

7. В отдельном файле кода напишете определение разделяемого класса, содержащего метод отсутствует. Пример:

    ```
    namespace Company.FamilyTree
    { partial class Person
      { bool GetDecoratorControlValue()
        {
          return this.Children.Count > 0;
    } } }
    ```

     Дополнительные сведения о настройке модели с помощью программного кода, см. в разделе [перехода и обновления модели в программном коде](../modeling/navigating-and-updating-a-model-in-program-code.md).

8. Заново собрать и запустить решение.

## <a name="see-also"></a>См. также

- [Определение фигур и соединителей](../modeling/defining-shapes-and-connectors.md)
- [Задание фонового изображения схемы](../modeling/setting-a-background-image-on-a-diagram.md)
- [Перемещение по модели и обновление модели в коде программы](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Написание кода для настройки доменного языка](../modeling/writing-code-to-customise-a-domain-specific-language.md)