---
title: Привязка данных к элементам управления в решениях Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio], connecting to data
- data, data binding
- data binding
- data binding, Office solutions
- data binding, controls
- Office applications [Office development in Visual Studio], data binding
- controls, data binding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1bbcbc2411d261b4ddec9423896dc21acc3e0033
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60073739"
---
# <a name="bind-data-to-controls-in-office-solutions"></a>Привязка данных к элементам управления в решениях Office
  Вы можете привязать элементы управления Windows Forms и *элементы управления ведущего приложения* в документе Microsoft Office Word или листе Microsoft Office Excel к источнику данных, чтобы эти элементы управления автоматически отображали данные. Можно привязывать данные к элементам управления в проектах уровня документа и уровня приложения.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Элементы управления ведущего приложения расширяют объекты, которые находятся в объектных моделях Word и Excel, такие как элементы управления контентом в Word и именованные диапазоны в Excel. Дополнительные сведения см. в разделе [ведущие элементы и размещать элементы управления](../vsto/host-items-and-host-controls-overview.md).

 Элементы управления Windows Forms и элементы управления ведущего приложения используют модель привязки данных Windows Forms, которая поддерживает как *простую привязку данных* , так и *сложную привязку данных* к источникам данных, например к таблицам и наборам данных. Полные сведения о модели привязки данных в Windows Forms, см. в разделе [привязки данных и Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).

 ![ссылка на видео](../vsto/media/playvideo.gif "ссылка на видео") демонстрационные видеоматериалы см. в разделе [инструкции: Использование данных базы данных в Excel? ](http://go.microsoft.com/fwlink/?LinkID=130287).

## <a name="simple-data-binding"></a>Простая привязка данных
 Простая привязка данных присутствует, когда свойство элемента управления привязывается к одному элементу данных, например к значению в таблице данных. Например, элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> имеет свойство <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> , которое можно привязать к полю в наборе данных. При изменении поля в наборе данных также изменяется значение в именованном диапазоне. Все элементы управления ведущего приложения, за исключением элемента управления <xref:Microsoft.Office.Tools.Word.XMLNodes> , поддерживают простую привязку данных. Элемент управления <xref:Microsoft.Office.Tools.Word.XMLNodes> представляет собой коллекцию, и поэтому он не поддерживает привязку данных.

 Чтобы выполнить простую привязку данных к элементу управления ведущего приложения, добавьте <xref:System.Windows.Forms.Binding> в свойство `DataBindings` этого элемента управления. Объект <xref:System.Windows.Forms.Binding> представляет простую привязку между значением свойства элемента управления и значением элемента данных.

 Следующий пример демонстрирует способ привязки свойства <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> к элементу данных в проекте уровня документа.

 [!code-vb[Trin_BindableComponent#4](../vsto/codesnippet/VisualBasic/Trin_BindableComponent/Sheet1.vb#4)]
 [!code-csharp[Trin_BindableComponent#4](../vsto/codesnippet/CSharp/Trin_BindableComponent/Sheet1.cs#4)]

 Пошаговые руководства с примерами простой привязки данных, см. в разделе [Пошаговое руководство: Простая привязка данных в проекте уровня документа](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md) для проекта уровня документа и [Пошаговое руководство: Простая привязка данных в проекте надстройки VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md) для проекта надстройки VSTO.

## <a name="complex-data-binding"></a>Сложная привязка данных
 Сложная привязка данных присутствует, когда свойство элемента управления привязывается к нескольким элементам данных, например к нескольким столбцам в таблице данных. Элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> для Excel — единственный элемент управления ведущего приложения, который поддерживает сложную привязку данных. Существует также множество элементов управления Windows Forms, поддерживающих сложную привязку данных, например элемент управления <xref:System.Windows.Forms.DataGridView> .

 Для выполнения сложной привязки данных задайте в свойстве `DataSource` элемента управления объект источника данных, который поддерживается сложной привязкой данных. Например, свойство <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> элемента управления <xref:Microsoft.Office.Tools.Excel.ListObject> можно привязать к нескольким столбцам в таблице данных. Все данные в таблице данных отображаются в элементе управления <xref:Microsoft.Office.Tools.Excel.ListObject> , и при изменении данных в таблице данных свойство <xref:Microsoft.Office.Tools.Excel.ListObject> также изменяется. Список источников данных, которые можно использовать для сложной привязки данных, см. в разделе [источников данных, поддерживаемые Windows Forms](/dotnet/framework/winforms/data-sources-supported-by-windows-forms).

 В следующем примере кода создается <xref:System.Data.DataSet> с двумя объектами <xref:System.Data.DataTable> и заполняется данными одна из таблиц. Затем этот код привязывает <xref:Microsoft.Office.Tools.Excel.ListObject> к таблице, содержащей данные. Этот пример предназначен для проекта уровня документа Excel.

 [!code-csharp[Trin_ExcelListObject#18](../vsto/codesnippet/CSharp/Trin_ExcelListObject/Trin_ExcelListObject.cs#18)]
 [!code-vb[Trin_ExcelListObject#18](../vsto/codesnippet/VisualBasic/Trin_ExcelListObject/Sheet1.vb#18)]

 Пошаговые руководства с примерами сложной привязки данных, см. в разделе [Пошаговое руководство: Сложная привязка данных в проекте уровня документа](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md) для проекта уровня документа и [Пошаговое руководство: Сложная привязка данных в проекте надстройки VSTO](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md) для проекта надстройки VSTO.

## <a name="display-data-in-documents-and-workbooks"></a>Отображение данных в документах и книгах
 В проектах уровня документа с помощью окна **Источники данных** можно легко добавлять элементы управления с привязкой к данным в документы или книги, так же, как это делается для форм Windows Forms. Дополнительные сведения об использовании **источников данных** окно, см. в разделе [управляет привязки Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) и [добавляются новые источники данных](../data-tools/add-new-data-sources.md).

### <a name="drag-controls-from-the-data-sources-window"></a>Перетащите элементы управления из окна источников данных
 Элемент управления создается в документе, когда вы перетаскиваете в него объект из окна **Источники данных** . Тип создаваемого элемента управления зависит от того, связывается ли один столбец данных или несколько столбцов данных.

 В Excel элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> создается в листе для каждого отдельного поля, а элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> создается для каждого диапазона данных, содержащего несколько строк и столбцов. Вы можете изменить этот порядок по умолчанию, выбрав таблицу или поле в окне **Источники данных** , а затем выбрав другой элемент управления из раскрывающегося списка.

 Элемент управления <xref:Microsoft.Office.Tools.Word.ContentControl> добавляется в документ. Тип элемента управления контентом зависит от типа данных выбранного поля.

### <a name="bind-data-in-document-level-projects-at-design-time"></a>Привязка данных в проектах уровня документа во время разработки
 В следующих разделах содержатся примеры привязки данных во время разработки.

- [Практическое руководство. Заполнение листов данными из базы данных](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)

- [Практическое руководство. Заполнение документов данными из базы данных](../vsto/how-to-populate-documents-with-data-from-a-database.md)

- [Практическое руководство. Заполнение документов данными из объектов](../vsto/how-to-populate-documents-with-data-from-objects.md)

- [Практическое руководство. Заполнение документов данными из служб](../vsto/how-to-populate-documents-with-data-from-services.md)

- [Практическое руководство. Прокрутить записи базы данных на листе](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)

### <a name="bind-data-in-vsto-add-in-projects"></a>Привязка данных в проектах надстройки VSTO
 В проектах надстройки VSTO можно добавить элементы управления только во время выполнения. Ниже приведены примеры привязки данных во время выполнения.

- [Пошаговое руководство: Простая привязка данных в проекте надстройки VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)

- [Пошаговое руководство: Сложная привязка данных в проекте надстройки VSTO](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md)

## <a name="update-data-that-is-bound-to-host-controls"></a>Обновление данных, привязанный к элементы управления ведущего приложения
 Привязка данных между источником данных и элементом управления ведущего приложения подразумевает два способа обновления данных. В простой привязке данных изменения в источнике данных автоматически отражаются в элементе управления ведущего приложения, но при изменениях в элементе управления ведущего приложения необходимо явно вызывать обновление источника данных. Причина заключается в том, что в некоторых случаях изменения в одном поле с привязкой к данным не принимаются, пока не будут дополнены изменениями в другом поле с привязкой к данным. Например, у вас может быть два поля, одно для возраста, а другое для стажа. Стаж не может превышать возраст. Пользователь не может изменить возраст с 50 на 25, а затем изменить стаж с 30 на 10, если он делает эти изменения в одно и то же время. Для разрешения этой проблемы поля с простой привязкой данных не обновляются, пока обновления не будут явно отправлены в коде.

 Для обновления источника данных из элементов управления ведущего приложения с поддержкой простой привязки данных вы должны отправить обновления в источник данных в памяти (такой как <xref:System.Data.DataSet> или <xref:System.Data.DataTable>) и во внутреннюю базу данных, если она используется в решении.

 Вам не нужно явно обновлять источник данных в памяти, если выполняется сложная привязка данных с помощью элемента управления <xref:Microsoft.Office.Tools.Excel.ListObject> . В этом случае изменения автоматически отправляются в источник данных в памяти без дополнительного кода.

 Дополнительные сведения см. в разделе [Как Обновить источник данных с данными из элемента управления ведущего приложения](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).

## <a name="see-also"></a>См. также
- [Привязка данных и Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms)
- [Практическое руководство. Создание элемента управления простой привязкой в форме Windows](/dotnet/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form)
- [Привязка элементов управления Windows Forms к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Сохранение данных обратно в базу данных](../data-tools/save-data-back-to-the-database.md)
- [Обновление данных с помощью адаптера таблицы](../data-tools/update-data-by-using-a-tableadapter.md)
- [Кэширование данных](../vsto/caching-data.md)
- [Данные в решениях Office](../vsto/data-in-office-solutions.md)
