---
title: IDebugDocumentPosition2::GetDocument | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2::GetDocument
helpviewer_keywords:
- IDebugDocumentPosition2::GetDocument
ms.assetid: eaa172c9-5748-4ce1-a0e2-33c2063f6752
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 006fe62796184d2c896e36f14190eac5f84671a5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56677946"
---
# <a name="idebugdocumentposition2getdocument"></a>IDebugDocumentPosition2::GetDocument
Получает содержащего документа.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetDocument( 
   IDebugDocument2** ppDoc
);
```

```csharp
int GetDocument( 
   out IDebugDocument2 ppDoc
);
```

#### <a name="parameters"></a>Параметры
 `ppDoc`

 [out] Возвращает [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) , представляющий документ, содержащий эту позицию.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также
- [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)