---
title: "IEnumDebugBoundBreakpoints2::GetCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugBoundBreakpoints2::GetCount"
helpviewer_keywords: 
  - "IEnumDebugBoundBreakpoints2::GetCount"
ms.assetid: 5a572eeb-beb7-4fc7-8259-792d277069be
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IEnumDebugBoundBreakpoints2::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Получает число элементов в перечислении.  
  
## Синтаксис  
  
```cpp#  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```c#  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### Параметры  
 `pcelt`  
 \[out\] возвращает число элементов в перечислении.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## Заметки  
 Этот метод не является частью привычного интерфейса перечисления модели COM, который указывает на то, что только `Next`"  `Clone`"  `Skip`и  `Reset` необходимость методов ссылкой его.  
  
## См. также  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)