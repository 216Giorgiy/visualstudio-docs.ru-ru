---
title: Web Essentials проекта | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7c7b3641a6c9fbc680f4a902b2f0e5d7bf331401
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60090697"
---
# <a name="web-project-essentials"></a>Основные компоненты веб-проекта
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Веб-проекты создания веб-приложений. Веб-проект можно использовать для создания веб-приложение имеет смарт-веб-страницы. Смарт-веб-страницы имеет серверный код, который выполняет визуализацию веб-страницы по запросу.  
  
 С помощью традиционных языках программирования, таких как [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../includes/csprcs-md.md)], можно создать смарт-веб-страниц для сбора и обработки информации от пользователя, сохранить его в базу данных и т. д.  
  
- Модель фонового кода связывает файлы зависимых исходного кода с веб-страниц .aspx расширение файла или ASMX. Например hello.aspx есть hello.aspx.cs зависимый исходный код файла.  
  
- Серверный код, связанный со смарт-веб-странице компилируется в исполняемый файл, расположенный в папке/Bin веб-сайта.  
  
- Дополнительные исходные файлы кода, таких как вспомогательные классы, которые не связаны с конкретной веб-странице, находятся в папке/App_Code веб-сайта.  
  
    - Проект веб-сайта (WSP) создает один исполняемый файл для каждого smart веб-страницы. Дополнительные исполняемые файлы, создаваемые все файлы исходного кода в папке/App_Code.  
  
    - Проект веб-приложения (WAP) создает один исполняемый файл, который сочетает в себе код для всех смарт-веб-страниц, а также все исходные файлы в папке/App_Code.  
  
- Отдельно от веб-сайта, сам находится файл решения веб-проекта. По умолчанию файлы решения приведены в \Documents and Settings\\*Ваша_учетная_запись*\My Documents\\*\<Visual Studio ### >* \Projects\\ *YourWebSite*.  
  
    > [!NOTE]
    >  Если вы хотите сохранить файл решения веб-сайт, просто перенесите ее и снова открыть его.  
  
- При открытии веб-сайт, который имеет отсутствует файл решения в Visual Studio, для нее автоматически создается новый файл решения.  
  
- Веб-проекты имеют не файлов проекта. Сведения о проекте хранится в файле решения, файл web.config и в других местах.  
  
- Добавление глобальных свойств веб-проекта автоматически создает файл хранения в папке решения веб-проекта.  
  
- Смарт-веб-страницы может быть связан с языком программирования на стороне сервера с помощью директивы страницы или \<скрипт runat = «server» > тег.  
  
- Кроме того веб-страниц может иметь любое количество блоков клиентского сценариев, написанных на любом языке сценариев.  
  
- Системы проекта веб-сайта осуществляется путем добавления шаблонов проектов и элементов и регистрацию, чтобы [!INCLUDE[vwprvw](../../includes/vwprvw-md.md)] проекта.  
  
- Система WAP реализуется как подтипом проекта, также называемый версии проекта. [!INCLUDE[vwprvw](../../includes/vwprvw-md.md)] Проекта является flavored по подтипу WAP для создания системы WAP. Дополнительные сведения о подтипов проекта, см. в разделе [подтипов проекта](../../extensibility/internals/project-subtypes.md).  
  
- Смарт-веб-странице объединяет HTML с языком программирования на стороне сервера. Язык на стороне сервера вызывается содержащегося языка. Для поддержки содержащегося языка, должен реализовывать веб-проекта системы <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> семейства интерфейсов.  
  
    - Для поддержки содержащегося языка в редакторе, языковой службы HTML необходимо отложить отображение содержащегося языка кода для службы содержащегося языка.  
  
    - Маркеры ошибок (Подчеркивание красной волнистой линией) всегда должны создаваться в первичном буфере редакторе кода.  
  
## <a name="see-also"></a>См. также  
 [Веб-проекты](../../extensibility/internals/web-projects.md)
