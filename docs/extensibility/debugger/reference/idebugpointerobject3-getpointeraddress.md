---
title: "IDebugPointerObject3::GetPointerAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetPointerAddress"
  - "IDebugPointerObject3::GetPointerAddress"
ms.assetid: 4cc5af04-9e70-420d-8230-ef3108df6d51
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPointerObject3::GetPointerAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Извлекает адрес указателя.  
  
## Синтаксис  
  
```cpp#  
HRESULT GetPointerAddress (  
   UINT64* puAddress  
);  
```  
  
```c#  
int GetPointerAddress (  
   out ulong puAddress  
);  
```  
  
#### Параметры  
 `puAddress`  
 \[out\] возвращает адрес указателя.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## См. также  
 [IDebugPointerObject3](../../../extensibility/debugger/reference/idebugpointerobject3.md)