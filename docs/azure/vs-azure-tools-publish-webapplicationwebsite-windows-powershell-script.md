---
title: Publish-WebApplicationWebSite (сценарий Windows PowerShell) | Документация Майкрософт
description: Узнайте, как опубликовать веб-проект на веб-сайте Azure. Этот сценарий создает необходимые ресурсы в подписке Azure, если они еще не созданы.
author: ghogen
manager: jillfra
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: dacc30785fc26e2f07bf5265eda8490d24333154
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913552"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (сценарий Windows PowerShell)
## <a name="syntax"></a>Синтаксис
Этот сценарий публикует веб-проект на веб-сайте Azure и создает необходимые ресурсы в подписке Azure, если они еще не созданы.

    Publish-WebApplicationWebSite
    –Configuration <configuration>
    -SubscriptionName <subscriptionName>
    -WebDeployPackage <packageName>
    -DatabaseServerPassword @{Name = "name"; Password = "password"}
    -SendHostMessagesToOutput
    -Verbose


## <a name="configuration"></a>Параметр Configuration
Путь к файлу конфигурации JSON, содержащему подробные сведения о развертывании.

| Параметр | Значение по умолчанию |
| --- | --- |
| Псевдонимы |Нет |
| Обязательный? |true |
| Положение |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="subscriptionname"></a>Параметр SubscriptionName
Имя подписки Azure, в которой необходимо создать веб-сайт.

| Параметр | Значение по умолчанию |
| --- | --- |
| Псевдонимы |Нет |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="webdeploypackage"></a>Параметр WebDeployPackage
Путь к пакету веб-развертывания для публикации на веб-сайте. Этот пакет можно создать с помощью мастера «Публикация веб-сайта» в Visual Studio. Дополнительные сведения можно найти в статье [Начало работы с облачными службами Azure и ASP.NET](http://go.microsoft.com/fwlink/p/?LinkID=623089).

| Параметр | Значение по умолчанию |
| --- | --- |
| Псевдонимы |Нет |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="databaseserverpassword"></a>Параметр DatabaseServerPassword
Имя и пароль администратора базы данных SQL в Azure.

| Параметр | Значение по умолчанию |
| --- | --- |
| Псевдонимы |Нет |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |Нет |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="sendhostmessagestooutput"></a>Параметр SendHostMessagesToOutput
Если установлено значение true, оправляет сообщения из сценария в поток вывода.

| Параметр | Значение по умолчанию |
| --- | --- |
| Псевдонимы |Нет |
| Обязательный? |False |
| Позиция |именованная |
| Значение по умолчанию |False |
| Принимает входные данные конвейера? |False |
| Принимает подстановочные знаки? |False |

## <a name="remarks"></a>Примечания
Подробное описание того, как использовать сценарий для создания сред разработки и тестирования, см. в статье [Использование скриптов Windows PowerShell для публикации в среды разработки и тестирования](vs-azure-tools-publishing-using-powershell-scripts.md).

В файле конфигурации JSON указаны данные объектов, которые необходимо развернуть. Он содержит сведения, указанные при создании проекта, такие как имя веб-сайта и имя пользователя. Он также содержит сведения о базе данных, которую нужно подготовить (если она есть). В следующем коде показан пример файла конфигурации JSON.

    {
        "environmentSettings": {
            "webSite": {
                "name": "WebApplication10554",
                "location": "West US"
            },
            "databases": [
                {
                    "connectionStringName": "DefaultConnection",
                    "databaseName": "WebApplication10554_db",
                    "serverName": "iss00brc88",
                    "user": "sqluser2",
                    "password": "",
                    "edition": "",
                    "size": "",
                    "collation": "",
                    "location": "West US"
                }
            ]
        }
    }

В файле конфигурации JSON можно изменить объекты, которые подлежат развертыванию. Раздел webSite является обязательным, а раздел database — необязательным.

## <a name="next-steps"></a>Следующие шаги
Дополнительные сведения см. в статье [Publish-WebApplicationVM (сценарий Windows PowerShell)](vs-azure-tools-publish-webapplicationvm.md)
