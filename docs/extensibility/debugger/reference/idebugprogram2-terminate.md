---
title: IDebugProgram2::Terminate | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::Terminate
helpviewer_keywords:
- IDebugProgram2::Terminate
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9b80afe3f0061e016301b86229f2eacedf217a43
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709308"
---
# <a name="idebugprogram2terminate"></a>IDebugProgram2::Terminate
Завершает программу.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Terminate( 
   void 
);
```

```csharp
int Terminate();
```

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Если это возможно программа будет завершен и выгружать из процесса; в противном случае модуль отладки (DE) выполнит необходимые операции очистки.

 Этот метод или [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) метод вызывается средой IDE, обычно в ответ на пользователя к остановке всех отладки. Реализация этого метода в идеале, завершение работы программы в рамках процесса. Если это невозможно, DE следует привести программы к работе в этом процессе большее количество (и выполнить необходимую очистку). Если `IDebugProcess2::Terminate` метод был вызван в интегрированной среде разработки, весь процесс завершается через некоторое время после `IDebugProgram2::Terminate` вызывается метод.

## <a name="see-also"></a>См. также
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [Terminate](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)