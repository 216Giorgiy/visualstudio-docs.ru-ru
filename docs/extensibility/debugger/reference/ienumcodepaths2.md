---
title: IEnumCodePaths2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumCodePaths2
helpviewer_keywords:
- IEnumCodePaths2 interface
ms.assetid: 17ec9f9e-dc06-4532-b5db-da52efcc8630
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eb1df4276c6156b6d53fbf40499f44a40275cba1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56692753"
---
# <a name="ienumcodepaths2"></a>IEnumCodePaths2
Этот интерфейс представляет список путей кода.

## <a name="syntax"></a>Синтаксис

```
IEnumCodePaths2 : IUnknown
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Модуль отладки (DE) реализует этот интерфейс для представления списка путей кода.

## <a name="notes-for-callers"></a>Заметки о вызывающих объектов
 Вызовите [EnumCodePaths](../../../extensibility/debugger/reference/idebugprogram2-enumcodepaths.md) для получения этого интерфейса.

## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable
 В следующей таблице показаны методы `IEnumCodePaths2`.

|Метод|Описание:|
|------------|-----------------|
|[Вперед](../../../extensibility/debugger/reference/ienumcodepaths2-next.md)|Получает заданное число путей в последовательности перечисления.|
|[Skip](../../../extensibility/debugger/reference/ienumcodepaths2-skip.md)|Пропускает заданное число путей в последовательности перечисления.|
|[Reset](../../../extensibility/debugger/reference/ienumcodepaths2-reset.md)|Сбрасывает последовательность перечислений в начало.|
|[Clone](../../../extensibility/debugger/reference/ienumcodepaths2-clone.md)|Создает перечислитель с тем же состоянием перечисления, что и текущий перечислитель.|
|[GetCount](../../../extensibility/debugger/reference/ienumcodepaths2-getcount.md)|Получает число путей кода в перечислителе.|

## <a name="remarks"></a>Примечания
 Путь кода представляет ветвь точки или вызов функции в программе. Список путей кода представляет собой путь, через который занял выполнение кода.

## <a name="requirements"></a>Требования
 Header: msdbg.h

 Пространство имен: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Базовые интерфейсы](../../../extensibility/debugger/reference/core-interfaces.md)