---
title: DOCCONTEXT_COMPARE | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4a2a685fb76e6e85078eb1f78f590ebc2b509e35
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49215008"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Указывает критерии для сравнения двух контекстов документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Участники  
 DOCCONTEXT_EQUAL  
 Найти первый контекст документа в списке, который равен целевой контекст документа.  
  
 DOCCONTEXT_LESS_THAN  
 Найти первый контекст документа в списке, который меньше, чем целевой контекст документа.  
  
 DOCCONTEXT_GREATER_THAN  
 Найти первый контекст документа в списке, который больше, чем целевой контекст документа.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 Найти первый контекст документа в списке, который находится в том же документе целевой контекст документа.  
  
## <a name="remarks"></a>Примечания  
 Передается в качестве аргумента для [сравнения](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) метод.  
  
 Эти значения используются для указания критерии сравнения для нахождения первого контекст документа в виде списка. Контекст документа предоставляется список контекстов документа сравнивать себя с помощью `IDebugDocumentContext2::Compare` метод. Первый контекст документа в списке, для которого является оператор сравнения `true` затем возвращается.  
  
## <a name="requirements"></a>Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)

