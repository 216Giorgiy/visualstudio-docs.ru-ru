---
title: IPropertyProxyEESide::CreateReplacementObject | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03bfeeb30fad4f332a3a747dcf8468c4fb39ef56
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704206"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
Создает копию объекта данных, относящиеся к вычислитель выражений (EE).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateReplacementObject(
   IEEDataStorage*  dataIn,
   IEEDataStorage** dataOut
);
```

```csharp
int CreateReplacementObject(
   IEEDataStorage     dataIn,
   out IEEDataStorage dataOut
);
```

#### <a name="parameters"></a>Параметры
 `dataIn`

 [in] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) объект, содержащий данные для копирования.

 `dataOut`

 [out] Возвращает новый `IEEDataStorage` объекта.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Этот метод предоставляется [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) объект, представляющий массив байтов. Это входящий объект данных обычно не реализуют EE. Тем не менее, объект, возвращаемый этим методом всегда реализуется EE, которая позволяет реализовать EE `IEEDataStorage` интерфейс требуется любой класс.

 Обратите внимание на то, что данные предоставляются во входящем `IEEDataStorage` объект должен иметь те же данные в исходящий `IEEDataStorage` объекта.

## <a name="see-also"></a>См. также
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)