---
title: Функции ловушек отчетов | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 18485d94aaedcb1f41c0ed747dc6af0be7f7e276
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952878"
---
# <a name="report-hook-functions"></a>Отчетные функции-ловушки
Отчетные функции-ловушки, установленные с помощью [_CrtSetReportHook](/cpp/c-runtime-library/reference/crtsetreporthook), вызываются каждый раз при создании отчета отладки [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw). Помимо всего прочего их можно использовать для фильтрации отчетов, которые позволяют отобрать выделения конкретного типа. Отчетная функция-ловушка должна иметь следующий прототип:  
  
```cpp
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 Указатель, передаваемый **_CrtSetReportHook** имеет тип **_CRT_REPORT_HOOK**, как определено в CRTDBG. H:  
  
```cpp
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 Когда CRT вызывает функцию-ловушку, аргумент *nRptType* содержит категорию отчета (**_CRT_WARN**, **_CRT_ERROR** или **_CRT_ASSERT**), *szMsg* содержит указатель на полностью собранную строку отчетного сообщения, а *retVal* задает значение, определяющее поведение `_CrtDbgReport`, которое может продолжить обычное выполнение после создания отчета или запустить отладчик. (Значение *retVal*, равное нулю, позволяет продолжить выполнение, а значение 1 запускает отладчик.)  
  
 Если ловушка полностью обрабатывает сообщение и дальнейшая выдача отчета не требуется, она возвращает значение **TRUE**. Если возвращается значение **FALSE**, `_CrtDbgReport` будет дальше выдавать отчетные сообщения в обычном режиме.  
  
## <a name="see-also"></a>См. также раздел  
 [Написание функций отладочных ловушек](../debugger/debug-hook-function-writing.md)   
 [Образец crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)
