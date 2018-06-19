---
title: Функция ScriptEngineBuildVersion (JavaScript) | Документы Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- ScriptEngineBuildVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngineBuildVersion function
ms.assetid: 7e255030-b0a3-420b-9c96-bb3e93c9333f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd458d43bebfb0d0e0b2cb6bebb483c22a60b4f0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
ms.locfileid: "24640024"
---
# <a name="scriptenginebuildversion-function-javascript"></a>Функция ScriptEngineBuildVersion (JavaScript)
Возвращает номер версии сборки используемого обработчика скриптов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ScriptEngineBuildVersion()  
```  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение соответствует данным о версии, содержащимся в библиотеке динамической компоновки (DLL) для используемого языка скриптов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано применение функции `ScriptEngineBuildVersion`.  
  
```JavaScript  
if(window.ScriptEngineBuildVersion) {  
    console.log(window.ScriptEngineBuildVersion());  
}  
  
// Output: <current build version>  
```  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Функция ScriptEngine](../../javascript/reference/scriptengine-function-javascript.md)   
 [Функция ScriptEngineMajorVersion](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [Функция ScriptEngineMinorVersion](../../javascript/reference/scriptengineminorversion-function-javascript.md)