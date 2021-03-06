---
title: IDiaPropertyStorage::ReadPropertyNames | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7492e0eee0523fd102ecd057d075f2672bf3b25b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56695847"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
Извлекает строковые имена соответствующих прав идентификаторов свойств.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT ReadPropertyNames (
   ULONG         cpropid,
   PROPID const* rgpropid,
   BSTR*         rglpwstrName
);
```

#### <a name="parameters"></a>Параметры
 `cpropid`

[in] Количество идентификаторов свойств в `rgpropid`.

 `rgpropid`

[in] Массив идентификаторов свойств, для которого необходимо получить имена (`PROPID` определяется в файле WTypes.h как `ULONG`).

 `rglpwstrName`

[in, out] Массив имен свойств для указанного свойства идентификаторов. Массив должен быть предварительно выделяются для хранения запрошенное число имен свойств и должен иметь возможность по крайней мере `cpropid``BSTR` строк.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Имя возвращаемого свойства должны быть высвобождены (путем вызова `SysFreeString` функции) когда они больше не нужны.

## <a name="see-also"></a>См. также раздел
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)