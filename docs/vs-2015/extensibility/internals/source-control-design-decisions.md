---
title: Исходный элемент управления проектные решения | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], design decisions
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 89d125dc52340e8528ee9692d5de00784632e6f2
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60047918"
---
# <a name="source-control-design-decisions"></a>Проектные решения для системы управления версиями
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

При реализации системы управления версиями для проектов должны быть рассмотрены следующие конструктивные решения.  
  
## <a name="will-information-be-shared-or-private"></a>Будут ли сведения о совместно используемой или закрытой?  
 Наиболее важное решение проектирования, можно выполнить — совместный доступ к информации и что является закрытым. Например список файлов для проекта является общим, но в этот список файлов, некоторым пользователям может потребоваться наличие личные файлы. Параметры компилятора используются совместно, но обычно закрытый запускаемого проекта. Параметры являются исключительно общего, общих с помощью переопределения или исключительно закрытый. По своей структуре личные элементы, такие, как решение пользовательские параметры (.suo) файлы, не проверяются в [!INCLUDE[vsvss](../../includes/vsvss-md.md)]. Убедитесь, что для хранения конфиденциальных сведений в личные файлы, например SUO-файл или определенного закрытого файла можно создать, например,. csproj.user файл для Visual C# или. vbproj.user-файл для Visual Basic.  
  
 Это решение не разрешены и могут выполняться на основе по элементу.  
  
## <a name="will-the-project-include-special-files"></a>Будет ли проект включает специальные файлы?  
 Другой важное решение проектирования является ли структуры проекта используются специальные файлы. Специальные файлы являются скрытыми, лежащих в основе файлов, которые являются видимыми в обозревателе решений и возврат и извлечение диалоговые окна. Если вы используете специальные файлы, придерживайтесь следующих рекомендаций.  
  
1. Не связывайте специальные файлы с корневой узел проекта, то есть с проектом файл сам. Файл проекта должен быть один файл.  
  
2. При добавлении, удалены или переименованы в проекте, соответствующий специальные файлы <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> события должны создаваться с установленным флагом, который указывает это специальные файлы. Эти события вызываются средой в ответ на вызов соответствующего проекта <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> методы.  
  
3. Когда проект или редактор вызывает <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> для файла, специальные файлы, связанные с этим файлом не извлекаются автоматически. Передайте специальные файлы в вместе с родительским файлом. Среда будет обнаружения связи между всеми файлами, которые передаются в и соответствующим образом скрыть специальные файлы в пользовательском Интерфейсе извлечения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [Поддержка системы управления версиями](../../extensibility/internals/supporting-source-control.md)
