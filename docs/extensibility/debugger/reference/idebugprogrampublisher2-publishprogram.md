---
title: IDebugProgramPublisher2::PublishProgram | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bb1553070f9afecf6ce60ac51b94ecb3f05d0eb9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698772"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
Этот метод выполняет программу для отладчиков (DEs) и диспетчер отладки сеансов.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT PublishProgram(
   CONST_GUID_ARRAY Engines,
   LPCOLESTR        szFriendlyName,
   IUnknown*        pDebuggeeInterface
);
```

```csharp
int PublishProgram(
   CONST_GUID_ARRAY Engines,
   string           szFriendlyName,
   object           pDebuggeeInterface
);
```

#### <a name="parameters"></a>Параметры
 `Engines`

 [in] Массив идентификаторов GUID для DEs, которые можно запустить или присоединить к этой программе.

 `szFriendlyName`

 [in] Понятное имя для программы (отображается в меню и диалоговых окон, показываемых пользователю).

 `pDebuggeeInterface`

 [in] `IUnknown` интерфейс для программы (это значение используется как файл cookie для уникальной идентификации программы; это же значение используется для отмены «публикации» программа)

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Чтобы сделать программу более не доступны для отладки, вызовите [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md).

## <a name="see-also"></a>См. также
- [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)
- [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)