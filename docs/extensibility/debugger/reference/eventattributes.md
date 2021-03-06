---
title: EVENTATTRIBUTES | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 58417471e37dd335c2fa751492f2db357274417a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686903"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Определяет атрибуты события.

## <a name="syntax"></a>Синтаксис

```cpp
enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
typedef DWORD EVENTATTRIBUTES;
```

```csharp
public enum enum_EVENTATTRIBUTES {
    EVENT_ASYNCHRONOUS          = 0x0000,
    EVENT_SYNCHRONOUS           = 0x0001,
    EVENT_STOPPING              = 0x0002,
    EVENT_ASYNC_STOP            = 0x0002,
    EVENT_SYNC_STOP             = 0x0003,
    EVENT_IMMEDIATE             = 0x0004,
    EVENT_EXPRESSION_EVALUATION = 0x0008
};
```

## <a name="members"></a>Участники
EVENT_ASYNCHRONOUS указывает, что событие является асинхронным, и требуется ответ на событие.

EVENT_SYNCHRONOUS указывает, что событие является синхронным, Ответить с помощью параметра [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).

EVENT_STOPPING указывает, что это событие остановки. Необходимо использовать вместе с `EVENT_ASYNCHRONOUS` или `EVENT_SYNCHRONOUS`.

EVENT_ASYNC_STOP указывает событие асинхронной остановки. В настоящее время нет такого события. Этот флаг является только заполнителем.

EVENT_SYNC_STOP указывает на событие синхронной остановке (сочетание `EVENT_SYNCHRONOUS` и `EVENT_STOPPING`). Это значение используется модулем отладки (DE), когда он отправляет событие stopping. Ответ осуществляется посредством вызова [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [шаг](../../../extensibility/debugger/reference/idebugprogram2-step.md), или [Продолжить](../../../extensibility/debugger/reference/idebugprogram2-continue.md).

EVENT_IMMEDIATE указывает событие, которое отправляется немедленно и синхронно в интегрированную среду разработки. Этот флаг используется в сочетании с другими флагами как `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, или `EVENT_SYNC_STOP` для указания типа события и тот факт, что механизм ответа (при наличии) будет известен.

EVENT_EXPRESSION_EVALUATION события является результатом вычисления выражения.

## <a name="remarks"></a>Примечания
Эти значения передаются в `dwAttrib` параметр [событий](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) метод.

Эти значения могут объединяться с побитовым объектом `OR`.

## <a name="requirements"></a>Требования
Header: msdbg.h

Пространство имен: Microsoft.VisualStudio.Debugger.Interop

Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
