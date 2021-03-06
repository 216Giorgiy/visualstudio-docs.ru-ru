---
title: 'Предупреждение: зависимость &#39;файл&#39; в проекте &#39;проекта&#39; невозможно скопировать в каталог выполнения, поскольку она перезапишет ссылку &#39;файл. &#39; | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
f1_keywords:
- vs.tasklisterror.copy_version_warning
ms.assetid: 116819f3-a4d4-48b5-9e71-7c54660d38ef
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d2f2a70df72f6dfcdc8946ca2f5afec9efa21a65
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60059244"
---
# <a name="warning-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-overwrite-the-reference-39file39"></a>Предупреждение: зависимость &#39;файл&#39; в проекте &#39;проекта&#39; невозможно скопировать в каталог выполнения, поскольку она перезапишет ссылку &#39;файл.&#39;
Существует конфликт между зависимостями. Чтобы запустить приложение, необходимо скопировать несколько разных файлов сборки с одним именем в каталог bin. Каталог запуска может разрешить конфликт, так как одна из зависимостей является первичной ссылкой.  
  
 Дважды щелкните этот элемент списка задач, чтобы перейти к конфликтующему узлу первичной ссылки.  
  
 Это предупреждение выводится, когда возникший конфликт зависимостей был устранен путем добавления одной из конфликтующих зависимостей в качестве ссылки. Или, возможно, у вас была ссылка на версию 1, а затем вы добавили вторую ссылку, которая сама ссылается на версию 2 первой ссылки.  
  
 Другими словами, эта ошибка происходит потому, что проекты в решении ссылаются друг на друга, но эти ссылки были созданы как файловые ссылки (с помощью кнопки **Обзор** в диалоговом окне [Добавление ссылки](http://msdn.microsoft.com/2feb0fe2-0805-4cc9-8cba-b0315849dfb7) ), а не как ссылки проекта на проект (с помощью вкладки **Проект** в диалоговом окне **Добавление ссылки** ). Преимущество ссылки проекта на проект состоит в том, что она создает зависимость между проектами в системе сборки. Зависимый проект будет собран, если он был изменен с момента последней сборки ссылающегося проекта. Ссылка на файл не создает зависимость сборки, поэтому можно собрать ссылающийся проект, не создавая зависимый, и ссылка может устареть. Проект может ссылаться на ранее собранную версию проекта. Это может привести к тому, что в каталоге bin потребуется несколько версий одной библиотеки DLL, что невозможно. В результате будет выведено это сообщение об ошибке.  
  
 Это сообщение появляется каждый раз при возникновении конфликта в каталоге bin, и работа приложения может быть нарушена. Даже несмотря на то, что вы, возможно, решили эту проблему, данное предупреждение будет по-прежнему отображаться, так как системе проектов не удается определить, будет ли версия зависимости правильно работать со всеми компонентами.  
  
 **Чтобы исправить эту ошибку**  
  
- Скопируйте один (или ни одного) файл сборки в каталог bin. Для этого поместите файлы сборки в глобальный кэш сборок. Глобальный кэш сборок разрешит конфликты имен файлов. Локальные копии файла сборки созданы не будут, поскольку среде CLR известно, как находить сборки в глобальном кэше сборок. Дополнительные сведения см. в разделах [Working with Assemblies and the Global Assembly Cache](http://msdn.microsoft.com/library/8a18e5c2-d41d-49ef-abcb-7c27e2469433) и [Error: the dependency 'file' in project 'project' cannot be copied to the run directory because it would conflict with dependency 'file'](/visualstudio/misc/error-dependency-file?view=vs-2015).  
  
## <a name="see-also"></a>См. также  
 [Управление ссылками в проекте](../ide/managing-references-in-a-project.md)   
 [Глобальный кэш сборок](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)   
 [Практическое руководство. Создание и удаление зависимостей проекта](../ide/how-to-create-and-remove-project-dependencies.md)