---
title: Развертывание приложений UWP | Документация Майкрософт
ms.custom: seodec18
ms.date: 01/16/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 02bfb1b4797973b3946405c38598409bf3247c70
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065744"
---
# <a name="deploy-uwp-apps-from-visual-studio"></a>Развертывание приложений UWP из Visual Studio

Функциональность развертывания Visual Studio выполняет сборку и регистрацию приложений универсальной платформы Windows, созданные с помощью Visual Studio на целевом устройстве. Конкретный способ регистрации зависит от того, является ли целевое устройство локальным или удаленным:

- Когда целевое устройство является локальным компьютером Visual Studio, Visual Studio регистрирует приложение из папки сборки.

- Когда целевое устройство является удаленным, Visual Studio копирует требуемые файлы на удаленный компьютер и регистрирует приложение на этом устройстве.

Развертывание осуществляется автоматически при отладке приложения из Visual Studio с помощью **начать отладку** параметр (клавиатуры: F5) или **Запуск без отладки** параметр (клавиатуры: CTRL + F5). Кроме того, приложение можно развернуть вручную. Это удобно в следующих сценариях:

- Специализированное тестирование на локальном или удаленном компьютере.

- Развертывание приложения, запускающего другое приложение, которое требует отладки.

- Развертывание приложения, для которого будет выполнена отладка, при его запуске другим приложением или методом.

## <a name="BKMK_How_to_deploy_a_Windows_Store_app"></a> Как развертывать приложения универсальной платформы Windows
 Ручное развертывание приложения не вызывает никаких сложностей:

1. Если вы выполняете развертывание на удаленное устройство, укажите имя или IP-адрес устройства на странице свойств для запускаемого проекта приложения. (Необходимые для этого действия перечислены ниже в этом разделе.)

2. На панели инструментов отладчика Visual Studio выберите цель развертывания в раскрывающемся списке рядом с кнопкой **Начать отладку** .

     ![Запуск на локальном компьютере](../debugger/media/vsrun_f5_local.png "VSRUN_F5_Local")

3. В меню **Сборка** выберите пункт **Развернуть**.

## <a name="BKMK_How_to_specify_a_remote_device"></a> Указание удаленного устройства

**Необходимые компоненты**

На удаленном устройстве Windows 10, необходимо включить [режим разработчика](/windows/uwp/get-started/enable-your-device-for-development). На устройствах Windows 10 Creators Update или более поздней версии, инструменты удаленной отладки устанавливаются автоматически при развертывании приложения. Дополнительные сведения см. в разделе [отладка установленного пакета приложения](../debugger/debug-installed-app-package.md).

> [!NOTE]
> В версии обновления pre разработчика Windows 10 инструменты удаленной отладки для Visual Studio должна быть установлена на удаленном устройстве и удаленный отладчик должен работать под управлением.

Развертывание использует канал сети удаленного отладчика для отправки файлов приложения на удаленное устройство.

#### <a name="to-specify-a-remote-device"></a>Порядок указания удаленного устройства

1. На странице свойств "Отладка" запускаемого проекта укажите имя или IP-адрес удаленной цели развертывания.

2. Чтобы открыть страницу свойств "Отладка", выберите проект в обозревателе решений и щелкните пункт **Свойства** в контекстном меню.

3. После этого выберите узел **Отладка** в окне страниц свойств.

4. Для **целевое устройство**выберите **удаленный компьютер**.

5. В разделе **удаленный компьютер**, нажмите кнопку **найти**.

6. Можно ввести имя или IP-адрес удаленного устройства, или можно выбрать устройство в **удаленного подключения** диалоговое окно.

    ![Выберите диалоговое окно подключения к удаленному отладчику](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")

    **Удаленного подключения** диалоговое окно устройства в подсети локальной сети и с любого устройства, непосредственно подключенные к компьютеру Visual Studio с помощью кабеля Ethernet.

   **Указание удаленного устройства в визуальном элементе C++ страница проекта**

   ![C&#43; &#43; свойства для удаленной отладки проекта](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")

7. Выберите **Удаленный отладчик** из списка **Отладчик для запуска** .

8. Введите имя сети для удаленного устройства в поле **Имя компьютера** . Либо вы можете выбрать стрелку вниз в поле, чтобы выбрать устройство в диалоговом окне "Выбрать подключение к удаленному отладчику".

   **Указание удаленного устройства на странице проекта Visual C# или Visual Basic**

   ![Свойства управляемого проекта для удаленной отладки](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")

9. Выберите **Удаленный компьютер** из списка **Целевое устройство** .

10. Введите сетевое имя удаленного устройства в поле **Удаленный компьютер** или щелкните **Найти** , чтобы выбрать устройство в диалоговом окне **Выбрать подключение к удаленному отладчику** .

## <a name="BKMK_Deployment_options"></a> Параметры развертывания

Вы можете задать следующие параметры развертывания на странице свойств "Отладка" запускаемого проекта.

**Разрешить замыкание на себя в локальной сети**

По соображениям безопасности UWP или [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] приложению, установленному стандартным образом не допускается выполнять сетевые вызовы на устройство, оно установлено. По умолчанию Visual Studio создает для развертываемого приложения исключение из этого правила. Это исключение позволяет тестировать процедуры обмена данными на одном компьютере. Прежде чем отправлять приложение в [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)], необходимо протестировать приложение без этого исключения.

Чтобы удалить исключение сетевого замыкания на себя из приложения, выполните следующие действия:

- На C# и Visual Basic странице свойств отладки, снимите флажок **разрешить сетевое замыкание на себя** "флажок".

- На C++ страница свойств отладки, задайте **разрешить сетевое замыкание на себя** значение **нет**.

**Не запускать, а отлаживать мой код при открытии (C# и Visual Basic) и запустить приложение (C++)**

Чтобы настроить развертывание на автоматический запуск сеанса отладки при запуске приложения, выполните следующие действия:

- На C# и страницу свойств отладки для Visual Basic, проверьте **не запускать, а отлаживать мой код при открытии** "флажок".

- На C++ страница свойств отладки, задайте **запустить приложение** значение **Да**.

## <a name="see-also"></a>См. также

- [Дополнительные параметры удаленного развертывания](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)
- [Отладка установленного пакета приложения](../debugger/debug-installed-app-package.md)
- [Запуск приложения из Visual Studio](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps)
