---
title: Настройка начальной страницы | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: 48
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f043e3cfbc6d81306abfb68276f2e32cce63ed45
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "57869035"
---
# <a name="customizing-the-start-page-for-visual-studio"></a>Настройка начальной страницы в Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Существует несколько способов настройки начальной страницы Visual Studio: например, для этого можно использовать диалоговое окно **Открытие проекта** или открыть решение, загруженное последним. Также можно отобразить настраиваемую начальную страницу, т. е. страницу XAML Windows Presentation Foundation (WPF), которая открывается в окне инструментов и может использоваться для выполнения внутренних команд Visual Studio.

## <a name="customizing-the-default-start-page"></a>Настройка начальной страницы по умолчанию

1.  В строке меню выберите **Сервис**, **Параметры**.

2.  Разверните меню **Среда** и выберите **Запуск**.

3.  В списке **При запуске** выберите элемент, который требуется настроить.

## <a name="show-a-custom-start-page"></a>Отображение настраиваемой начальной страницы

1.  Установите настраиваемую начальную страницу одним из следующих способов:

    -   Установите его из [Visual Studio Marketplace](https://marketplace.visualstudio.com/), другого веб-сайта или со страницы своей локальной интрасети.

        > [!NOTE]
        >  Если вы предпочитаете страницу, предназначенную для более ранней версии Visual Studio, то можете обновить ее при помощи пакета SDK для Visual Studio. См. [Практическое руководство. Обновление настраиваемой начальной страницы Visual Studio](../misc/how-to-upgrade-a-visual-studio-custom-start-page.md).

         Откройте файл VSIX, содержащий настраиваемую начальную страницу, или скопируйте и вставьте файлы начальной страницы в папку **%USERPROFILE% \Мои документы\Visual Studio 2015\StartPages** на компьютере.

    -   Создайте собственную начальную страницу, если на вашем компьютере установлен пакет SDK для Visual Studio.

         См. в разделе [создание собственной начальной страницы](../misc/creating-your-own-start-page.md).

2.  В строке меню выберите **Сервис**, **Параметры**.

3.  Разверните меню **Среда** и выберите **Запуск**.

4.  В списке **Настроить начальную страницу** выберите нужную страницу.

> [!NOTE]
>  Если ошибка в настраиваемой начальной странице вызывает сбой Visual Studio, можно запустить Visual Studio в безопасном режиме, а затем настроить использование начальной страницы по умолчанию. См. раздел [/SafeMode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>См. также раздел
 [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3) [создание собственной начальной страницы](../misc/creating-your-own-start-page.md)
