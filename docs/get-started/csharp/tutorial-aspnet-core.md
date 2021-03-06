---
title: Учебник. Начало работы с C# и ASP.NET Core
titleSuffix: ''
description: Пошаговые инструкции по созданию веб-приложения ASP.NET Core в Visual Studio на C#.
ms.custom: seodec18, get-started
ms.date: 03/23/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 11f2849a2cf36564104d3250bdbad66ac69a0b40
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856571"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>Учебник. Начало работы с C# и ASP.NET Core в Visual Studio

В этом руководстве по разработке на языке C# с помощью ASP.NET Core в Visual Studio вы создадите веб-приложение ASP.NET Core на C#, внесете в него изменения, изучите некоторые возможности интегрированной среды разработки, после чего запустите приложение.

## <a name="before-you-begin"></a>Подготовка к работе

### <a name="install-visual-studio"></a>Установка Visual Studio

::: moniker range="vs-2017"

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017), если еще не сделали этого.

::: moniker-end

::: moniker range="vs-2019"

Установите Visual Studio бесплатно со страницы [скачиваемых материалов Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), если еще не сделали этого.

::: moniker-end

### <a name="update-visual-studio"></a>Обновление Visual Studio

Если вы уже установили Visual Studio, убедитесь, что используется самый последний выпуск среды. Дополнительные сведения об обновлении установки см. на странице [Обновление до последнего выпуска Visual Studio](../../install/update-visual-studio.md).

### <a name="choose-your-theme-optional"></a>Выбор темы (необязательно)

В этом руководстве содержатся снимки экрана, использующие темную тему. Если вы не используете темную тему, но хотите переключиться на нее, см. страницу [Персонализация интегрированной среды разработки и редактора Visual Studio](../../ide/quickstart-personalize-the-ide.md).

## <a name="create-a-project"></a>Создание проекта

Сначала создадим проект ASP.NET Core. Проект этого типа содержит все файлы шаблонов, необходимые для полнофункционального веб-сайта, что избавляет вас от лишней работы.

::: moniker range="vs-2017"

1. Откройте Visual Studio 2017.

2. В верхней строке меню последовательно выберите **Файл** > **Создать** > **Проект**.

3. В левой области диалогового окна **Новый проект** разверните узел **Visual C#**, затем разверните узел **Веб** и выберите **.NET Core**. В средней области выберите **Веб-приложение ASP.NET Core**. Назовите файл *MyCoreApp* и нажмите **ОК**.

   ![Шаблон проекта "Веб-приложение ASP.NET Core" в диалоговом окне "Новый проект" в интегрированной среде разработки Visual Studio](media/csharp-aspnet-choose-template-name-razor-mycoreapp-file.png)

### <a name="add-a-workload-optional"></a>Добавление рабочей нагрузки (необязательно)

Если шаблон проекта **Веб-приложение ASP.NET Core** отсутствует, его можно получить, добавив рабочую нагрузку **ASP.NET и разработка веб-приложений**. Добавить ее можно одним из двух способов в зависимости от того, какие обновления Visual Studio 2017 установлены на вашем компьютере.

#### <a name="option-1-use-the-new-project-dialog-box"></a>Вариант 1: использование диалогового окна "Новый проект"

1. Выберите ссылку **Открыть Visual Studio Installer** в левой области диалогового окна **Новый проект**. (В зависимости от параметров отображения может потребоваться выполнить прокрутку.)

   ![Выберите ссылку "Открыть Visual Studio Installer" в диалоговом окне "Новый проект"](../media/open-visual-studio-installer-mycoreapp.png)

1. Запускается Visual Studio Installer. Выберите рабочую нагрузку **ASP.NET и разработка веб-приложений**, а затем щелкните **Изменить**.

   ![Рабочая нагрузка "Кроссплатформенная разработка .NET Core" в Visual Studio Installer](../media/tutorial-aspnet-workload.png)

   (Возможно, перед тем как продолжить установку рабочей нагрузки, придется закрыть Visual Studio.)

#### <a name="option-2-use-the-tools-menu-bar"></a>Вариант 2: использование меню "Сервис"

