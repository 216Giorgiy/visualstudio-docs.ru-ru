---
title: IDiaSymbol::get_backEndMinor | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_backEndMinor method
ms.assetid: 37f38d19-6685-440d-a477-7127c4f8699e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c4cbdaf9a259e199c0cc32141e961e74f9c91c8c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56628628"
---
# <a name="idiasymbolgetbackendminor"></a>IDiaSymbol::get_backEndMinor
Извлекает серверной части дополнительный номер версии компилятора.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT get_backEndMinor ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>Параметры
 `pRetVal`

[out] Возвращает серверной части дополнительный номер версии. См. заметки.

## <a name="return-value"></a>Возвращаемое значение
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает `S_FALSE` или код ошибки.

> [!NOTE]
>  Возвращаемое значение `S_FALSE` означает, что свойство недоступно для символа.

## <a name="remarks"></a>Примечания
 Компилятор обычно состоит из двух основных элементов: переднего плана (средство синтаксического анализа), который обрабатывает синтаксического анализа исходного кода в промежуточный форму, и серверной частью (генератор кода), который преобразует промежуточную форму в сборку. Нередко для внешнего интерфейса до имеют версию, отличную от серверной части.

 Интерфейс или номер версии серверной части состоит из трех частей: \<основных >.\< дополнительный номер >. \<сборки >, где \<основных > — номер основной версии \<незначительные > — это дополнительный номер версии, и \<сборки > — номер сборки. Например, 13.10.3077.

## <a name="requirements"></a>Требования

|Требование|Описание|
|-----------------|-----------------|
|Заголовок:|dia2.h|
|Версия:|ПАКЕТ SDK для версии 7.0|

## <a name="see-also"></a>См. также раздел
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)