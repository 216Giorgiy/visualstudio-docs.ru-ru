---
title: "IDebugField::Equal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugField::Equal"
helpviewer_keywords: 
  - "Метод IDebugField::Equal"
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugField::Equal
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Этот метод сравнивает это поле с указанным полем на равенство.  
  
## Синтаксис  
  
```cpp#  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```c#  
int Equal(  
   IDebugField pField  
);  
```  
  
#### Параметры  
 `pField`  
 \[in\] поля, которое требуется сравнить значение.  
  
## Возвращаемое значение  
 Если поля совпадают, то возвращается `S_OK`.  Если поля различаются, то возвращается `S_FALSE.` В противном случае возвращает код ошибки.  
  
## См. также  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)