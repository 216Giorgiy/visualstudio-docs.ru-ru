---
title: IDiaSession::put_loadAddress | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b768b06e0702f7929b402086dcc6e11918f3e683
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630097"
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
Задает адрес загрузки исполняемого файла, соответствующее к символам в данном хранилище символов.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT put_loadAddress ( 
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>Параметры
 `NewVal`

[in] Загрузить адрес для исполняемого файла.

## <a name="remarks"></a>Примечания
 Свойства символа виртуальный адрес (VA) вычисляются с помощью значения этого метода. Если это свойство не задано значение ненулевое, виртуальных адресов не вычисляются.

> [!NOTE]
>  Этот метод необходимо вызвать при получении [IDiaSession](../../debugger/debug-interface-access/idiasession.md) объекта и перед началом работы с помощью объекта, если необходимо использовать все виртуальные свойства на символы.

## <a name="see-also"></a>См. также раздел
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)