1. Закройте диалоговое окно **Создать проект**. Затем в верхней строке меню выберите **Сервис** > **Получить средства и компоненты**.

1. Запускается Visual Studio Installer. Выберите рабочую нагрузку **ASP.NET и разработка веб-приложений**, а затем щелкните **Изменить**.

   (Возможно, перед тем как продолжить установку рабочей нагрузки, придется закрыть Visual Studio.)

### <a name="add-a-project-template"></a>Добавление шаблона проекта

1. В диалоговом окне **Создать веб-приложение ASP.NET Core** выберите шаблон проекта **Веб-приложение**.

1. Убедитесь, что в верхнем раскрывающемся меню отображается **ASP.NET Core 2.1**. Затем нажмите **ОК**.

   ![Диалоговое окно "Создать веб-приложение ASP.NET Core"](media/new-project-csharp-aspnet-razor-web-app.png)

   > [!NOTE]
   > Если **ASP.NET Core 2.1** или более поздняя версия не отображается в верхнем раскрывающемся меню, убедитесь, что вы используете самый последний выпуск Visual Studio. Дополнительные сведения об обновлении установки см. на странице [Обновление до последнего выпуска Visual Studio](../../install/update-visual-studio.md).

::: moniker-end

::: moniker range="vs-2019"

1. На начальном экране выберите **Создать проект**.

   ![Просмотр окна "Создание проекта"](../../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. В поле поиска окна **Создание проекта** введите *ASP.NET*. Затем выберите **C#** в списке языков и **Windows** в списке платформ. 

   Применив фильтры языка и платформы, выберите шаблон **Веб-приложение ASP.NET Core** и нажмите кнопку **Далее**.

   ![Выбор шаблона C# для веб-приложения ASP.NET Core](./media/vs-2019/csharp-create-new-project-search-aspnet-core-filtered.png)

   > [!NOTE]
   > Если шаблон **Веб-приложение ASP.NET Core** отсутствует, его можно установить из окна **Создание проекта**. В сообщении **Не нашли то, что искали?** выберите ссылку **Установка других средств и компонентов**.
   >
   > ![Ссылка "Установка других средств и компонентов" из сообщения "Не нашли то, что искали?" в окне "Создание проекта"](../../get-started/media/vs-2019/not-finding-what-looking-for.png) 
   > 
   > После этого в Visual Studio Installer выберите рабочую нагрузку **ASP.NET и разработка веб-приложений**.
   >
   > ![Рабочая нагрузка "Кроссплатформенная разработка .NET Core" в Visual Studio Installer](../../get-started/media/aspnet-core-web-dev-workload.png)
   >
   > Затем нажмите кнопку **Изменить** в Visual Studio Installer. Вам может быть предложено сохранить результаты работы; в таком случае сделайте это. Выберите **Продолжить**, чтобы установить рабочую нагрузку. После этого вернитесь к шагу 2 в процедуре [Создание проекта](#create-a-project).

1. В поле **Имя проекта** окна **Настроить новый проект** введите *MyCoreApp*. Затем нажмите **Создать**.

   ![В окне "Настроить новый проект" назовите проект "MyCoreApp"](./media/vs-2019/csharp-name-your-aspnet-mycoreapp-project.png)

1. Убедитесь, что в верхнем раскрывающемся меню диалогового окна **Create a new ASP.NET Core Web Application** (Создание веб-приложения ASP.NET Core) отображается **ASP.NET Core 2.1** или более поздней версии. Выберите **Веб-приложение**, включающее примеры Razor Pages. Затем выберите **Создать**.

   ![Окно "Create a new ASP.NET Core Web Application" (Создание веб-приложения ASP.NET Core)](./media/vs-2019/csharp-create-aspnet-core-razor-pages-app.png)

   Новый проект открывается в Visual Studio.

::: moniker-end

### <a name="about-your-solution"></a>Сведения о решении

Это решение основано на конструктивном шаблоне **Страница Razor**. Он отличается от конструктивного шаблона [Model-View-Controller (MVC)](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x) тем, что содержит код модели и код контролера в самой странице Razor.

## <a name="tour-your-solution"></a>Обзор решения

 1. С помощью шаблона проекта создается решение с одним проектом ASP.NET Core, который имеет имя _MyCoreApp_. Перейдите на вкладку **Обозреватель решений**, чтобы просмотреть его содержимое.

    ![Обозреватель решений ASP.NET в Visual Studio для решения "Страница Razor" с именем MyCoreApp](media/csharp-aspnet-razor-solution-explorer-mycoreapp.png)

 1. Разверните папку **Pages** и узел *About.cshtml*.

     ![Файл About.cshtml в обозревателе решений Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtml.png)

 1. Просмотрите файл **About.cshtml** в редакторе кода.

     ![Файл About.cshtml в редакторе кода Visual Studio](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code.png)

 1. Выберите файл **About.cshtml.cs**.

     ![Файл About.cshtml.cs в редакторе кода Visual Studio](media/csharp-aspnet-razor-solution-explorer-aboutcshtmlcs.png)

 1. Просмотрите файл **About.cshtml.cs** в редакторе кода.

     ![Файл About.cshtml в редакторе кода Visual Studio](media/csharp-aspnet-razor-aboutcshtmlcs-mycoreapp-code.png)

 1. Проект содержит папку **wwwroot**, которая является корневой для веб-сайта. Разверните папку, чтобы просмотреть его содержимое.

     ![Папка wwwroot в обозревателе решений Visual Studio](media/csharp-aspnet-razor-solution-explorer-wwwroot.png)

    Вы можете поместить статическое содержимое сайта &mdash; например CSS, изображения и библиотеки JavaScript &mdash; непосредственно в нужные пути.

 1. Проект также содержит файлы конфигурации для управления веб-приложением в среде выполнения. Стандартная [конфигурация](/aspnet/core/fundamentals/configuration) приложения хранится в файле *appsettings.json*. Тем не менее эти параметры можно переопределить с помощью *appsettings.Development.json*. Разверните файл **appsettings.json**, чтобы просмотреть файл **appsettings.Development.json**.

     ![Файлы конфигурации в обозревателе решений Visual Studio](media/csharp-aspnet-razor-solution-explorer-appsettingsjson.png)

## <a name="run-debug-and-make-changes"></a>Запуск, отладка и внесение изменений

1. Чтобы выполнить сборку приложения и запустить его в режиме отладки, нажмите в интегрированной среде разработки кнопку **IIS Express**. (Кроме того, можно нажать клавишу **F5** или выбрать пункт меню **Отладка** > **Начать отладку** в строке меню.)

     ![Нажмите кнопку "IIS Express" в Visual Studio](media/csharp-aspnet-razor-iisexpress.png)

     > [!NOTE]
     > Если появляется сообщение об ошибке **Не удается подключиться к веб-серверу "IIS Express"**, закройте среду Visual Studio и откройте ее с помощью пункта **Запуск от имени администратора** в контекстном меню. Затем снова запустите приложение.
     >
     > Может также появиться запрос о том, хотите ли вы принять сертификат IIS SSL Express. Чтобы просмотреть код в веб-браузере, выберите **Да**, а затем снова **Да**, если появится предупреждение системы безопасности о дальнейшей обработке. 

1. Visual Studio откроет окно браузера. В строке меню вы должны увидеть названия страниц **Home** (Главная), **About** (О программе) и **Contact** (Контакты). (Если названия страниц не отображаются, нажмите кнопку меню, напоминающую гамбургер, чтобы их увидеть.)

    ![Кнопка меню, напоминающая гамбургер, в строке меню веб-приложения](media/csharp-aspnet-razor-browser-page.png)

     > [!TIP]
     > Вы не можете изменить код в редакторе кода Visual Studio, когда проект открыт в окне браузера. 

1. Выберите в строке меню страницу **About** (О программе).

   ![Страница About (О программе) в строке меню открытого в браузере приложения](media/csharp-aspnet-razor-browser-page-about-menu.png)

   Помимо прочего, на открытой в браузере странице **About** (О программе) отображается текст, заданный в файле *About.cshtml*.

   ![Просмотр текста на странице "About"](media/csharp-aspnet-razor-browser-page-about.png)

1. Не закрывая окно браузера, вернитесь в Visual Studio.

1. В Visual Studio выберите файл **About.cshtml**. Затем удалите слово _additional_, заменив его словами _file и directory_.

    ![Изменение текста в файле About.cshtml](media/csharp-aspnet-razor-aboutcshtml-mycoreapp-code-changed.png)

1. Выберите файл **About.cshtml.cs**. Очистите директивы `using` в начале файла, как описано ниже.

   Выберите любую из выделенных серым цветом директив `using`. Под курсором или в поле слева отобразится меню [Быстрые действия](../../ide/quick-actions.md) (значок лампочки). Выберите лампочку, а затем команду **Удалить ненужные директивы Using**.

   ![Удаление ненужных директив Using из файла About.cshtml.cs](media/csharp-aspnet-razor-remove-unnecessary-usings.png)

     Visual Studio удалит из файла ненужные директивы `using`.

1. Затем в методе `OnGet()` замените основную часть таким кодом:

     ```csharp
     public void OnGet()
     {
         string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
     }
    ```
1. Обратите внимание, что **Environment** (Среда) и **String** (Строка) подчеркнуты волнистой линией. Подчеркивание волнистой линией появилось, потому что эти типы находятся за пределами области.

   ![Ошибки, подчеркнутые волнистой линией, в методе OnGet](media/csharp-aspnet-razor-add-new-on-get-method.png)

    Откройте панель инструментов **Список ошибок**, чтобы просмотреть там те же самые ошибки. (Если вы не видите панель инструментов **Список ошибок**, выберите **Представление** > **Список ошибок** в верхней строке меню.)

   ![Список ошибок в Visual Studio](media/csharp-aspnet-razor-error-list.png)

1. Давайте исправим это. В редакторе кода установите курсор в любую строку с ошибкой, а затем в поле слева выберите меню "Быстрые действия" (значок лампочки). В раскрывающемся меню выберите **using System;**, чтобы добавить эту директиву в начало файла и устранить ошибки.

   ![Добавление директивы using System;](media/csharp-aspnet-razor-add-usings.png)

1. Нажмите клавиши **CTRL**+**S**, чтобы сохранить изменения, и обновите приложение в веб-браузере.

1. В верхней части веб-сайта выберите пункт **About** (О программе), чтобы просмотреть изменения.

   ![Обновленная страница About (О программе) с внесенными изменениями](media/csharp-aspnet-razor-browser-page-about-changed.png)

1. Закройте веб-браузер, нажмите клавиши **SHIFT**+**F5**, чтобы выйти из режима отладки, и закройте Visual Studio.

## <a name="quick-answers-faq"></a>Быстрые ответы на часто задаваемые вопросы

Ниже приведен краткий список вопросов и ответов, с помощью которого вы сможете ознакомиться с некоторыми основными понятиями.

### <a name="what-is-c"></a>Что такое C#?

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) — это типобезопасный объектно-ориентированный язык программирования, который обладает широкими возможностями, но в то же время прост в обучении.

### <a name="what-is-aspnet-core"></a>Что такое ASP.NET Core?

ASP.NET Core — это кроссплатформенная платформа с открытым кодом для создания приложений, подключенных к Интернету, таких как веб-приложения и службы. Приложения ASP.NET Core могут работать на основе .NET Core или .NET Framework. Приложения ASP.NET Core можно разрабатывать и запускать на различных платформах, включая Windows, Mac и Linux. Код ASP.NET Core открыт для общего доступа в [GitHub](https://github.com/aspnet/home).

### <a name="what-is-visual-studio"></a>Что такое Visual Studio?

Visual Studio — это интегрированный набор средств разработки. Его можно рассматривать как программу для создания приложений.

## <a name="next-steps"></a>Следующие шаги

Поздравляем с завершением этого учебника! Надеемся, что вы узнали что-то новое о C#, ASP.NET Core и интегрированной среде разработки Visual Studio. Дополнительные сведения о создании веб-приложения или веб-сайта с помощью C# и ASP.NET вы найдете в следующих руководствах:

> [!div class="nextstepaction"]
> [Создание веб-приложения Razor Pages с помощью ASP.NET Core](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>См. также

[Публикация веб-приложения в службе приложений Azure с помощью Visual Studio](../../deployment/quickstart-deploy-to-azure.md)
