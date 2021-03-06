---
title: Команда "Путь к символам" | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 27c4c8ac23e2524245107d9052642350e9db09d2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59670407"
---
# <a name="symbol-path-command"></a>Команда Symbol Path
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Задает список каталогов для поиска символов отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Аргументы  
 `pathname`  
 Необязательный параметр. Список путей, разделенных точкой с запятой, для поиска символов отладчиком.  
  
## <a name="remarks"></a>Примечания  
 Если `pathname` не указан, эта команда выводит список текущих путей к символам.  
  
## <a name="example"></a>Пример  
 Этот пример добавляет два пути в список каталогов символов.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Пример  
 Этот пример отображает список текущих путей к символам, разделенных точкой с запятой.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>См. также раздел  
 [Командное окно](../../ide/reference/command-window.md)   
 [Команды Visual Studio](../../ide/reference/visual-studio-commands.md)
