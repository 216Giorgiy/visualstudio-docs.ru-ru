---
title: IDebugDisassemblyStream2::GetSize | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::GetSize
helpviewer_keywords:
- IDebugDisassemblyStream2::GetSize
ms.assetid: 8f512704-12d0-46d2-959a-4f8dffe117b5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d415c87c67c20880615d83c1201b4588a683719c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706383"
---
# <a name="idebugdisassemblystream2getsize"></a>IDebugDisassemblyStream2::GetSize
Возвращает размер в инструкциях этого потока Дизассемблированный код.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetSize( 
   UINT64* pnSize
);
```

```csharp
int GetSize( 
   out ulong pnSize
);
```

#### <a name="parameters"></a>Параметры
 `pnSize`

 [out] Возвращает размер, в инструкции.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Значение, возвращаемое этим методом, можно выделить память для массива [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) структур, которые затем передается [чтения](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) метод.

## <a name="see-also"></a>См. также
- [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
- [Read](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)