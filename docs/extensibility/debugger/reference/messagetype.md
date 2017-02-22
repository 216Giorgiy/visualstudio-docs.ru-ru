---
title: "MESSAGETYPE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MESSAGETYPE"
helpviewer_keywords: 
  - "Перечисления MESSAGETYPE"
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# MESSAGETYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Указывает тип сообщений и причину.  
  
## Синтаксис  
  
```cpp#  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```c#  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## Члены  
 MT\_OUTPUTSTRING  
 Указывает, что сообщение должно быть отправлено в окно вывода.  Это является взаимоисключающим из `MT_MESSAGEBOX`.  
  
 MT\_MESSAGEBOX  
 Указывает, что сообщение должно отображаться в окне сообщения.  Это является взаимоисключающим из `MT_OUTPUTSTRING`.  
  
 MT\_TYPE\_MASK  
 Значение маски для выявления назначение сообщения.  
  
 MT\_REASON\_EXCEPTION  
 Указывает, что окно сообщения, в котором отображается в результате исключения.  Это является взаимоисключающим из `MT_REASON_TRACEPOINT`.  
  
 MT\_REASON\_TRACEPOINT  
 Указывает, что окно сообщения, в котором отображается в результате обращение к точку трассировки.  Это является взаимоисключающим с `MT_REASON_EXCEPTION`.  
  
 MT\_REASON\_MASK  
 Значение маски, чтобы выявить причину, показыванным сообщения.  
  
## Заметки  
 Эти значения возвращаются из [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) и  [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) методы.  
  
 Одно из значений причины могут быть объединены с одним из значений назначения выхода, используя побитовую `OR`.  
  
## Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## См. также  
 [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)