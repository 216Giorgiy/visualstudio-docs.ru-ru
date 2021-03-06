---
title: Регистрация расширений платформы .NET Framework | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- Add References dialog box, registering extensions of the .NET Framework
- MSBuild, registering extensions of the .NET Framework
- .NET Framework extensions, registering
ms.assetid: deee6f53-ea87-4b88-a120-bea589822e03
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3cea1375b59b791c7c81c79be0a462d5eb690776
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59664180"
---
# <a name="registering-extensions-of-the-net-framework"></a>Регистрация расширений платформы .NET Framework
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Можно создать сборку, расширяющую определенную версию платформы .NET Framework. Чтобы отобразить сборку в диалоговом окне Visual Studio **Добавление ссылок**, необходимо добавить ее родительскую папку в системный реестр.  
  
 Например, предположим, что компания Trey Research разработала библиотеку, которая расширяет платформу .NET Framework 4. При этом сборки библиотеки должны отображаться в диалоговом окне **Добавление ссылок** при разработке проекта для платформы .NET Framework 4. Также предположим, что сборки установлены в папке C:\TreyResearch\Extensions4\, являются 64-разрядными и выполняются на 64-разрядном компьютере или являются 32-разрядными и выполняются на 32-разрядном компьютере.  
  
 Зарегистрируйте эту папку с помощью следующего раздела: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\. Присвойте этому разделу значение по умолчанию: C:\TreyResearch\Extensions4.  
  
> [!NOTE]
>  Номер сборки версии .NET Framework может быть другим.  
  
 Чтобы зарегистрировать 32-разрядную сборку на 64-разрядном компьютере, используйте узел Wow6432, например: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\v4.0.21006\AssemblyFoldersEx\TreyResearch\\.  
  
## <a name="see-also"></a>См. также  
 [Visual Studio Integration](../msbuild/visual-studio-integration-msbuild.md) (Интеграция Visual Studio)
