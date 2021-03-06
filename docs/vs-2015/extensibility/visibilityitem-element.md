---
title: Элемент VisibilityItem | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f6f71e145282d1d6e340060b9798ca54c9af9f4e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58980227"
---
# <a name="visibilityitem-element"></a>Элемент VisibilityItem
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`VisibilityItem` Элемент определяет статические видимость команды и панели инструментов. Каждая запись определяет команду или меню, а также контекст пользовательского интерфейса связанная команда. Visual Studio обнаруживает команд, меню и панелей инструментов и их видимости без загрузки пакетов VSPackage, который их определения. Интегрированная среда разработки использует <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> метод, чтобы определить, активен ли контекст пользовательского интерфейса команды.  
  
 После загрузки VSPackage, Visual Studio ожидает, что видимость команды будет определяться VSPackage, а не `VisibilityItem`. Чтобы определить видимость вашей команды, можно реализовать <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> обработчик событий или <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> метод, в зависимости от реализации вашей команды.  
  
 Команда или меню, которое содержит `VisibilityItem` элемент появляется, только когда связанный контекст является активным. Одной команды, меню или панели инструментов можно связать с одной или нескольких контекстов пользовательского интерфейса команды, включив запись для каждого сочетания контекст команды. Если при наличии нескольких контекстов пользовательского интерфейса команды связана команду или меню, затем команду или меню отображается при активном любого из контекстов пользовательского интерфейса связанная команда.  
  
 `VisibilityItem` Элемент применяется только к команд, меню и панелей инструментов, а не группам. Элемент, который не имеет связанный с ним `VisibilityItem` элемент является видимым, каждый раз, когда его родительском меню активен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|guid|Обязательный. Идентификатор GUID идентификатор GUID и идентификатора команды.|  
|id|Обязательный. Идентификатор GUID и идентификатора идентификатор команды.|  
|контекст|Обязательный. Контекст пользовательского интерфейса, в котором отображается команда.|  
|Условие|Необязательный параметр. См. в разделе [условные атрибуты](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` Элемент определяет видимость статических групп, команд и панелей инструментов.|  
  
## <a name="remarks"></a>Примечания  
 Определенные стандартные контексты пользовательского интерфейса Visual Studio в *путь установки Visual Studio SDK*\VisualStudioIntegration\Common\Inc\vsshlids.h также файл в качестве <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> и <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> классы. Более полный набор контекстов пользовательского интерфейса определен в <xref:Microsoft.VisualStudio.VSConstants> класса.  
  
## <a name="example"></a>Пример  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [Элемент VisibilityConstraints](../extensibility/visibilityconstraints-element.md)   
 [Файлы таблицы команд Visual Studio (VSCT-файлы)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
