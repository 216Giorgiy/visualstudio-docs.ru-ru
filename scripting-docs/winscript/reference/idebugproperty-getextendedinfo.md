---
title: IDebugProperty::GetExtendedInfo | Документация Майкрософт
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6dc3fc90b8f5fa465715bc4b9466da472cbbb580
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086545"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
Возвращает расширенные сведения для свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cInfos`  
 [in] Счетчик расширенных сведений об объектах.  
  
 `rgguidExtendedInfo`  
 [in] Массив `GUID`s передается, чтобы можно было получить несколько элементов из расширенных сведений в то же время.  
  
 `pExtendedInfo`  
 [out] Возвращает массив `VARIANT`s, который может использоваться для получения этих данных расширенного свойства.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает допустимый `HRESULT`, обычно `S_OK`.  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс возвращает расширенные сведения для этого объекта. API существует только в целях получения информации, которая не совместима получить с помощью `IDebugProperty::GetPropertyInfo`).  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IDebugProperty](../../winscript/reference/idebugproperty-interface.md)