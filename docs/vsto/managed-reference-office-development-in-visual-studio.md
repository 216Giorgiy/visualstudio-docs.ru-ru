---
title: Справочник по управляемому коду (Разработка решений Office в Visual Studio)
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d6fa14bfffb500ab107523bc7444efa12f930e0c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646764"
---
# <a name="managed-reference-office-development-in-visual-studio"></a>Справочник по управляемому коду (Разработка решений Office в Visual Studio)
  В этом разделе содержится справочная документация по API для пространств имен и типов, используемых в проектах Office, предназначенных для [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] или [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. API справочную документацию по пространствам имен и типов, используемых в проектах Office, ориентированных на .NET Framework 3.5, см. в следующем справочном разделе документации Visual Studio: [ http://go.microsoft.com/fwlink/?LinkId=160658 ](http://go.microsoft.com/fwlink/?LinkId=160658).

> [!NOTE]
>  Занимаетесь разработкой решений, расширяющих возможности Office по [нескольких платформ](https://dev.office.com/add-in-availability)? Ознакомьтесь с новой [модель надстроек Office](https://dev.office.com/docs/add-ins/overview/office-add-ins). Надстройки Office имеют небольшого размера, по сравнению с надстройками VSTO и решения, и вы можете создавать их с помощью почти любой технологии веб-программирования, таких как HTML5, JavaScript, CSS3 и XML.

## <a name="in-this-section"></a>Содержание раздела
 <xref:Microsoft.Office.Tools>

 Содержит классы, общие для программирования решений Office. К ним относятся базовый класс для надстроек VSTO, классы для создания настраиваемых областей задач в настройках VSTO, классы для создания смарт-тегов в решениях Word и Excel и классы для создания панелей действий в настройках уровня документа.

 <xref:Microsoft.Office.Tools.Excel>

 Содержит элементы управления ведущего приложения и ведущие элементы, которые могут использоваться в решениях для Excel.

 <xref:Microsoft.Office.Tools.Excel.Controls>

 Содержит элементы управления Excel и элементы управления Windows Forms, которые могут использоваться в решениях для Excel.

 <xref:Microsoft.Office.Tools.Outlook>

 Содержит классы, используемые надстройками VSTO для Outlook, включая классы, используемые для создания настраиваемых областей формы.

 <xref:Microsoft.Office.Tools.Ribbon>

 Содержит классы, используемые для программного изменения настроек ленты, созданных с помощью конструктора лент.

 <xref:Microsoft.Office.Tools.Word>

 Содержит элементы управления ведущего приложения и ведущие элементы, которые могут использоваться в решениях для Word.

 <xref:Microsoft.Office.Tools.Word.Controls>

 Содержит элементы управления Word и элементы управления Windows Forms, которые могут использоваться в решениях для Word.

 <xref:Microsoft.VisualStudio.Tools.Applications>

 Содержит класс <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> и набор связанных классов кэшированных данных. Эти классы могут использоваться для изменения некоторых аспектов настроек уровня документа на компьютерах, на которых не установлен Microsoft Office.

 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>

 Содержит интерфейс <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> (который можно реализовать для создания *действий, выполняемых после развертывания* , для решения Office), исключения, которые могут возникать при установке решения Office, и другие API, которые являются частью инфраструктуры Visual Studio.

 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>

 Содержит основные исключения, которые могут создаваться [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], несколько классов, которые могут использоваться для кэширования данных в настройках уровня документа, и другие API, являющиеся частью инфраструктуры Visual Studio.

 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>

 Содержит классы задач MSBuild, которые используются для сборки проектов Office.

## <a name="see-also"></a>См. также
- [Visual Studio tools для среды](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [Начало работы &#40;разработка решений Office в Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Примеры разработки решений Office и пошаговые руководства](../vsto/office-development-samples-and-walkthroughs.md)
- [Разработка и создание решений Office](../vsto/designing-and-creating-office-solutions.md)
