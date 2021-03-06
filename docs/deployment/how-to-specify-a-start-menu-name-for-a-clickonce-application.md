---
title: Практическое руководство. Задание имени в меню Пуск для ClickOnce-приложения | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Start menu resource name
- Start menu name
- ClickOnce deployment, Start menu name
ms.assetid: 4b5183b2-2fd4-4433-9310-4a73bb12c4e3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4ef1675480182796e1fe8bbe29baa5ed6a9d5f63
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085120"
---
# <a name="how-to-specify-a-start-menu-name-for-a-clickonce-application"></a>Практическое руководство. Задание имени в меню "Пуск" для приложения ClickOnce
Когда [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] установлено приложение для использования сетевой и автономный режим, чтобы добавляется запись **запустить** меню и **Установка и удаление программ** списка. По умолчанию, отображаемое имя совпадает с именем сборки приложения, но отображаемое имя можно изменить, задав **название продукта** в **параметры публикации** диалоговое окно.

 **Название продукта** будут отображаться на *publish.htm* странице; для установленного автономного приложения, он будет использоваться имя элемента в **запустить** меню, а также будет имя, которое отображается в **Установка и удаление программ**.

 **Имя издателя** будут отображаться на *publish.htm* страницу выше **название продукта**, и для установленного автономного приложения, он также будет имя папки, которая содержит приложение значок в **запустить** меню.

 Справочник по ярлык программы или приложения меню Пуск создается в *%appdata%\Microsoft\Windows\Start Menu\Programs\\< имя издателя\>*. Ярлык программы или приложения ссылка имеет то же имя, что имя продукта.

 Можно задать **название продукта** и **имя издателя** свойств в **параметры публикации** диалоговом окне на **публикации** страницы из **в конструкторе проектов**.

### <a name="to-specify-a-start-menu-name"></a>Для указания имени меню "Пуск"

1. Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**.

2. Перейдите на вкладку **Публикация**.

3. Нажмите кнопку **параметры** кнопку, чтобы открыть **параметры публикации** диалоговое окно.

4. Нажмите кнопку **описание**.

5. В **параметры публикации** диалогового окна введите имя, отображаемое в **название продукта**.

6. При необходимости можно ввести имя издателя в **имя издателя**.

## <a name="see-also"></a>См. также
- [Публикация приложений ClickOnce](../deployment/publishing-clickonce-applications.md)
- [Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)