---
title: Публикация в службе приложений на платформе Linux
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: e0268c2e65cd08274c2267ad2a4969f6015cbaf4
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "39234858"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>Публикация приложения ASP.NET Core в службе приложений на платформе Linux с помощью Visual Studio

Можно использовать **публикации** , которая позволяет публиковать приложения ASP.NET Core в службе приложений Azure на платформе Linux.

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>Публикация в службе приложений на платформе Linux

1. В обозревателе решений щелкните правой кнопкой мыши проект и выберите **публикации** (или используйте **построения** > **публикации** пункт меню).

    ![Команда публикации в контекстном меню проекта в обозревателе решений](../deployment/media/quickstart-publish.png "выберите публикации")

1. Если ранее вы настроили все профили публикации **публикации** откроется панель, в какие вариантов выберите **создать новый профиль**.

1. В **выберите целевой объект публикации** диалоговом окне выберите **служба приложений в Linux**.

    ![Выберите службу приложений Azure](../deployment/media/quickstart-publish-linux.png "выберите службу приложений Azure")

1. Нажмите **Публиковать**. **Создать службу приложений** откроется диалоговое окно. Войдите, используя вы учетную запись Azure, при необходимости, а затем параметрам службы приложений по умолчанию заполните поля.

    ![Создание службы приложений](../deployment/media/quickstart-publish-settings-app-service-linux.png "Создание службы приложений Azure")

1. Выберите **Создать**. Visual Studio развертывает приложение на службу приложений Azure и загружает веб-приложение в браузере. Свойства проекта **публикации** области отображается URL-адрес сайта и другие сведения.

    ![Панель свойств со сводкой профиля публикации](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>Следующие шаги

В этом кратком руководстве вы узнали, как использовать Visual Studio для создания профиля публикации для развертывания в службе приложений на платформе Linux. Дополнительные сведения о публикации в Linux с помощью Azure можно.

> [!div class="nextstepaction"]
> [Службы приложений Linux](/azure/app-service/containers/app-service-linux-intro)