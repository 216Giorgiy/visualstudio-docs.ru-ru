---
title: Отладка управляемого кода | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging managed code
- debugging ASP.NET Web applications, managed code
- managed code, debugging
ms.assetid: fa3aff01-c271-4aa7-b5b1-def560471c84
caps.latest.revision: 37
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efa999fabc0d27900900c6d1512cca3fde76043d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47572481"
---
# <a name="debugging-managed-code"></a>Отладка управляемого кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [Debugging Managed Code](https://docs.microsoft.com/visualstudio/debugger/debugging-managed-code).  
  
В данном разделе приводится описание общих проблем отладки и способов их решения для управляемых приложений или приложений, написанных на языках, предназначенных для общеязыковой среды выполнения, например Visual Basic, C#, и C++). Описанные здесь методики — методики высшего уровня. Дополнительные сведения см. в разделе [использование отладчика](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Диагностические сообщения в окне вывода](../debugger/diagnostic-messages-in-the-output-window.md)  
 Описывает <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace> классы, с помощью которых можно написать сообщения времени выполнения для **вывода** окна. Эти классы содержат методы вывода, позволяющие выводить сведения без прерывания выполнения программы, и выводить сведения, которые также прерывают выполнение при невыполнении заданного условия.  
  
 [Утверждения в управляемом коде](../debugger/assertions-in-managed-code.md)  
 Описывает утверждения в управляемом коде, которые проверяют условия, заданные в качестве аргументов методов `Assert`. Кроме того, этот раздел содержит пример кода, содержащий сведения об использовании методов классов <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace>, вопросы, касающиеся отладочной и выпускаемой версий кода, побочных эффектов, аргументов утверждений, настройки поведения утверждений и файлов конфигурации.  
  
 [Оператор Stop в Visual Basic](../debugger/stop-statements-in-visual-basic.md)  
 Описывает оператор `Stop`, который представляет собой альтернативу указанию точки останова. Кроме того, раздел содержит пример кода и сравнение оператора `Stop` с оператором `End`, а также оператора `Stop` с оператором `Assert`.  
  
 [Пошаговое руководство. Отладка в Windows Forms](../debugger/walkthrough-debugging-a-windows-form.md)  
 Пошаговые инструкции по созданию формы Windows Form и ее отладке. Форма Windows Forms - стандартный компонент приложения Windows, — один из наиболее распространенных вариантов управляемых приложений. В данном пошаговом руководстве используются языки Visual C# и Visual Basic, но методика создания форм Windows Forms с помощью C++ во многом аналогична.  
  
 [Отладка метода OnStart](../debugger/how-to-debug-the-onstart-method.md)  
 Предоставляются примеры кода, позволяющие выполнять отладку метода `OnStart` управляемой службы Windows. Для отладки метода `OnStart` службы Windows необходимо добавить несколько строк кода для имитации работы службы.  
  
 [Отладка в смешанном режиме](../debugger/debugging-mixed-mode-applications.md)  
 Обсуждение отладки приложений в смешанном режиме. Это подразумевает любое приложение, объединяющее машинный код с управляемым кодом.  
  
 [Ошибка. Отладка невозможна, так как в системе включен отладчик ядра](../debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system.md)  
 Описание сообщения об ошибке, возникающее при попытке произвести отладку управляемого кода на [!INCLUDE[win7](../includes/win7-md.md)], [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)], [!INCLUDE[winxp](../includes/winxp-md.md)], [!INCLUDE[Win2kFamily](../includes/win2kfamily-md.md)], или система Windows NT, который был запущен в режиме отладки.  
  
 [JIT-отладка и оптимизация](../debugger/jit-optimization-and-debugging.md)  
 Описывает эффекты по оптимизации по отладке JIT.  
  
 [Отладка LINQ и DLINQ](../debugger/debugging-linq.md)  
 Описывает методы отладки LINQ запросов.  
  
 [Пошаговое руководство. Отладка параллельного приложения](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Описывает использование **параллельных задач** и **Параллельные стеки** средство windows для отладки параллельного приложения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [IntelliTrace](../debugger/intellitrace.md)  
 Используйте IntelliTrace для ведения журнала выполнения приложений, чтобы сделать поиск ошибок более быстрым и удобным. Перемещайтесь вперед или назад между различными записанными событиями и вызовами для определения состояния приложения в соответствующие моменты времени. Производите отладку приложения, не устанавливая множество точек останова и не перезапуская приложение слишком часто. Доступно только в Visual Studio Ultimate.  
  
 [Трассировка и инструментирование приложений](http://msdn.microsoft.com/library/773b6fc4-9013-4322-b728-5dec7a72e743)  
 Описание трассировки приложений, позволяющей отследить ход выполнения приложения, и инструментирования приложений, размещающего операторы трассировки в стратегически важных местах кода. Кроме того, в данном разделе представлены ссылки на руководство по оборудованию и трассировке, а также по переключателям трассировки, слушателям трассировки, коду трассировки в приложении, добавлению оператора трассировки в код приложения и условной компиляции с использованием атрибутов <xref:System.Diagnostics.Debug> и <xref:System.Diagnostics.Trace>.  
  
 [/ ASSEMBLYDEBUG](http://msdn.microsoft.com/library/94443af3-470c-41d7-83a0-7434563d7982)  
 Описание параметра компоновщика, который добавляет <xref:System.Diagnostics.DebuggableAttribute> в код, написанный на языке C++. Этот атрибут необходим для использования таких возможностей отладчика, как, например, "присоединить с C++".  
  
 [Отладка приложений служб Windows](http://msdn.microsoft.com/library/63ab0800-0f05-4f1e-88e6-94c73fd920a2)  
 Рекомендации по отладке служебных приложений Windows, включая настройку, подключение к процессу, отладку кода в методе `OnStart` службы и кода в методе Main, задание точек останова и использование диспетчера управления службами для запуска, остановки, приостановки и продолжения выполнения службы пользователя.  
  
 [Отладка и профилирование](http://msdn.microsoft.com/library/4a04863e-2475-46f4-bc3f-3c11510c2a4b)  
 Описание отладки приложений .NET Framework и требований к конфигурации.  
  
 [Отладка приложений скриптов и веб-приложений](../debugger/debugging-web-applications-and-script.md)  
 Описание общих задач и методов отладки скриптов и веб-приложений.  
  
 [Новые возможности отладчика в Visual Studio 2015](../debugger/what’s-new-for-the-debugger-in-visual-studio-2015.md)  
 Описание новых возможностей отладки, добавленных в данном выпуске [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 [Домашняя страница отладки](../debugger/debugging-in-visual-studio.md)  
 Ссылки на крупные разделы документации об отладке. В них содержатся следующие сведения: новые возможности отладчика, сведения о параметрах и подготовке, точках останова, обработке исключений, изменении и продолжении выполнения, отладке управляемого кода, проектов Visual C++, объектов COM и ActiveX, библиотек DLL, SQL, а также ссылки на пользовательский интерфейс.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](http://msdn.microsoft.com/library/1fd83ccd-3798-42fc-85a3-6cba99467387)   
 [Безопасность отладчика](../debugger/debugger-security.md)   
 [Отладка в Visual Studio](../debugger/debugging-in-visual-studio.md)


