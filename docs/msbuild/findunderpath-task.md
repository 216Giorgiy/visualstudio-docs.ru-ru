---
title: Задача FindUnderPath | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#FindUnderPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FindUnderPath task
- FindUnderPath task [MSBuild]
ms.assetid: 3c6d58b0-36e8-47aa-bfca-b73dd2045d91
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c22e2465b79faa68f8789cefeeb181c2e15b73b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602195"
---
# <a name="findunderpath-task"></a>FindUnderPath - задача
Определяет, какие элементы в указанной коллекции имеют пути в указанной папке или на более низком уровне.

## <a name="parameters"></a>Параметры
В следующей таблице приводятся параметры задачи `FindUnderPath` .

|Параметр|Описание|
|---------------|-----------------|
|`Files`|Необязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Указывает файлы, пути которых следует сравнивать с путем, заданным в параметре `Path`.|
|`InPath`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Содержит элементы, найденные по указанному пути.|
|`OutOfPath`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Содержит элементы, не найденные по указанному пути.|
|`Path`|Обязательный параметр <xref:Microsoft.Build.Framework.ITaskItem> .<br /><br /> Указывает путь к папке для использования в качестве ссылки.|
|`UpdateToAbsolutePaths`|Необязательный параметр `Boolean` .<br /><br /> Если имеет значение true, пути к выходным элементам изменяются на абсолютные.|

## <a name="remarks"></a>Примечания
Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Пример
В этом примере задача `FindUnderPath` используется для определения наличия в файлах, содержащихся в элементе `MyFiles`, путей ниже указанного в свойстве `SearchPath`. После выполнения задачи элемент `FilesNotFoundInPath` содержит файл *File1.txt*, а элемент `FilesFoundInPath` содержит файл *File2.txt*.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <ItemGroup>
        <MyFiles Include="C:\File1.txt" />
        <MyFiles Include="C:\Projects\MyProject\File2.txt" />
    </ItemGroup>

    <PropertyGroup>
        <SearchPath>C:\Projects\MyProject</SearchPath>
    </PropertyGroup>

    <Target Name="FindFiles">
        <FindUnderPath
            Files="@(MyFiles)"
            Path="$(SearchPath)">
            <Output
                TaskParameter="InPath"
                ItemName="FilesFoundInPath" />
            <Output
                TaskParameter="OutOfPath"
                ItemName="FilesNotFoundInPath" />
        </FindUnderPath>
    </Target>

</Project>
```

## <a name="see-also"></a>См. также
- [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)
- [Задачи](../msbuild/msbuild-tasks.md)
- [Основные понятия MSBuild](../msbuild/msbuild-concepts.md)
