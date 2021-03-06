---
title: Настройка репозитория Subversion
description: Использование Subversion в Visual Studio для Mac.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: 7dfb5c645125afc1485c1422909e52741507b327
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2019
ms.locfileid: "56953691"
---
# <a name="set-up-a-subversion-repository"></a>Настройка репозитория Subversion

Subversion — это централизованная _система управления версиями_, то есть все файлы и редакции находятся на одном сервере, откуда пользователи могут получить для изменения любую версию любого файла. Если файлы извлекаются из удаленного репозитория Subversion, пользователь получит моментальный снимок этого репозитория на соответствующий момент времени.

Чтобы использовать Subversion для управления версиями, ее нужно установить на компьютере. Чтобы проверить это, выполните следующую команду в терминале:

```bash
svn --version
```

Эта команда возвращает номер версии.

Если система Subversion еще не установлена, проще всего ее получить, установив _программы командой строки Xcode_. Используйте приведенную ниже команду для установки программ командной строки Xcode и Subversion.

```bash
xcode-select --install
```

После установки Subversion на компьютере выполните указанные ниже действия для публикации проекта в SVN.

1. Создайте бесплатный репозиторий SVN в сети. В этом примере используется [Assembla](https://app.assembla.com/). После создания будет предоставлен URL-адрес, используемый для подключения к репозиторию:

    ![Скопируйте URL-адрес SVN.](media/version-control-subversion1-sml.png)

2. Откройте или создайте проект Visual Studio для Mac.

3. Щелкните правой кнопкой мыши проект и выберите **Управление версиями > Publish in Version Control...** (Опубликовать в системе управления версиями):

    ![Начало публикации проекта](media/version-control-subversion2.png)

4. На вкладке **Подключение к репозиторию** выберите **Subversion** в верхнем раскрывающемся списке.

5. Введите URL-адрес из шага 1. После ввода URL-адреса остальные поля заполняются по умолчанию:

    ![Диалоговое окно для выбора репозитория и ввода сведений](media/version-control-subversion3.png)

7. Нажмите кнопку **ОК** и затем подтвердите, нажав кнопку **Опубликовать**.

7. Вам может быть предложено ввести свои учетные данные для сайта, где создан репозиторий, как показано ниже:

    ![Ввод учетных данных для репозитория Subversion](media/version-control-subversion5.png)

8. Все доступные команды управления версиями теперь должны отображаться в меню управления версиями.

## <a name="see-also"></a>См. также

- [Работа с Subversion](working-with-subversion.md)