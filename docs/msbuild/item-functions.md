---
title: Функции элементов | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d01de837deb5141b4b0bdbb7bebcb50412826b1f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56617162"
---
# <a name="item-functions"></a>Функции элементов
Начиная с MSBuild 4.0, код в задачах и целевых объектах может вызывать функции элементов для получения сведений об элементах в проекте. Эти функции упрощают получение элементов Distinct() и выполняются быстрее, чем перебор элементов.

## <a name="string-item-functions"></a>Строковые функции элементов
Строковые методы и свойства в .NET Framework можно использовать для обработки любого значения элемента. Для методов <xref:System.String> укажите имя метода. Для свойств <xref:System.String> укажите имя свойства после "get_".

В элементах, имеющих несколько строк, строковый метод или строковое свойство выполняются для каждой строки.

Следующий пример показывает, как использовать строковые функции элементов.

```xml
<ItemGroup>
    <theItem Include="andromeda;tadpole;cartwheel" />
</ItemGroup>

<Target Name = "go">
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />
    <Message Text="Length   @(theItem->get_Length())" />
    <Message Text="Chars    @(theItem->get_Chars(2))" />
</Target>

  <!--
  Output:
    IndexOf  3;-1;2
    Replace  andromeda;pinwheel;cartwheel
    Length   9;7;9
    Chars    d;d;r
  -->
```

## <a name="intrinsic-item-functions"></a>Встроенные функции элементов
В следующей таблице перечислены доступные для элементов встроенные функции.

|Функция|Пример|Описание|
|--------------|-------------|-----------------|
|`Count`|`@(MyItem->Count())`|Возвращает количество элементов.|
|`DirectoryName`|`@(MyItem->DirectoryName())`|Возвращает эквивалент `Path.DirectoryName` для каждого элемента.|
|`Distinct`|`@(MyItem->Distinct())`|Возвращает элементы, имеющие уникальные значения `Include`. Метаданные игнорируются. При сравнении регистр не учитывается.|
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|Возвращает элементы, имеющие уникальные значения `itemspec`. Метаданные игнорируются. При сравнении учитывается регистр.|
|`Reverse`|`@(MyItem->Reverse())`|Возвращает элементы в обратном порядке.|
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|Возвращает `boolean`, чтобы указать, имеет ли какой-либо элемент заданное имя и значение метаданных. При сравнении регистр не учитывается.|
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|Возвращает элементы с очищенными метаданными. Сохраняется только `itemspec`.|
|`HasMetadata`|`@(MyItem->HasMetadata("MetadataName"))`|Возвращает элементы, для которых указано имя метаданных. При сравнении регистр не учитывается.|
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|Возвращает значения метаданных, имеющие имя метаданных.|
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue"))`|Возвращает элементы, для которых указано имя и значение метаданных. При сравнении регистр не учитывается.|

Следующий пример показывает, как использовать встроенные функции элементов.

```xml
<ItemGroup>
    <TheItem Include="first">
        <Plant>geranium</Plant>
    </TheItem>
    <TheItem Include="second">
        <Plant>algae</Plant>
    </TheItem>
    <TheItem Include="third">
        <Plant>geranium</Plant>
    </TheItem>
</ItemGroup>

<Target Name="go">
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />
    <Message Text=" " />
    <Message Text="Count:   @(theItem->Count())" />
    <Message Text="Reverse: @(theItem->Reverse())" />
</Target>

  <!--
  Output:
    MetaData:    geranium;algae;geranium
    HasMetadata: first;second;third
    WithMetadataValue: first;third

    Count:   3
    Reverse: third;second;first
  -->
```

## <a name="see-also"></a>См. также
- [Элементы](../msbuild/msbuild-items.md)
