---
title: Расширение изолированной оболочки | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio shell, isolated mode
ms.assetid: 9a641d8f-211e-4486-a1b1-4a89fafe7ee8
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 65efd5a864863fb18f26d8fdfc3736423aad7aeb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054096"
---
# <a name="extending-the-isolated-shell"></a>Расширение изолированной оболочки
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Изолированная оболочка Visual Studio можно расширить, добавив VSPackage, частью Managed Extensibility Framework (MEF) компонента или универсального проекта VSIX в приложение изолированной оболочки.  
  
> [!NOTE]
>  Следующие шаги наличии в системе, создания базового приложения изолированной оболочки с помощью изолированной оболочки Visual Studio шаблон проекта. Дополнительные сведения о этот шаблон проекта, см. в разделе [Пошаговое руководство: Создание базового приложения Isolated Shell](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Расположения для шаблона Visual Studio Package  
 Шаблон проекта пакета Visual Studio можно найти в трех разных местах диалогового окна **Создание проекта** .  
  
1. В разделе **Visual Basic**, **расширяемости**. Язык проекта по умолчанию — Visual Basic.  
  
2. В разделе **Visual C#**, **расширяемости**. Язык проекта по умолчанию — C#.  
  
3. В разделе **других типов проектов**, **расширяемости**. Язык проекта по умолчанию — C++.  
  
## <a name="adding-a-vspackage"></a>Добавление пакетов VSPackage  
 Пакет VSPackage можно добавить в приложение изолированной оболочки. Ниже показано, как создать, добавляющий команды меню.  
  
#### <a name="to-add-a-new-vspackage"></a>Чтобы добавить нового пакета VSPackage  
  
1. Добавление проекта пакета Visual Studio с именем `MenuCommandsPackage`.  
  
2. На **базовых сведений о VSPackage** страницы мастера задайте **название компании** для `Fabrikam` и **имя VSPackage** для `FabrikamMenuCommands`. Нажмите кнопку **Далее**.  
  
3. На следующей странице выберите **команды меню** и выберите **Далее**.  
  
4. На следующей странице установите **имя команды** для `Fabrikam Command` и **идентификатор команды** для `cmdidFabrikamCommand`, а затем выберите **Далее**.  
  
5. На **Выбор параметров проекта теста** странице, снимите флажки всех параметров тестирования, а затем выберите **Готово** кнопки.  
  
6. В проекте ShellExtensionsVSIX откройте файл source.extension.vsixmanifest.  
  
     **Активы** раздел должен содержать запись для проекта VSShellStub.AboutBoxPackage.  
  
7. Выберите **New** кнопки.  
  
8. В **добавить новый актив** окно в **тип** выберите **Microsoft.VisualStudio.VsPackage**.  
  
9. В **источника** списке, убедитесь, что **проекта в текущем решении** выбран. В **проекта** поле со списком выберите **MenuCommandsPackage**.  
  
10. Сохраните и закройте файл.  
  
11. Перестройте решение и запустите отладку изолированной оболочки.  
  
12. В строке меню выберите **средства** меню, затем **команда Fabrikam**.  
  
     Появится окно сообщения.  
  
13. Остановите отладку приложения.  
  
## <a name="adding-a-mef-component-part"></a>Добавление компонента части MEF  
 Ниже показано, как добавить часть компонента MEF в приложение изолированной оболочки.  
  
#### <a name="to-add-a-mef-component"></a>Чтобы добавить компонент MEF  
  
1. В **Добавление нового проекта** диалогового **Visual C#**, **расширяемости**, использовать **поле редактора** шаблона, чтобы добавить в проект. Присвойте обработчику события имя `ShellEditorMargin`.  
  
2. В проекте ShellExtensionsVSIX откройте файл Source.extension.vsixmanifest в режиме конструктора, а не в представлении кода.  
  
3. В `Asset` выберите **добавить содержимое**.  
  
4. В **добавить новый актив** окно в **тип** выберите **Microsoft.VisualStudio.MefComponent**.  
  
5. В **источника** списке, убедитесь, что **проекта в текущем решении** выбран. В **проекта** поле со списком выберите **ShellEditorMargin**.  
  
6. Сохраните и закройте файл.  
  
7. Перестройте решение и запустите отладку изолированной оболочки.  
  
8. Откройте текстовый файл.  
  
     Зеленую границу, которая содержит слова «Hello world!» должны отображаться в нижней части окна файла текста.  
  
9. Остановите отладку приложения.  
  
## <a name="adding-a-generic-vsix-project"></a>Добавление проекта универсального VSIX  
  
#### <a name="to-add-a-generic-vsix-project"></a>Добавление универсального проекта VSIX  
  
1. В **Добавление нового проекта** диалогового **Visual C#**, **расширяемости**, использовать **VSIXProject** шаблона, чтобы добавить в проект. Присвойте обработчику события имя `EmptyVSIX`.  
  
2. В проекте ShellExtensionsVSIX откройте файл Source.extensions.vsixmanifest в режиме конструктора, а не в представлении кода.  
  
3. В `Assets` выберите **New**.  
  
4. В **добавить новый актив** окно в **тип** выберите типы содержимого, которые вы хотите добавить.  
  
5. В **источника**, убедитесь, что **проект в текущем решении** выбран параметр. В окне списка выберите имя проекта VSIX.  
  
6. Сохраните и закройте файл.  
  
7. Если этот проект содержит скомпилированный код, необходимо изменить проект, чтобы сборка будет включена в выходных данных.  
  
    1. Выгрузите проект VSIX и откройте файл проекта.  
  
    2. В первом `<PropertyGroup>` block, измените значение свойства `<CopyBuildOutputToOutputDirectory>` для `true`.  
  
    3. Сохранить и перезагрузить проект.  
  
8. Постройте и запустите это решение.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Создание базового приложения изолированной оболочки](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)
