---
title: Практическое руководство. Применение изменений в режиме приостановки выполнения с помощью изменить и продолжить | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e26b293a5ac7326ca8f82250ec3d0da9fe96371c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069930"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Практическое руководство. Применение изменений в режиме приостановки выполнения с помощью изменить и продолжить
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Можно использовать "Изменить и продолжить" для изменения кода в режиме приостановки и продолжения затем работы без остановки и перезапуска приложения.  
  
 Режим "Изменить и продолжить" не доступен при следующих скриптах отладки:  
  
- отладка в смешанном режиме (машинный код/управляемый код);  
  
- отладка SQL;  
  
- отладка дампа Dr. Watson;  
  
- изменение кода после необработанного исключения, когда не включен параметр **Очищать стек вызовов от кадров необработанных исключений** ;  
  
- отладка вложенного приложения времени выполнения;  
  
- Отладка приложения с **присоединить к** вместо запуска приложения с **запустить** из **Отладка** меню.  
  
- отладка оптимизированного кода;  
  
- отладка управляемого кода 64-разрядного приложения. Если необходимо использовать операцию "Изменить и продолжить", нужно задать целевую архитектуру x86 (_Проекта_**свойства**, **компиляции** вкладке **Дополнительные параметры компилятора** параметр.).  
  
- отладка старой версии кода при наличии ошибок построения новой версии кода.  
  
### <a name="to-edit-code-in-break-mode"></a>Изменение кода в режиме приостановки  
  
1. Войдите в режим приостановки, выполнив одно из следующих действий:  
  
    - установите точку останова в коде, а затем выберите команду **Начать отладку** в меню **Отладка** и ждите, когда приложение попадет на точке останова;  
  
         – или –  
  
    - начните отладку, а затем выберите команду **Прервать все** в меню **Отладка**;  
  
         – или –  
  
    - При возникновении исключения выберите **Разрешить изменение** на**исключениям**.  
  
2. Внесите все необходимые и допустимые изменения в код.  
  
     Дополнительные сведения см. в разделе [неподдерживаемые изменения в Visual Basic, изменить и продолжить](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md).  
  
    > [!NOTE]
    >  При попытке недопустимого режимом "Изменить и продолжить" изменения кода, изменения будут подчеркнуты фиолетовой волнистой линией и соответствующая пометка появится в списке задач. Если не отменить недопустимые изменения кода, возможности продолжить выполнение кода не будет.  
  
3. В меню **Отладка** выберите пункт **Продолжить**, чтобы возобновить выполнение.  
  
     Код теперь выполняется с учетом примененных к проекту изменений.  
  
## <a name="see-also"></a>См. также  
 [Изменения, не поддерживаемые в Visual Basic, изменить и продолжить](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)   
 [Изменить и продолжить (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)
