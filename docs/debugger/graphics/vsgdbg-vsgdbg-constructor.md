---
title: VsgDbg::VsgDbg (конструктор) | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: db51226c4d980359fd36ee5196e48d7fa4577a37
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723205"
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg (конструктор)
Создает экземпляр класса `VsgDbg` с подготовкой или без подготовки компонента диагностики графики в приложении для активного захвата и записи данных графики по умолчанию, в зависимости от заданного логического параметра.

## <a name="syntax"></a>Синтаксис

```C++
VsgDbg(
  bDefaultInit
);
```

#### <a name="parameters"></a>Параметры
 `bDefaultInit` Значение `true` для указания того, что компонент диагностики графики в приложении должен быть подготовлен к активному захвату и записи данных графики; значение `false` для указания того, что в данный момент приложение не должно быть подготовлено к активному захвату и записи данных графики.

## <a name="remarks"></a>Примечания
 При вызове конструктора с `bDefaultInit` присвоено `true`, имя файла, файла журнала графики, определяется как `DONT_SAVE_VSGLOG_TO_TEMP` и `VSG_DEFAULT_RUN_FILENAME` определены символы препроцессора, прежде чем `vsgcapture.h` включается в вашем приложении.

 При вызове конструктора с параметром `bDefaultInit`, установленным в значение `false`, компонент диагностики графики в приложении может быть подготовлен для активного захвата и записи данных графики позднее с помощью функции `Init`.

## <a name="see-also"></a>См. также раздел
- [VsgDbg::~VsgDbg (деструктор)](vsgdbg-tilde-vsgdbg-destructor.md)
- [Init](init.md)
- [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)
- [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)