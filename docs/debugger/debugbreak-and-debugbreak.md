---
title: DebugBreak и __debugbreak | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6c4b9d780caf7589eecdc709cbede577dd7a6fd
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686162"
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak и __debugbreak
Вызов функции DebugBreak Win32 или встроенной функции [__debugbreak](/cpp/intrinsics/debugbreak) можно разместить в любом месте кода. Вызов `DebugBreak` или `__debugbreak` эквивалентен установке точки останова в этом месте программы.

 Поскольку `DebugBreak` — это системная функция, на компьютере должны быть установлены системные отладочные символы, гарантирующие правильное отображение информации стека вызовов после приостановки выполнения. В противном случае сведения стека вызовов, отображаемые в отладчике, могут выйти за пределы одного кадра. При использовании `__debugbreak` символы не требуются.

## <a name="see-also"></a>См. также раздел
- [Встроенные инструкции компилятора](/cpp/intrinsics/compiler-intrinsics)
- [Безопасность отладчика](../debugger/debugger-security.md)
- [Отладка машинного кода](../debugger/debugging-native-code.md)
- [Указание файлов символов (.pdb) и файлов с исходным кодом](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)