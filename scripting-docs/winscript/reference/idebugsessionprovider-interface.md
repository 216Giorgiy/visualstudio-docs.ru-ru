---
title: "Интерфейс IDebugSessionProvider | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e61b1e5e794c68e34250f958cdda0f50b68334c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsessionprovider-interface"></a>Интерфейс IDebugSessionProvider
Это основной интерфейс, предоставляемый отладчиком интегрированной среды разработки для узла и языка инициировал отладки. Он устанавливает сеанс отладки для выполняемого приложения. Этот интерфейс реализуется диспетчера отладки.  
  
 Помимо методов, наследуемых от `IUnknown`, `IDebugSessionProvider` интерфейс предоставляет следующие методы.  
  
## <a name="methods-in-vtable-order"></a>Методы в порядке таблицы Vtable  
  
|Метод|Описание|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|Инициирует сеанс отладки с указанным приложением.|