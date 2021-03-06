---
title: Настройка интегрированной среды разработки
ms.date: 11/20/2017
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62f2d98777f1fe87b67bdb28e6302f29f752f27f
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790242"
---
# <a name="personalize-the-visual-studio-ide"></a>Персонализация интегрированной среды разработки Visual Studio

Доступны разные способы индивидуальной настройки Visual Studio в соответствии с личным стилем и требованиями к разработке. Целый ряд параметров можно использовать в разных экземплярах Visual Studio &mdash; см. статью [Синхронизация параметров в Visual Studio](../ide/synchronized-settings-in-visual-studio.md). В этой статье кратко описываются эти способы, а также приводятся ссылки на ресурсы с дополнительными сведениями.

> [!NOTE]
> Этот раздел относится к Visual Studio в Windows. Информацию о Visual Studio для Mac см. в статье [Настройка интегрированной среды разработки Visual Studio для Mac](/visualstudio/mac/customizing-the-ide).

## <a name="default-settings"></a>Параметры по умолчанию

Можно выбрать заданную по умолчанию коллекцию параметров, которая оптимизирует Visual Studio для вашего типа разработки. Дополнительные сведения см. в статье [Параметры среды](environment-settings.md).

## <a name="general-environment-options"></a>Общие параметры среды

Доступ ко многим персонализированным параметрам можно также получить в диалоговом окне [Параметры среды](../ide/reference/environment-options-dialog-box.md). Открыть это диалоговое окно можно двумя способами:

- В строке меню выберите **Сервис** > **Параметры** и при необходимости разверните узел **Среда**.

- Нажмите клавиши **CTRL**+**Q**, введите **среда** в поле поиска, а затем выберите **Среда --> Общие** из результатов.

> [!TIP]
> В открывшемся диалоговом окне "Параметры" нажмите клавишу **F1** для получения справочных сведений о различных параметрах на этой странице.

## <a name="environment-color-themes"></a>Цветовые темы среды

Чтобы изменить цветовую тему на светлую, темную или синюю, введите **среда** в поле поиска и выберите **Среда --> Общие**. В диалоговом окне **Параметры** измените значение настройки **Цветовая тема**.

Чтобы изменить параметры раскраски в редакторе, введите **среда** в поле поиска и выберите **Среда --> Шрифты и цвета**. См. практическое руководство по [ Изменение шрифтов и цветов](../ide/how-to-change-fonts-and-colors-in-visual-studio.md).

### <a name="main-menu-casing"></a>Регистр главного меню

Вы можете изменить регистр главного меню, выбрав вариант **Заглавные буквы** (например, "Файл") и **ВСЕ ПРОПИСНЫЕ** (например, "ФАЙЛ"). Введите **среда** в поле поиска, выберите **Среда --> Общие**, а затем измените параметр **Применить регистр заголовка к строке меню**.

### <a name="customize-menus-and-toolbars"></a>Настройка меню и панелей инструментов

Сведения о добавлении или удалении элементов меню или панели инструментов см. в разделе [Практическое руководство. Настройка меню и панелей инструментов](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md).

::: moniker range="vs-2017"

## <a name="start-page"></a>Начальная страница

Сведения о создании настраиваемой начальной страницы для пользователя и команды см. в разделе [Настройка начальной страницы](../ide/customizing-the-start-page-for-visual-studio.md).

::: moniker-end

## <a name="window-layouts"></a>Макеты окон

Можно определить и сохранить несколько макетов окон и переключаться между ними. Например, можно определить один макет для написания кода, а другой — для отладки. Сведения о расположении окон и упорядочивании их поведения, а также о сохранении пользовательских макетов см. в статье [Настройка макетов окон](../ide/customizing-window-layouts-in-visual-studio.md).

## <a name="external-tools"></a>Внешние инструменты

Вы можете настроить меню **Сервис** и запускать внешние средства. Дополнительные сведения см. в разделе [Управление внешними инструментами](../ide/managing-external-tools.md).

## <a name="see-also"></a>См. также

- [Параметры среды](environment-settings.md)
- [Обзор интегрированной среды разработки Visual Studio](../get-started/visual-studio-ide.md)
- [Краткое руководство. Знакомство с интегрированной средой разработки Visual Studio](../ide/quickstart-ide-orientation.md)
- [Настройка интегрированной среды разработки Visual Studio для Mac](/visualstudio/mac/customizing-the-ide)