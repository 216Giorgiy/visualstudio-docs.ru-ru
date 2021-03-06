---
title: Как использовать XML-фрагменты
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e4a56249c0a87b2516dc233818208f7c7c4b696e
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526221"
---
# <a name="how-to-use-xml-snippets"></a>Практическое руководство. Использовать XML-фрагменты

XML-фрагменты можно вызывать с помощью следующих двух команд в контекстное меню редактора XML. **Вставить фрагмент** команда вставляет фрагмент кода XML в позиции курсора. **Окружить** команда создает оболочку для XML-фрагмент вокруг выбранного текста. Для каждого XML-фрагмента имеются назначенные типы фрагментов. Типы фрагментов определяют ли фрагмент доступен с **вставить фрагмент** команде **окружить** или для обеих команд.

После добавления XML-фрагмента в редактор все редактируемые поля во фрагменте выделяются желтым цветом, а курсор помещается в первое редактируемое поле.

## <a name="insert-snippet"></a>Вставить фрагмент

Следующие процедуры описывают, как получить доступ к **вставить фрагмент** команды.

> [!NOTE]
> **Вставить фрагмент** команда также доступна через сочетание клавиш (**Ctrl**+**K**, затем **Ctrl** + **X**).

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Вставка фрагментов из контекстного меню

1. Поместите курсор в то место, куда нужно добавить XML-фрагмент.

2. Щелкните правой кнопкой мыши и выберите **вставить фрагмент**.

   Отображается список доступных XML-фрагментов.

3. Выберите фрагмент из списка при помощи мыши или введя имя фрагмента и нажатия клавиши **вкладке** или **ввод**.

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Вставка фрагментов с помощью меню IntelliSense

1. Поместите курсор в то место, куда нужно добавить XML-фрагмент.

2. Из **изменить** последовательно выберите пункты **IntelliSense**, а затем выберите **вставить фрагмент**.

   Отображается список доступных XML-фрагментов.

3. Выберите фрагмент из списка при помощи мыши или введите имя фрагмента и нажатия клавиши **вкладке** или **ввод**.

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>Вставка фрагментов список слов IntelliSense

1. Поместите курсор в то место, куда нужно добавить XML-фрагмент.

2. Начните вводить XML-фрагмент, который нужно добавить в файл. Если включено автоматическое завершение, отобразится список слов IntelliSense для автоматического завершения. Если он не отображается, нажмите клавишу **Ctrl**+**пространства** для ее активации.

3. Выберите XML-фрагмент из списка автоматического завершения слов.

4. Нажмите клавишу **вкладке**, **вкладке** вызвать фрагмент кода XML.

> [!NOTE]
> В некоторых случаях XML-фрагмент не вызывается. К примеру, если попытаться вставить элемент `xs:complexType` внутри узла `xs:element`, редактор не создает XML-фрагмент. Когда элемент `xs:complexType` используется внутри узла `xs:element`, отсутствуют необходимые атрибуты или вложенные элементы, поэтому редактор не имеет данных для вставки.

### <a name="to-insert-snippets-using-the-shortcut-name"></a>Вставка фрагментов с помощью сокращенных имен

1. Поместите курсор в то место, куда нужно добавить XML-фрагмент.

2. Наберите `<` на панели редактора.

3. Нажмите клавишу **Esc** закрыть список слов IntelliSense.

4. Введите имя ярлыка фрагмента, а затем нажмите клавишу **вкладке** вызвать фрагмент кода XML.

## <a name="surround-with"></a>Окружить

Следующие процедуры описывают, как получить доступ к **окружить** команды.

> [!NOTE]
> **Окружить** команда также доступна через сочетание клавиш (**Ctrl**+**K**, затем **Ctrl** + **S**).

### <a name="to-use-surround-with-from-the-context-menu"></a>Чтобы использовать разместить во фрагменте, в контекстном меню

1. Выделите текст, который нужно окружить с помощью редактора XML.

2. Щелкните правой кнопкой мыши и выберите **окружить**.

   Отображается список XML-фрагментов, доступных для окружения.

3. Выберите фрагмент из списка при помощи мыши или введя имя фрагмента и нажатия клавиши **вкладке** или **ввод**.

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>Чтобы использовать окружить из меню IntelliSense

1. Выделите текст, который нужно окружить с помощью редактора XML.

2. Из **изменить** последовательно выберите пункты **IntelliSense**, а затем выберите **окружить**.

   Отображается список XML-фрагментов, доступных для окружения.

3. Выберите фрагмент из списка при помощи мыши или введя имя фрагмента и нажатия клавиши **вкладке** или **ввод**.

## <a name="use-xml-snippets"></a>Использовать XML-фрагменты

Если выбран XML-фрагмент, текст фрагмента кода автоматически вставляется в текущей позиции курсора. Все редактируемые поля фрагмента выделяются цветом, а первое редактируемое поле выбирается автоматически. Выбранное в данный момент поле окружено рамкой.

Выделив поле, можно ввести для него новое значение. Нажав клавишу **вкладке** циклическое переключение между редактируемые поля фрагмента кода; при нажатии **Shift**+**вкладке** переходить по ним в обратном порядке. Если щелкнуть поле один раз, курсор помещается в поле, а если щелкнуть поле дважды, оно будет выделено. Если поле выделено подсветкой, может отображаться подсказка с описанием этого поля.

Редактируемым является только первый экземпляр данного поля. После выделения такого поля прочие экземпляры поля обозначаются контуром. Если изменить значение в редактируемом поле, это поле изменится везде, где оно встречается во фрагменте.

Нажав клавишу **ввод** или **Esc** отменить редактирование поля и возвращается к норме редактора.

Цвета по умолчанию для редактируемых полей фрагментов кода можно изменить, изменив **поле фрагмента кода** в **шрифты и цвета** области **параметры** диалоговое окно. Дополнительные сведения см. в разделе [Как Изменение шрифтов и цветов в редакторе](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>См. также

- [XML-фрагменты](../xml-tools/xml-snippets.md)
- [Практическое руководство. Создание XML-фрагмент из схемы XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [Практическое руководство. Создание XML-фрагментов](../xml-tools/how-to-create-xml-snippets.md)