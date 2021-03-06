---
title: DataKind | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21630bea3022769d18748190c2a2d24c0e519a3c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608504"
---
# <a name="datakind"></a>DataKind
Указывает область конкретного значения данных.

## <a name="syntax"></a>Синтаксис

```C++
enum DataKind {
    DataIsUnknown,
    DataIsLocal,
    DataIsStaticLocal,
    DataIsParam,
    DataIsObjectPtr,
    DataIsFileStatic,
    DataIsGlobal,
    DataIsMember,
    DataIsStaticMember,
    DataIsConstant
};
```

## <a name="elements"></a>Элементы
Не удается определить символ DataIsUnknown данных.

Элемент данных DataIsLocal является локальной переменной.

Элемент данных DataIsStaticLocal является статической локальной переменной.

Элемент данных DataIsParam является формальным параметром.

Элемент данных DataIsObjectPtr является указателем объекта (`this`).

Элемент данных DataIsFileStatic — это переменная уровня файла.

Элемент данных DataIsGlobal является глобальной переменной.

Элемент данных DataIsMember является переменной члена объекта.

Элемент данных DataIsStaticMember является статической переменной класса.

Элемент данных DataIsConstant является константа.

## <a name="remarks"></a>Примечания
Возвращаемые значения в этом перечислении [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) метод.

## <a name="requirements"></a>Требования
Заголовок: cvconst.h

## <a name="see-also"></a>См. также раздел
- [Перечисления и структуры](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
