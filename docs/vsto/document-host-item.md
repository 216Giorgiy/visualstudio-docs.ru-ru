---
title: Ведущий элемент документа
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio]
- documents [Office development in Visual Studio], document host items
- document host items
- Word [Office development in Visual Studio], Word documents
- Word [Office development in Visual Studio]
- Word documents
- host items [Office development in Visual Studio], Document
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8710fb703b353b267e7057973865cf845ebf79a9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599624"
---
# <a name="document-host-item"></a>Ведущий элемент документа
  Ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> является типом, который расширяет тип <xref:Microsoft.Office.Interop.Word.Document> из основной сборки взаимодействия для Word. Ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> предоставляет все свойства, методы и события объекта <xref:Microsoft.Office.Interop.Word.Document> , но также предоставляет дополнительные события и выступает в роли контейнера для элементов управления ведущего приложения и элементов управления Windows Forms.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 В проектах уровня документа имеется ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> по умолчанию, который представляет документ в проекте. В проектах надстройки VSTO во время выполнения можно создавать ведущие элементы <xref:Microsoft.Office.Tools.Word.Document> .

## <a name="understand-the-document-host-item-in-document-level-projects"></a>Понять, ведущий элемент документа в проектах уровня документа
 Для доступа к документу в проекте используйте класс `ThisDocument` . При создании проекта уровня документа Visual Studio создает класс `ThisDocument` в качестве связи между Word и кодом настройки. Класс `ThisDocument` обеспечивает доступ к членам ведущего элемента <xref:Microsoft.Office.Tools.Word.Document> для выполнения основных задач по настройке, например для запуска кода при открытии или закрытии документа. Вы также можете использовать эти классы для добавления элементов управления в документы. Используя различные сочетания элементов управления и создавая код, можно привязать элементы управления к данным, собирать сведения от пользователя и реагировать на действия пользователя. Дополнительные сведения см. в разделе [программирование настроек уровня документа](../vsto/programming-document-level-customizations.md).

 Класс `ThisDocument` предоставляет место, в котором можно начать создание кода в проекте. Поскольку этот класс предоставляет все свойства, методы и события, что и объект <xref:Microsoft.Office.Interop.Word.Document> в основной сборке взаимодействия для Word, вы также можете использовать `ThisDocument` для доступа к объектной модели Word. Дополнительные сведения см. в разделе [обзор объектной модели Word](../vsto/word-object-model-overview.md).

### <a name="limitations-of-the-document-host-item-in-document-level-projects"></a>Ограничения ведущих элементов документа в проектах уровня документа
 Проект уровня документа может содержать только один ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> (то есть класс `ThisDocument` ). Вы не можете добавлять новые <xref:Microsoft.Office.Tools.Word.Document> ведущих элементов в проект во время разработки, и вы не можете создавать новые <xref:Microsoft.Office.Tools.Word.Document> ведущие элементы во время выполнения из настройки уровня документа.

 При создании нового документа Word во время выполнения, он будет иметь тип <xref:Microsoft.Office.Interop.Word.Document>. Поскольку это не ведущий элемент, он не может содержать никаких элементов управления ведущего приложения или элементов управления Windows Forms. Дополнительные сведения о создании документов во время выполнения, см. в разделе [как: Программное создание документов](../vsto/how-to-programmatically-create-new-documents.md).

## <a name="understand-document-host-items-in-application-level-projects"></a>Понять ведущих элементов документа в проектах уровня приложения
 В проектах надстроек VSTO можно создавать ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> во время выполнения для любого документа, открытого в Word. Вы можете использовать ведущий элемент <xref:Microsoft.Office.Tools.Word.Document> для добавления элементов управления в связанный документ или для обработки событий, которые недоступны в объектах <xref:Microsoft.Office.Interop.Word.Document> .

 Для создания ведущего элемента <xref:Microsoft.Office.Tools.Word.Document> используйте метод `GetVstoObject`. Дополнительные сведения см. в разделе [документов расширения Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="see-also"></a>См. также
- [Ведущие элементы и элементы управления](../vsto/host-items-and-host-controls-overview.md)
- [Автоматизация Word с помощью расширенных объектов](../vsto/automating-word-by-using-extended-objects.md)
- [Обзор объектной модели Word](../vsto/word-object-model-overview.md)
- [Программные ограничения ведущих элементов и элементов управления ведущего приложения](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
- [Расширение документов Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
