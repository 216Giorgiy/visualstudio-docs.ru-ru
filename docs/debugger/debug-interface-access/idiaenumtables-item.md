---
title: IDiaEnumTables::Item | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03931580f774c29a67771d2251b51825242535c9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56623558"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
Возвращает таблицу с помощью индекса или имени.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT Item ( 
   VARIANT     index,
   IDiaTable** table
);
```

#### <a name="parameters"></a>Параметры
 `index`

[in] Индекс или имя [IDiaTable](../../debugger/debug-interface-access/idiatable.md) требуется получить. Если используется вариант целое число, он должен быть в диапазоне от 0 до `count`-1, где `count` как возвращаемый [IDiaEnumTables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) метод.

 `table`

[out] Возвращает [IDiaTable](../../debugger/debug-interface-access/idiatable.md) объект, представляющий нужную таблицу.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Если указан вариант строка, строка имен конкретной таблицы. Имя должно быть одно из имен таблицы как определено в [константы (SDK отладки интерфейса доступа)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).

## <a name="example"></a>Пример

```C++
VARIANT var;
var.vt = VT_BSTR;
var.bstrVal = SysAllocString(DiaTable_Symbols );
IDiaTable* pTable;
pEnumTables->Item( var, &pTable );
```

## <a name="see-also"></a>См. также раздел
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
- [IDiaEnumTables::get_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)
- [Константы (SDK для доступа к интерфейсу отладки)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)