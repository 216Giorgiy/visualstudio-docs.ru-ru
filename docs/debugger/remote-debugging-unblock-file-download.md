---
title: Разблокировать загрузки инструментов удаленной отладки
ms.date: 07/19/2018
ms.topic: troubleshooting
helpviewer_keywords:
- remote debugging, unblock download
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a243033bf5831952d83fdf688302651e02b76b7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54988146"
---
# <a name="how-to-unblock-the-download-of-the-remote-tools-on-windows-server"></a>Как выполнить Разблокировать загрузки инструментов удаленной отладки на Windows Server

Параметры безопасности по умолчанию в Internet Explorer в Windows Server может быть слишком много времени загрузки компонентов, таких как инструменты удаленной отладки.

* Конфигурация усиленной безопасности включен в Internet Explorer, что не позволяет открывать веб-сайтов и доступ к веб-ресурсы, если явно не разрешены домен, содержащий ресурс (то есть доверенные). Несмотря на то, что вы можете отключить этот параметр, не рекомендуется, так как он может представлять угрозу безопасности.

* В Windows Server 2016, значения по умолчанию **обозревателя** > **безопасности** > **Internet**  >   **Пользовательский уровень** > **загружает** также отключает файлам загрузки. Если вы решили загрузить инструменты удаленной отладки непосредственно на сервере Windows, необходимо включить загрузку файлов.

Чтобы скачать средства в Windows Server, рекомендуется один из следующих:

* Скачать инструменты удаленной отладки на другом компьютере, такие как одной работающей Visual Studio, а затем скопируйте *.exe* файл для Windows Server.

* Запуск удаленного отладчика [из общей папки](../debugger/remote-debugging.md#fileshare_msvsmon) на компьютере Visual Studio.

* Загрузить инструменты удаленной отладки непосредственно на сервере Windows и следуйте указаниям, чтобы добавить надежные сайты. Современные веб-сайты включаются много сторонних ресурсов, чтобы это может привести многочисленные запросы. Кроме того все перенаправленные ссылки может потребоваться добавить вручную. Вы можете добавить некоторые из надежных узлов перед началом загрузки. Перейдите к **свойства обозревателя > Безопасность > Надежные сайты > сайты** и добавьте следующие узлы.

  * visualstudio.microsoft.com
  * download.visualstudio.microsoft.com
  * о: пустое

  Для более старых версий отладчика на my.visualstudio.com добавьте эти дополнительные сайты, чтобы убедиться в том, что выполнено успешно, это имя входа:

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * my.visualstudio.com
  * login.microsoftonline.com
  * login.live.com
  * secure.aadcdn.microsoftonline-p.com
  * MSFT.STS.Microsoft.com
  * AUTH.gfx.MS
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * query.prod.cms.rt.microsoft.com

    Если вы решили такие домены необходимо добавить во время загрузки инструментов удаленной отладки, а затем выберите **добавить** при появлении запроса.

    ![Заблокированные содержимого диалоговое окно](../debugger/media/remotedbg-blocked-content.png)

    При загрузке программного обеспечения, вы получаете некоторые дополнительные запросы, чтобы предоставить разрешение для загрузки различные сценарии веб-сайт и ресурсы. На my.visualstudio.com мы рекомендуем добавить дополнительные домены, чтобы убедиться, что вход выполнен успешно.