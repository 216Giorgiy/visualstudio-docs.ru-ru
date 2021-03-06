---
title: IRemoteDebugApplicationEx:ForceStepMode | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:ForceStepMode
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:ForceStepMode
ms.assetid: 83e69a3e-e4c9-4ddd-b01b-1820e4177a03
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04a2c700d2cac4bcdc845ebf442de29863e87deb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159495"
---
# <a name="iremotedebugapplicationexforcestepmode"></a>IRemoteDebugApplicationEx:ForceStepMode

Заставляет отладчик в пошаговом режиме.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT ForceStepMode(
   IRemoteDebugApplicationThread*  pStepThread
);
```

### <a name="parameters"></a>Параметры

`pStepThread`

[in] Поток для монитор отладки процесса к шагу. Если значение равно null, PDM очищает его пошагового выполнения потока.

## <a name="return-value"></a>Возвращаемое значение

Метод возвращает `HRESULT`. Допустимые значения включают, но не ограничиваются, значения, приведенные в следующей таблице.

|Значение|Описание|
|-----------|-----------------|
|`S_OK`|Метод успешно выполнен.|

## <a name="see-also"></a>См. также

- [IRemoteDebugApplicationEx Interface](iremotedebugapplicationex-interface.md)