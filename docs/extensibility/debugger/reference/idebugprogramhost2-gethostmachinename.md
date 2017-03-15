---
title: "IDebugProgramHost2::GetHostMachineName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramHost2::GetHostMachineName"
helpviewer_keywords: 
  - "IDebugProgramHost2::GetHostMachineName"
ms.assetid: 4677ffe4-aa9b-4450-a63b-74cd3984d956
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgramHost2::GetHostMachineName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Возвращает имя компьютера, на котором выполняется программа процесса размещения.  
  
## Синтаксис  
  
```cpp#  
HRESULT GetHostMachineName(   
   BSTR* pbstrHostMachineName  
);  
```  
  
```c#  
int GetHostMachineName(   
   out string pbstrHostMachineName  
);  
```  
  
#### Параметры  
 `pbstrHostMachineName`  
 \[out\] возвращает имя компьютера.  
  
## Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## См. также  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)