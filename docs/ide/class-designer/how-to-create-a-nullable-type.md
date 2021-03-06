---
title: Как выполнить  Создание типа, допускающего значение NULL (конструктор классов)
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- nullable types, Class Designer
- Class Designer [Visual Studio], nullable types
ms.assetid: 84673a89-3f6d-4668-919e-1c0f56182fe5
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a5c70375e7b7b47b9c345c13b5529ea29e1eed45
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55925528"
---
# <a name="how-to-create-a-nullable-type-in-class-designer"></a>Как выполнить  Создание типа, допускающего значение NULL, в конструкторе классов

Определенные типы значений не всегда имеют или требуют определенное значение. Это распространенная практика в базах данных, где некоторым полям нельзя назначить любое значение. Например, полю базы данных можно присвоить значение NULL, чтобы указать, что ему еще не было назначено значение.

*Тип, допускающий значение NULL* является типом значений, который можно расширить, чтобы он принял стандартный набор значений для этого типа, а также значение NULL. Например, для допускающего значение NULL `Int32`, который также обозначается как Nullable\<Int32>, можно назначить любое значение от -2 147 483 648 до 2 147 483 647 или значение NULL. Для Nullable\<bool> можно назначить значения `True`, `False` или NULL (без значения).

Типы, допускающие значения NULL, являются экземплярами структуры <xref:System.Nullable%601>. Каждый объект типа, допускающего значение NULL, имеет два открытых свойства, доступных только для чтения, `HasValue` и `Value`:

-   `HasValue` имеет тип `bool` и указывает, содержит ли переменная определенное значение. `True` означает, что переменная содержит значение, не равное NULL. Можно провести тест для определенного значения с помощью оператора, такого как `if (x.HasValue)` или `if (y != null)`.

-   `Value` имеет тот же тип, что и базовый тип. Если `HasValue` равно `True`, то свойство `Value` содержит полезное значение. Если `HasValue` равно `False`, доступ к свойству `Value` вызовет исключение недопустимой операции.

По умолчанию при объявлении переменной как типа данных, допускающего значения NULL, она не имеет определенного значения (`HasValue` равен `False`), отличного от значения по умолчанию для базового типа.

Конструктор классов отображает тип, допускающий значение NULL, так же, как он отображает его базовый тип.

См. дополнительные сведения о [типах, допускающих значение NULL в C#](/dotnet/csharp/programming-guide/nullable-types/index). Дополнительные сведения о типах, допускающих значение NULL, в Visual Basic см. в разделе [Типы значений, допускающие значение NULL](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types).

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-a-nullable-type-by-using-the-class-designer"></a>Добавление типа, допускающего значение NULL, с помощью конструктора классов

1.  На диаграмме классов разверните существующий класс или создайте новый.

2.  Чтобы добавить класс в проект, в меню **Диаграмма классов** щелкните **Добавить** > **Добавить класс**.

3.  Чтобы развернуть фигуру класса, в меню **Схема классов** щелкните **Развернуть**.

4.  Выберите фигуру класса. В меню **Диаграмма классов** щелкните **Добавить** > **Поле**. Новое поле с именем по умолчанию **Поле** появится на фигуре класса, а также в окне **Сведения о классе**.

5.  В столбце **Имя** окна **Сведения о классе** (или на самой фигуре класса) измените имя нового поля на допустимое и значимое имя.

6.  В столбце **Тип** окна **Сведения о классах** объявите тип как тип, допускающий значения NULL, указав следующее:

    - `int?` (Visual C#)
    - `Nullable(Of Integer)` (Visual Basic)

## <a name="to-add-a-nullable-type-by-using-the-code-editor"></a>Добавление типа, допускающего значение NULL, с помощью редактора кода

1.  Добавьте в проект класс. Выберите узел проекта в **обозревателе решений**, а затем в меню **Проект** выберите **Добавить класс**.

2.  В файл CS или VB нового класса добавьте один или несколько типов, допускающих значения NULL, в объявление нового класса.

    ```csharp
    // Declare a nullable type in Visual C#:
    class Test
    {
       int? building_number = 5;
    }
    ```

    ```vb
    ' Declare a nullable type in Visual Basic:
    Class Test
       Dim buildingNumber As Nullable(Of Integer) = 5
    End Class
    ```

3.  Из представления классов перетащите значок нового класса в область конструктора классов. Фигура класса появляется на схеме классов.

4.  Разверните сведения для фигуры класса и переместите указатель мыши на элементы класса. Всплывающая подсказка отображает объявление каждого члена.

5.  Щелкните правой кнопкой мыши фигуру класса и выберите пункт **Сведения о классе**. Свойства нового типа можно просмотреть или изменить в окне **Сведения о классе**.

## <a name="see-also"></a>См. также

- <xref:System.Nullable%601>
- [Типы, допускающие значения NULL](/dotnet/csharp/programming-guide/nullable-types/index)
- [Использование допускающих значение NULL типов](/dotnet/csharp/programming-guide/nullable-types/using-nullable-types)
- [Практическое руководство. Идентификация типа, допускающего значение NULL](/dotnet/csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type)
- [Типы значений, допускающие значение NULL](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)
