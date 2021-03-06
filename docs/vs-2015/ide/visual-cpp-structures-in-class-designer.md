---
title: Структуры Visual C++ в конструкторе классов | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 19ffa241fdc1f58500c7065e2cee2a33340e33f8
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2019
ms.locfileid: "54794474"
---
# <a name="visual-c-structures-in-class-designer"></a>Структуры Visual C++ в конструкторе классов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Конструктор классов поддерживает те структуры C++, которые объявлены с использованием ключевого слова `struct`. Ниже представлен пример.  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 Дополнительные сведения об использовании типа `struct` см. в статье [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6).  
  
 Фигура структуры C++ на схеме классов выглядит так же, как фигура класса, но при этом она содержит надпись **Структура** и имеет квадратные, а не скругленные углы.  
  
|Элемент кода|Представление конструктора классов|  
|------------------|-------------------------|  
|`struct StructureName {};`|**StructureName**<br /><br /> Структура|  
  
## <a name="see-also"></a>См. также раздел  
 [Working with Visual C++ Code (Class Designer)](../ide/working-with-visual-cpp-code-class-designer.md)  (Работа с кодом Visual C++ (конструктор классов))  
 [Классы и структуры](http://msdn.microsoft.com/library/516dd496-13fb-4f17-845a-e9ca45437873)   
 [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6)
