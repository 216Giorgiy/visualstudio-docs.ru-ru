---
title: Публикация в папку
ms.date: 01/22/2019
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: e963fb4b-6d32-4d45-86bb-ef7e4d3028b0
author: sayedihashimi
ms.author: sayedha
manager: unniravindranathan
ms.prod: visual-studio-mac
ms.openlocfilehash: c59e19434edcb19982fa72d3ddc96d7cb6a870a8
ms.sourcegitcommit: da73f7a0cf1795d5d400c0897ae3326191435dd0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58568136"
---
# <a name="publish-a-web-app-to-a-folder-using-visual-studio-for-mac"></a>Публикация веб-приложения в папку с помощью Visual Studio для Mac

Вы можете использовать средство публикации для публикации приложений ASP.NET Core в папку.

## <a name="prerequisites"></a>Предварительные требования

 - [Visual Studio 2017 для Mac](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs4mac2017), установленный с поддержкой ASP.NET Core.
 - Проект ASP.NET Core. Если у вас еще нет проекта, вы можете [создать его](https://docs.microsoft.com/visualstudio/mac/create-new-projects?view=vsmac-2017).

## <a name="publish-to-folder"></a>Публикация в папку

С помощью Visual Studio для Mac можно публиковать проекты ASP.NET Core в папку, используя средство публикации. После публикации в папку можно передать файлы на веб-сервер, чтобы получить его в другой среде. Для публикации в папку выполните следующие действия.

 1. На панели решений щелкните проект правой кнопкой мыши и выберите пункт **Опубликовать**.

    ![Контекстное меню публикации](media/publish-context-menu.png)

 2. Если ранее вы публиковали этот проект, вы увидите профиль публикации в меню. Выберите этот профиль публикации, чтобы начать процесс публикации.

 3. Чтобы опубликовать этот проект в папку в первый раз, выберите **Публикация в папку**

    ![Контекстное меню "Публикация в папку"](media/publish-to-folder-context-menu.png)

 4. Появится диалоговое окно **Публикация в папку**. В этом диалоговом окне можно настроить папку, где будет опубликован проект. Нажмите кнопку **Обзор** или вставьте путь.

 5. После нажатия кнопки **Опубликовать** выполняются следующие действия. Сначала создается профиль публикации. Профиль публикации — это файл MSBuild, который импортируется в проект во время процесса публикации. Он содержит свойства, которые используются во время процесса публикации. Эти файлы хранятся в `Properties/PublishProfiles` и имеют расширение `.pubxml`. Затем запускается процесс публикации. Ход выполнения можно контролировать в строке состояния в Visual Studio для Mac.

    ![Строка состояния в интегрированной среде разработки с состоянием публикации](media/publish-to-folder-status-bar.png)

 6. После успешного завершения публикации в окне поиска откроется папка публикации. Созданный профиль публикации отображается в контекстном меню публикации.

    ![Контекстное меню публикации с профилем папки](media/publish-context-menu-with-folder-profile.png)

 7. Чтобы опубликовать проект еще раз с теми же параметрами, щелкните профиль в контекстном меню публикации.

## <a name="customize-publish-options"></a>Настройка параметров публикации

Чтобы изменить имя профиля публикации (которое отображается в контекстном меню публикации), переименуйте файл профиля публикации. Не меняйте расширение файла (`.puxbml`).

Чтобы изменить путь к папке публикации, откройте профиль публикации и измените значение `publishUrl`.

Чтобы изменить используемую конфигурацию сборки, измените свойство `LastUsedBuildConfiguration` в профиле публикации.