---
title: Устранение неполадок регистрации пакета RegPkg | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: troubleshooting
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6337562ff7a043c225dac678cb846cc76384c03c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58989776"
---
# <a name="troubleshooting-regpkg-package-registration"></a>Устранение неполадок регистрации пакета RegPkg
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!NOTE]
>  С помощью файлах pkgdef — предпочтительный способ зарегистрировать пакеты в Visual Studio. Это позволяет расширение развертывания без доступа в системный реестр. Файлов pkgdef создаются с помощью [программа CreatePkgDef](../../extensibility/internals/createpkgdef-utility.md).  
  
 Чтобы зарегистрировать пакет с помощью RegPkg в [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], необходимо использовать версию RegPkg, который подходит для вашего пакета.  
  
## <a name="regpkg-versions-related-to-package-versions"></a>Версии RegPkg, связанное с версиями пакета  
 Существуют две версии RegPkg. Одна версия входит в [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Эта версия используется для регистрации пакетов, созданных с помощью одного из следующих сборок:  
  
1. Microsoft.VisualStudioShell.9.0.dll  
  
2. Microsoft.VisualStudioShell.10.0.dll  
  
3. Microsoft.VisualStudioShell.11.0.dll  
  
   Его не удалось зарегистрировать пакетов, созданных с помощью более ранних Microsoft.VisualStudio.Shell.dll сборки.  
  
   На более раннюю версию RegPkg можно зарегистрировать пакеты, которые созданы с помощью Microsoft.VisualStudio.Shell.dll сборки. Тем не менее его не удалось зарегистрировать пакеты, созданные с помощью более поздней версии этой сборки.  
  
## <a name="see-also"></a>См. также  
 [Выпуск продукта](../../misc/releasing-a-visual-studio-integration-product.md)
