---
title: IDebugStackFrame2::GetExpressionContext | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetExpressionContext
helpviewer_keywords:
- IDebugStackFrame2::GetExpressionContext
ms.assetid: a2604e6a-502d-473b-868f-b11ac64c7a35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0c453de210e503722dbf9da518a813f62090c495
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698668"
---
# <a name="idebugstackframe2getexpressioncontext"></a>IDebugStackFrame2::GetExpressionContext
Получает контекст вычисления для оценки выражения в контексте текущего кадра стека и потока.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetExpressionContext ( 
   IDebugExpressionContext2** ppExprCxt
);
```

```csharp
int GetExpressionContext ( 
   out IDebugExpressionContext2 ppExprCxt
);
```

#### <a name="parameters"></a>Параметры
 `ppExprCxt`

 [out] Возвращает [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) объект, представляющий контекст для вычисления выражений.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Как правило контекст вычисления выражения могут рассматриваться как область для выполнения вычисления выражений. Вызовите [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) метода для синтаксического разбора выражения, а затем вызвать итоговый [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) или [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) методы для оценки проанализированное выражение.

## <a name="see-also"></a>См. также
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
- [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)