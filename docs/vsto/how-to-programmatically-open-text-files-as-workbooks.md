---
title: Практическое руководство. Программное открытие текстовых файлов как книг Excel
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 61e51f6274bc22ed0d34d33f5ff85bfbfbd927bd
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60060142"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Практическое руководство. Программное открытие текстовых файлов как книг Excel
  Текстовый файл можно открыть как книгу. Необходимо передать имя текстовый файл, который требуется открыть. Можно указать несколько необязательных параметров, например, номер строки для синтаксического анализа и формат столбцов данных в файле.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="example"></a>Пример
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]

## <a name="compile-the-code"></a>Компиляция кода
 В этом примере требуются следующие компоненты:

- Файл с разделителями-запятыми, с именем `Test.txt` , содержащий по крайней мере три строки текста.

- Текстовый файл `Test.txt` сохраняются на диске C.

## <a name="see-also"></a>См. также
- [Работа с книгами](../vsto/working-with-workbooks.md)
- [Практическое руководство. Программное открытие книг Excel](../vsto/how-to-programmatically-open-workbooks.md)
- [Практическое руководство. Программное создание книг Excel](../vsto/how-to-programmatically-create-new-workbooks.md)
- [Практическое руководство. Программное Сохранение книг Excel](../vsto/how-to-programmatically-save-workbooks.md)
- [Практическое руководство. Программное закрытие книг Excel](../vsto/how-to-programmatically-close-workbooks.md)
- [Необязательные параметры в решениях Office](../vsto/optional-parameters-in-office-solutions.md)
