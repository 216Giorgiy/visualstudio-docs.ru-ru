---
title: Завершение программы | Документация Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf972e6bb38d9dcd2995814e885ceb0b071abe29
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294686"
---
# <a name="terminating-a-program"></a>Завершение программы
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ниже приведено описание прекращения одной программы с одним потоком.  
  
## <a name="termination-process"></a>Завершение процесса  
  
1.  Отправляет DE [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) допустимое [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  Отправляет DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) допустимое [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 Интегрированная среда разработки переходит в режим конструктора. Модуль отладки или среда выполнения вызывает метод [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) удаление программы из порта.  
  
## <a name="see-also"></a>См. также  
 [Вызов событий отладчика](../../extensibility/debugger/calling-debugger-events.md)

