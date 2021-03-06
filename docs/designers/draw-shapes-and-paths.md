---
title: Рисование фигур и контуров
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d5378c59-e2e5-49f0-91f1-aa82d984a33c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bc629f44ed39fb07459916f07ef430f87b00e14a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918888"
---
# <a name="draw-shapes-and-paths"></a>Рисование фигур и контуров

В конструкторе XAML *фигура* — это именно тот объект, который соответствует вашим представлениям. Например, прямоугольник, круг или эллипс. Объект *контур* является более универсальной версией фигуры. Можно, например, изменить эти объекты или объединить их в форме новых фигур.

Для фигур и контуров используется векторная графика, поэтому их легко масштабировать для дисплеев с высоким разрешением. Если вы хотите узнать больше о векторной графике, ознакомьтесь с видео о том, [что такое векторная графика](https://www.youtube.com/watch?v=MoCSwF0n-io) , или статьей о [векторной графике](http://www.webopedia.com/TERM/V/vector_graphics.html).

##  <a name="Shape"></a> Рисование фигуры
 Фигуры можно найти на панели **Ресурсы** .

 ![Категория фигур на панели ресурсов](../designers/media/b4_shapes_assetspanel.png)

 Перетащите любую нужную фигуру в область рисования. Затем используйте маркеры фигуры, чтобы масштабировать, поворачивать, перемещать и наклонять фигуру.

 ![Handles](../designers/media/84261e83-3091-4490-ab58-4218b188439e.png)

##  <a name="Path"></a> Рисование контура
 Контур — это последовательность соединенных линий и кривых. Используйте контур для создания интересных фигур, которые недоступны на панели **Ресурсы** .

 Контур можно нарисовать с помощью линии, пера или карандаша. Эти инструменты доступны на панели **Средства** .

 ![Перо](../designers/media/717956a8-b6a5-4e37-8af3-70bcfc78c82a.png) ![Параметры пера](../designers/media/8fbbbb21-be83-4cf6-903b-3a49f00c9860.png)

### <a name="draw-a-straight-line"></a>Рисование прямой линии
 Используйте **Перо** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png) или **Линию** ![Линия](../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png).

 **Использование пера** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png)

 Щелкните один раз в области рисования, чтобы определить начальную точку, а затем щелкните еще раз для задания конечной точки линии.

 **Использование линии** ![Линия](../designers/media/eb618397-5283-48be-8396-3449be7b6fbf.png)

 В области рисования зажмите кнопку мыши в том месте, где должна начинаться линия, затем перетащите и отпустите кнопку мыши там, где линия завершается.

### <a name="draw-a-curve"></a>Рисование кривой
 Используйте **перо** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 В области рисования щелкните один раз, чтобы определить начальную точку линии, а затем зажмите и перетащите указатель мыши, чтобы задать нужную кривизну.

 Если требуется замкнуть контур, щелкните начальную точку линии.

### <a name="change-the-shape-of-a-curve"></a>Изменение формы кривой
 Используйте **прямое выделение** ![Прямое выделение](../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png).

 Щелкните фигуру, а затем потяните за любую точку на фигуре, чтобы изменить форму кривой.

### <a name="draw-a-free-form-path"></a>Рисование контура произвольной формы
 Используйте **карандаш** ![Карандаш](../designers/media/509dc167-734f-46c9-b012-987ee63450cd.png).

 Нарисуйте произвольный контур в области рисования, как если бы вы пользовались настоящим карандашом.

### <a name="remove-part-of-a-path"></a>Удаление части контура
 Используйте **прямое выделение** ![Прямое выделение](../designers/media/6dd6571f-c116-451d-8dd2-1f88b8406362.png).

 Выберите контур, содержащий сегмент, который требуется удалить, и нажмите кнопку **Удалить** .

### <a name="remove-a-point-in-a-path"></a>Удаление точки контура
 Используйте инструмент **выделения** ![Инструмент выделения](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png) и **перо** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 Используйте инструмент **выделения** ![Инструмент выделения](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png), чтобы выбрать контур. Затем с помощью **пера** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png) выделите точку, которую требуется удалить.

### <a name="add-a-point-to-a-path"></a>Добавление точки контура
 Используйте инструмент **выделения** ![Инструмент выделения](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png) и **перо** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png).

 Используйте инструмент **выделения** ![Инструмент выделения](../designers/media/2ff91340-477e-4efa-a0f7-af20851e4daa.png), чтобы выбрать контур. С помощью **пера** ![Перо](../designers/media/894f8612-e0ed-4e00-84cf-a9bc8f38fc54.png) щелкните в любом месте контура, где необходимо добавить точку.

##  <a name="Convert"></a> Преобразование фигуры в контур
 Чтобы изменить фигуру теми же способами, которые вы использовали для изменения контура, преобразуйте фигуру в контур.

 **Ознакомьтесь с коротким видео.** ![Настройка установленных компонентов](../designers/media/bldadminconsoleinitialconfigicon.png) [Работа с контурами. Преобразование фигуры в контур](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=147).

##  <a name="Combine"></a> Объединение контуров
 Контуры и фигуры можно объединить в один контур.

 ![Объединение контуров](../designers/media/2df17a5d-a338-4ef4-96c5-dae51cc1ca8a.png)

|||||
|-|-|-|-|
|![Две фигуры до объединения](../designers/media/b1_1.png)|Две фигуры до объединения|![Пересечение](../designers/media/b1_4.png)|Пересечение|
|![Исключение наложения](../designers/media/b1_2.png)|Объединение|![](../designers/media/b1_5.png)|Исключение перекрытия|
|![Subtract](../designers/media/b1_3.png)|Divide|![](../designers/media/b1_6.png)|Subtract|

 **Ознакомьтесь с коротким видео.** ![Настройка установленных компонентов](../designers/media/bldadminconsoleinitialconfigicon.png) [Работа с контурами. Объединение контуров](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=195).

##  <a name="Compound"></a> Создание составного пути
 При создании составного контура все пересекающиеся части контуров исключаются из результата, и результирующий контур принимает визуальные свойства нижнего контура.

 В любой момент после создания составного пути он может быть разбит на составляющие части.

 ![Прерывание составного контура](../designers/media/2157a8aa-d9a7-4de4-8de5-b10d28f08a84.png)

 **Ознакомьтесь с коротким видео.** ![Настройка установленных компонентов](../designers/media/bldadminconsoleinitialconfigicon.png) [Работа с контурами. Создание составного контура](https://www.youtube.com/watch?v=Io5bC0-nH6Q).

##  <a name="Clipping"></a> Создание контура кадрирования
 Контур обрезки — это контур или фигура, применяемая к другому объекту, чтобы скрыть части маскируемого объекта за пределами контура обрезки.

 ![Контур кадрирования](../designers/media/22471e98-a841-4f39-a3ef-36090cf5a625.png)

 **Ознакомьтесь с коротким видео.** ![Настройка установленных компонентов](../designers/media/bldadminconsoleinitialconfigicon.png) [Работа с контурами. Создание контура кадрирования](https://www.youtube.com/watch?v=Io5bC0-nH6Q#t=232).

## <a name="see-also"></a>См. также

- [Создание пользовательского интерфейса с помощью Blend для Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)