---
title: Отладка в Windows Forms | Документация Майкрософт
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- debugging managed code, Windows Forms
- debugging [Visual Studio], Windows Forms
- Attach to Process dialog box
- debugger, attaching to programs
- Attach to Process dialog box, walkthroughs
- Windows Forms, debugging
- debugging Windows Forms, walkthroughs
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d348675ca8670aa27035d31657d06bc2c4e0a829
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60075354"
---
# <a name="walkthrough-debugging-a-windows-form"></a>Пошаговое руководство. Отладка формы Windows Form
Форма Windows Forms — один из наиболее распространенных вариантов управляемых приложений. На основе формы Windows Forms создается стандартное приложение Windows. Можно реализовать данный примере на Visual Basic, C# или C++.

 Для начала необходимо закрыть и открыть решения.

### <a name="to-prepare-for-this-walkthrough"></a>Чтобы подготовиться к выполнению данного пошагового руководства

- Если какое–либо решение уже открыто, закройте его. (В меню **Файл** выберите команду **Закрыть решение**.)

## <a name="create-a-new-windows-form"></a>Создание новой формы Windows Forms.
 Далее нам предстоит создать новую форму Windows Forms.

#### <a name="to-create-the-windows-form-for-this-walkthrough"></a>Чтобы создать форму Windows Forms для данного примера

1. В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.

     Откроется диалоговое окно **Новый проект** .

2. В области "Типы проектов" разверните узел **Visual Basic**, **Visual C#** или **Visual C++**, затем

    1. Для Visual Basic или Visual C#, выберите **Windows Desktop** > **приложение формы Windows**.

    2. Visual C++ выберите **классическое приложение Windows**.

3. В поле **Имя** задайте уникальное имя проекта (например, Walkthrough_SimpleDebug).

4. Нажмите кнопку **ОК**.

     Visual Studio создаст новый проект и откроет новую форму в конструкторе Windows Forms. Дополнительные сведения см. в разделе [Конструктор Windows Forms](/previous-versions/visualstudio/visual-studio-2010/e06hs424\(v\=vs.100\)).

5. В меню **Вид** выберите пункт **Панель элементов**.

     Откроется Панель элементов. См. дополнительные сведения о [панели элементов](../ide/reference/toolbox.md).

6. В панели элементов щелкните элемент управления **Кнопка** и перетащите его на поверхность разработки формы. Опустите кнопку на форму.

7. В панели элементов щелкните элемент управления **Текстовое поле** и перетащите его на поверхность разработки формы. Бросьте **Текстовое поле** в форму.

8. На поверхности разработки формы дважды щелкните кнопку.

     Появится страница кода. Курсор должен находиться в тексте `button1_Click`

10. В функции `button1_Click` добавьте следующий код:

    ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";
    ```

11. В меню **Сборка** выберите команду **Собрать решение**.

     Проект должен быть построен без ошибок.

## <a name="debug-your-form"></a>Отладка формы
 Теперь все готово для того, чтобы начать отладку.

#### <a name="to-debug-the-windows-form-created-for-this-walkthrough"></a>Чтобы выполнить отладку формы Windows Forms, созданной для данного примера

1. В окне исходного кода щелкните левое поле на той же строке, в которую добавляется текст:

     ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";
    ```

     Появится красная точка, и текст строки будет выделен красным цветом. Красная точка представляет точку останова. Дополнительные сведения см. в разделе [Точки останова](https://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583). Если приложение запускается из отладчика, выполнение этого приложения будет приостановлено отладчиком на строке с помеченным кодом. После этого можно просмотреть состояние приложения и произвести его отладку.

    > [!NOTE]
    >  Можно также щелкнуть правкой кнопкой мыши любую строку кода, выбрать пункт **Точка останова**, затем щелкнуть **Вставить точку останова**, чтобы добавить точку останова в эту строку.

2. В меню **Отладка** выберите команду **Пуск**.

     Запустится форма Windows Forms.

3. В форме Windows Forms щелкните добавленную кнопку.

     После этого в Visual Studio приложение остановится на той строке, где была задана точка останова на странице кода. Эта строка будет выделена желтым цветом. Теперь можно просматривать переменные в приложении и управлять его выполнением. В этот момент приложение остановит свое выполнение и будет ожидать действий со стороны пользователя.

4. В меню **Отладка** выберите пункт **Окна**, затем **Контрольные значения** и потом **Контрольные значения 1**.

5. В окне **Контрольные значения 1** щелкните пустую строку. В **имя** столбец, тип `textBox1.Text` (Если вы используете Visual Basic или Visual C#) или `textBox1->Text` (если используется C++), затем нажмите клавишу ВВОД.

     Окно **Контрольные значения 1** отобразит значение этой переменной в двойных кавычках, как показано ниже:

    `""`

6. В меню **Отладка** выберите команду **Выполнять по шагам**.

     Значение textBox1.Text в **Контрольные значения 1** окно, чтобы:

    `Button was clicked!`

7. В меню **Отладка** выберите команду **Продолжить** для возобновления отладки программы.

8. В форме Windows Forms снова нажмите кнопку.

     Visual Studio снова приостановит выполнение программы.

9. Щелкните красную точка, представляющую точка останова.

     Это действие удалит точка останова из кода программы.

10. В меню **Отладка** выберите **Остановить отладку**.

## <a name="attach-to-your-windows-form-application-for-debugging"></a>Присоединение к приложению Windows Form для отладки
 В [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] можно присоединить отладчик к выполняющемуся процессу. Если используется экспресс-выпуск, эта функция не поддерживается.

#### <a name="to-attach-to-the-windows-form-application-for-debugging"></a>Присоединение к приложению Windows Form для отладки

1. В созданном ранее проекте щелкните левое поле, чтобы еще раз установить точка останова на добавленной строке:

     ```vb
    textBox1.Text = "Button was clicked!"
    ```

    ```csharp
    textBox1.Text = "Button was clicked!";
    ```

    ```cpp
    textBox1->Text = "Button was clicked!";

2. On the **Debug** menu, select **Start Without Debugging**.

     The Windows Form starts running under Windows, just as if you had double-clicked its executable. The debugger is not attached.

3. On the **Debug** menu, select **Attach to Process**. (This command is also available on the **Tools** menu.)

     The **Attach to Process** dialog box appears.

4. In the **Available Processes** pane, find the process name (Walkthrough_SimpleDebug.exe) in the **Process** column and click it.

5. Click the **Attach** button.

6. In your Windows Form, click the one and only button.

     The debugger breaks execution of the Windows Form at the breakpoint.

## See Also
- [Debugging Managed Code](../debugger/debugging-managed-code.md)
- [Debugger Security](../debugger/debugger-security.md)