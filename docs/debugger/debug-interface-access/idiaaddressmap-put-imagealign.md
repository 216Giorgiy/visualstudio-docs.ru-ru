---
title: IDiaAddressMap::put_imageAlign | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2126d59d223e4923609071fa130b1cac465073ad
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616954"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
Задает выравнивание изображения.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT put_imageAlign ( 
   DWORD NewVal
);
```

#### <a name="parameters"></a>Параметры
 NewVal

[in] Новое значение выравнивания изображения для исполняемого файла.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Примечания
 Изображения (загруженных исполняемых файлов) выравниваются по границы указанной области памяти. Такое выравнивание может влиять текущую архитектуру системы и параметрами времени компиляции и связывания. Выравнивание изображения всегда включен байтовым границам. Допустимы следующие значения выравнивания изображения: 1, 2, 4, 8, 16, 32 и 64 байта границы.

 Текущий тип выравнивания изображения можно получить с помощью вызова [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) метод.

> [!NOTE]
>  Когда этот метод может вызываться уже загрузки изображения. `put_imageAlign` Метод обычно используется, если изображение были перемещены и изменены, и новый выравнивание является обязательным.

## <a name="see-also"></a>См. также раздел
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)