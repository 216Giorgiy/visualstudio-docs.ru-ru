---
title: "IDebugThread2::GetLogicalThread | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: d1591fab36316df8344d0602afaac0367b232c72
ms.lasthandoff: 02/22/2017

---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
Отладчики не реализуют этот метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
HRESULT GetLogicalThread(   
   IDebugStackFrame2*     pStackFrame,  
   IDebugLogicalThread2** ppLogicalThread  
);  
```  
  
```c#  
int GetLogicalThread(   
   IDebugStackFrame2        pStackFrame,  
   out IDebugLogicalThread2 ppLogicalThread  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStackFrame`  
 [in] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) объект, который представляет кадр стека.  
  
 `ppLogicalThread`  
 [out] Возвращает `IDebugLogicalThread2` интерфейс, который представляет логический поток. Реализации обработчика отладки следует выбрать значение null.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Отладка ядра реализации всегда возвращают `E_NOTIMPL`.  
  
## <a name="see-also"></a>См. также  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
