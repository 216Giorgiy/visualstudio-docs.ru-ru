---
title: IDebugMethodField::EnumArguments | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bf62392118ed3ddfb2dfbfca06588f0935f3192d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56719903"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
Создает перечислитель для тип каждого аргумента, необходимые для вызова метода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumArguments( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumArguments(
   out IEnumDebugFields ppParams
);
```

#### <a name="parameters"></a>Параметры
 `ppParams`

 [out] Возвращает [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) объект, представляющий список типов аргументов. Возвращает значение null, если аргументы не используются.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает значение S_OK, или возвращает S_FALSE, если аргументы не используются. В противном случае возвращается код ошибки.

## <a name="remarks"></a>Примечания
 Каждый элемент является [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) объект, представляющий тип каждого параметра. Вызовите [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) метод для извлечения сведений о типе каждого параметра.

 Если требуется указать имя параметра вместе с типом, затем вызвать [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md) метод.

## <a name="see-also"></a>См. также
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)