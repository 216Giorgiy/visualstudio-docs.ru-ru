---
title: StopTrackingAndCleanup | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- StopTrackingAndCleanup
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StopTrackingAndCleanup
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 56f4fb82ab0e9792cadbeeea05499744e4c8ce46
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621309"
---
# <a name="stoptrackingandcleanup"></a>StopTrackingAndCleanup
Останавливает все отслеживание и освобождает память, используемую сеансом отслеживания.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT WINAPI StopTrackingAndCleanup(void);
```

## <a name="return-value"></a>Возвращаемое значение
 Возвращает **HRESULT** с установленным битом **SUCCEEDED**, если отслеживание было остановлено.

## <a name="requirements"></a>Требования
 **Заголовок.** *FileTracker.h*

## <a name="see-also"></a>См. также
- [StartTrackingContext](../msbuild/starttrackingcontext.md)