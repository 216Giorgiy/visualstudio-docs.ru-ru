---
title: Изменить и продолжить (Visual C#) | Документация Майкрософт
ms.date: 10/11/2017
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Edit and Continue
- Edit and Continue [C#]
- debugging [C#], Edit and Continue
ms.assetid: 591bd1b7-ef10-4d10-817b-3f92ca4be006
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 972ad0d772eee9b876f43bc3e2fcd032d4b7e0ab
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685369"
---
# <a name="edit-and-continue-visual-c"></a>Режим "Изменить и продолжить" (Visual C#)
 С помощью операции "Изменить и продолжить" для С# в процессе отладки можно вносить изменения в код в режиме приостановки выполнения. Изменения могут применяться без необходимости остановки и повторного запуска сеанса отладки. В режиме выполнения редактор исходного кода доступен только для чтения.

 Операция "Изменить и продолжить" поддерживает большинство изменений, которые могут потребоваться в ходе отладки, но существуют некоторые исключения. Дополнительные сведения см. в разделе [поддерживаемые изменения кода (C# и Visual Basic)](../debugger/supported-code-changes-csharp.md).

 Изменить и продолжить поддерживается в универсальной платформы Windows в Windows 10 и x86 и x64 приложениях, предназначенных для .NET Framework 4.6 рабочего стола или более поздней версии, (.NET Framework является только версии настольного компьютера).

 > [!NOTE]
 > Неподдерживаемые приложения и платформы включают ASP.NET 5, Silverlight 5 и Windows 8.1.

 Когда операция "Изменить и продолжить" включена, поддерживаемые изменения применяются автоматически при использовании команд отладчика, таких как **Продолжить**, **Шаг**, **Задать следующий оператор**, или при выполнении вычисления функции в окне отладчика.

 Дополнительные сведения см. в разделе [как: изменить и продолжить (C#)](../debugger/how-to-use-edit-and-continue-csharp.md).

## <a name="see-also"></a>См. также раздел
- [Практическое руководство. Использование режима "Изменить и продолжить" (C#)](../debugger/how-to-use-edit-and-continue-csharp.md)
- [Поддерживаемые изменения кода (C# и Visual Basic)](../debugger/supported-code-changes-csharp.md)