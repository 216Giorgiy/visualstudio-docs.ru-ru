---
title: Отладка элемента управления WebView | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 7d105907-8b39-4d07-8762-5c5ed74c7f21
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1ffb19e85d7294c082f7eecb0dbffd8aa436a03c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065471"
---
# <a name="debug-a-webview-control"></a>Отладка элемента управления WebView
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Применяется к Windows и Windows Phone] (.. /Image/windows_and_phone_content.PNG «windows_and_phone_content»)  
  
 Для проверки и отладки элементов управления `WebView` в приложении среды выполнения Windows вы можете настроить Visual Studio на вложение отладчика скрипта при запуске приложения. Начиная с обновления 2 для Visual Studio 2013, у вас появилось два способа взаимодействия с элементами управления `WebView` с помощью отладчика.  
  
- Откройте [Проводник DOM](../debugger/quickstart-debug-html-and-css.md) для экземпляра `WebView`, а затем проверьте элементы DOM, изучите проблемы со стилями CSS и протестируйте динамические отрисовываемые изменения в стилях.  
  
- Выберите веб-страницу или `iFrame`, отображаемые в экземпляре `WebView`, в качестве цели в окне [Консоль JavaScript](../debugger/javascript-console-commands.md), а затем осуществите взаимодействие с веб-страницей с помощью команд консоли. Консоль предоставляет доступ к текущему контексту выполнения скрипта.  
  
### <a name="attach-the-debugger-c-visual-basic-c"></a>Добавление делений в код C#, Visual Basic, C++  
  
1. В Visual Studio добавьте элемент управления `WebView` в свое приложение среды выполнения Windows.  
  
2. В обозревателе решений откройте свойства для проекта, выбрав пункт **Свойства** в контекстном меню для проекта.  
  
3. Выберите **Отладка**. В списке **Процесс приложения** выберите **Скрипт**.  
  
     ![Подключение отладчика сценариев](../debugger/media/js-dom-webview-script-debugger.png "JS_DOM_WebView_Script_Debugger")  
  
4. (Необязательно) Для отличных от Express версий Visual Studio, отключить отладку just-in-time (JIT), выбрав **средства**, **параметры**, **Отладка**, **Just-In-Time**, и отключив JIT-отладку для скрипта.  
  
    > [!NOTE]
    >  Отключив JIT-отладку, вы можете скрыть диалоговые окна для необработанных исключений, возникающих на некоторых страницах. В Visual Studio Express JIT-отладка всегда отключена.  
  
5. Нажмите клавишу F5, чтобы начать отладку.  
  
### <a name="use-the-dom-explorer-to-inspect-and-debug-a-webview-control"></a>Использование проводника DOM для проверки и отладки элемента управления WebView  
  
1. (C#, Visual Basic, C++) Вложите отладчик скрипта в приложение. Инструкции см. в первом разделе.  
  
2. Если вы еще этого не сделали, добавьте элемент управления `WebView` в свое приложение и нажмите клавишу F5 для запуска отладки.  
  
3. Перейдите на страницу, содержащую элементы управления `Webview`.  
  
4. Откройте окно проводника DOM для элемента управления `WebView`, выбрав **Отладка**, **Окна**, **Проводник DOM**, а затем выберите URL-адрес `WebView`, который хотите проверить.  
  
     ![Открытие проводника DOM](../debugger/media/js-dom-webview.png "JS_DOM_WebView")  
  
     Проводник DOM, сопоставленный с `WebView`, отображается в Visual Studio в виде новой вкладки.  
  
5. Просматривать и изменять элементы live DOM и стили CSS, как описано в разделе [стилей CSS, отладка с использованием проводника DOM](../debugger/debug-css-styles-using-dom-explorer.md).  
  
### <a name="use-the-javascript-console-window-to-inspect-and-debug-a-webview-control"></a>Использование окна консоли JavaScript для проверки и отладки элемента управления WebView  
  
1. (C#, Visual Basic, C++) Вложите отладчик скрипта в приложение. Инструкции см. в первом разделе.  
  
2. Если вы еще этого не сделали, добавьте элемент управления `WebView` в свое приложение и нажмите клавишу F5 для запуска отладки.  
  
3. Откройте окно консоли JavaScript для элемента управления `WebView`, выбрав **Отладка**, **Окна**, **Консоль JavaScript**.  
  
     Отображается окно консоли JavaScript.  
  
4. Перейдите на страницу, содержащую элементы управления `Webview`.  
  
5. В окне консоли выберите веб-страницу или `iFrame`, отображаемый элементом управления `WebView` в списке **Цель**.  
  
     ![Предназначенных для выбора в окне консоли JavaScript](../debugger/media/js-console-target.png "JS_Console_Target")  
  
    > [!NOTE]
    >  С помощью консоли вы можете одновременно взаимодействовать с отдельным `WebView`, `iFrame`, контрактом отправки данных или рабочим веб-процессом. Каждый элемент требует отдельного экземпляра узла веб-платформы (WWAHost.exe). Одновременно можно взаимодействовать с одним узлом.  
  
6. Просмотреть и изменить переменные в приложении или используйте команды консоли, как описано в разделе [краткое руководство: Отладка JavaScript](../debugger/quickstart-debug-javascript-using-the-console.md) и [команды консоли JavaScript](../debugger/javascript-console-commands.md).  
  
## <a name="see-also"></a>См. также  
 [Краткое руководство. Отладка HTML и CSS](../debugger/quickstart-debug-html-and-css.md)
