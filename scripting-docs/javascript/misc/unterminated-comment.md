---
title: Незавершенный комментарий | Документация Майкрософт
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d4286315-814b-4966-b4c4-1ee19d796eff
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bf7c570c832fb5db5489a2a9f9bec459f26f0a1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101280"
---
# <a name="unterminated-comment"></a>Комментарий без признака завершения
Вы начали блок многострочного комментария, но не был завершен его должным образом. Многострочные комментарии начинаются с «/ *» комбинации и заканчиваться обратной "\*/» сочетания. Ниже представлен пример такого кода.  
  
```JavaScript  
/* This is a comment  
This is another part of the same comment.*/  
```  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь, что завершение многострочных комментариев с «* /».  
  
## <a name="see-also"></a>См. также  
 [Операторы комментария](../../javascript/reference/comment-statements-javascript.md)