---
title: IDebugApplication::FCanJitDebug | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.FCanJitDebug
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FCanJitDebug
ms.assetid: d7ddac65-4864-411f-bf66-34a46c03f239
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d5dc03d7d2511f5b50969c062104759e78fcf03
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58159014"
---
# <a name="idebugapplicationfcanjitdebug"></a>IDebugApplication::FCanJitDebug
Определяет, зарегистрирован ли отладчик just-in-time (JIT).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
BOOL FCanJitDebug();  
```  
  
#### <a name="parameters"></a>Параметры  
 Этот метод не принимает параметров.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, и регистрируется JIT-отладчик, метод возвращает `TRUE`. В противном случае она возвращает `FALSE`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод определяет, зарегистрирован ли JIT-отладчик.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IDebugApplication](../../winscript/reference/idebugapplication-interface.md)