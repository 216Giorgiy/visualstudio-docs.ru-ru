---
title: IDiaSymbol::get_lowerBoundId | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_lowerBoundId method
ms.assetid: 12ce98e9-a225-4947-88c9-5fda39dd67e4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c591b9350128a425a3f97363cb43c43de2005156
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598288"
---
# <a name="idiasymbolgetlowerboundid"></a>IDiaSymbol::get_lowerBoundId
Извлекает идентификатор символа нижней границы измерения массива FORTRAN.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT get_lowerBoundId ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Параметры
 `pRetVal`

[out] Возвращает идентификатор символа символ, представляющий нижнюю границу измерения массива FORTRAN.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` или код ошибки.

> [!NOTE]
>  Возвращаемое значение `S_FALSE` означает, что свойство недоступно для символа.

## <a name="remarks"></a>Примечания
 Идентификатор — это уникальное значение, созданные с помощью пакета SDK доступа к интерфейсу отладки, чтобы пометить все символы как уникальный.

## <a name="see-also"></a>См. также раздел
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)