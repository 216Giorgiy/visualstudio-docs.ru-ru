---
title: IDebugReturnValueEvent2::GetReturnValue | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReturnValueEvent2::GetReturnValue
helpviewer_keywords:
- IDebugReturnValueEvent2::GetReturnValue
ms.assetid: 86c50d5a-6df6-4798-818a-c587a8741f90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 76d129d433f43b9264dc7262841d9b84c4d729c2
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685694"
---
# <a name="idebugreturnvalueevent2getreturnvalue"></a>IDebugReturnValueEvent2::GetReturnValue
Получает значение, возвращенное на пошаговую отладку из или обходом функции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetReturnValue ( 
   IDebugProperty2** ppReturnValue
);
```

```csharp
int GetReturnValue ( 
   out IDebugProperty2 ppReturnValue
);
```

#### <a name="parameters"></a>Параметры
 `ppReturnValue`

 [out] Возвращает [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , представляющий извлекаемого значения.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также
- [IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)