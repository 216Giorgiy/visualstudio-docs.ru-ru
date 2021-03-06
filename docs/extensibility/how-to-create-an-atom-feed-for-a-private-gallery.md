---
title: Практическое руководство. Создание Atom веб-канала для закрытой коллекции | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 094bff5c761a45e936f14f79587b4846d3838610
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56722412"
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>Практическое руководство. Создание канала для закрытой коллекции Atom
Можно создать Atom RSS-канал в расположение в интрасети, содержащий расширения и добавить веб-канале, **расширения и обновления** качестве частной коллекции. Дополнительные сведения см. в разделе [закрытые коллекции](../extensibility/private-galleries.md).

## <a name="create-an-atom-feed"></a>Создать канал Atom
 Чтобы создать канал в качестве частной коллекции Atom, сначала собрать расширений (*.vsix* файлы) в папку. Если вы хотите, чтобы можно упорядочить их по вложенным папкам. Необходимо также следующие ресурсы:

- *Atom.xml* файл, который делает доступными расширения качестве частной коллекции. Сведения о подключении *atom.xml* файл **расширения и обновления**, см. в разделе [закрытые коллекции](../extensibility/private-galleries.md).

- Папку, содержащую все файлы изображений, которые были извлечены из расширений (например, снимки экрана). *Atom.xml* файл содержит относительных ссылок на эти образы, чтобы они были доступны в **расширения и обновления**.

  Например предположим, что следующие два модуля, собранными в папку:

- *Template_Wizard_239.VSIX*, который является пустой шаблон проекта VSIX.

- *SelectionHighlight.vsix*, которое представляет собой инструмент, чтобы выделить все экземпляры отдельного слова.

  Содержание *atom.xml* файла будет выглядеть следующим образом:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<feed xmlns="http://www.w3.org/2005/Atom">
  <title type="text" />
  <id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>
  <updated>2011-04-14T21:25:48Z</updated>
  <entry>
    <id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>
    <title type="text">Highlight all occurrences of selected word</title>
    <summary type="text">This extends the editor to highlight ....</summary>
    <published>2011-04-14T14:24:51-07:00</published>
    <updated>2011-04-14T14:24:22-07:00</updated>
    <author>
      <name>Microsoft</name>
    </author>
    <link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />
    <link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />
    <content type="application/octet-stream" src="SelectionHighlight.vsix" />
    <Vsix xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>
      <Version>1.31</Version>
      <References />
      <Rating xsi:nil="true" />
      <RatingCount xsi:nil="true" />
      <DownloadCount xsi:nil="true" />
    </Vsix>
  </entry>
  <entry>
    <id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>
    ...
  </entry>
</feed>
```

 Обратите внимание на то, что теги двух ссылок ссылаются на снимки экрана в папке созданного образов.

## <a name="see-also"></a>См. также
- [Закрытые коллекции](../extensibility/private-galleries.md)
