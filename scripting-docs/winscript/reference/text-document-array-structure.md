---
title: "TEXT_DOCUMENT_ARRAY — структура | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "TEXT_DOCUMENT_ARRAY — структура"
ms.assetid: 47c08f23-981b-4105-9240-6dfffc6cb91b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# TEXT_DOCUMENT_ARRAY — структура
Массив объектов [Интерфейс IDebugDocumentText](../../winscript/reference/idebugdocumenttext-interface.md).  Члены выделитьы с помощью CoTaskMemAlloc.  
  
## Синтаксис  
  
```  
typedef struct tagTEXT_DOCUMENT_ARRAY  
{  
    DWORD dwCount;  
    [size_is(dwCount)] IDebugDocumentText **Members;  
} TEXT_DOCUMENT_ARRAY;  
  
```  
  
## Члены  
 `dwCount`  
 Количество документов.  
  
 `Members`  
 Пакете документов.  
  
## См. также  
 [Константы, перечисления и структуры отладчика активных скриптов](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)