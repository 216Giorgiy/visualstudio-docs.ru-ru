---
title: Правила использования средств профилирования | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 693b43d4a421bd0d0d87fbf485af88573b26adff
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754850"
---
# <a name="profiling-tools-usage-rules"></a>Правила использования средств профилирования
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Правила производительности в категории "Использование средств профилирования" обеспечивают рекомендации по наиболее эффективному использованию профилировщика для сбора данных.  
  
|||  
|-|-|  
|[DA0002. Отсутствует файл VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md)|Профилирование из командной строки может давать неполные данные для двоичных файлов [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Это может быть вызвано тем, что не были установлены правильные переменные среды.|  
|[DA0003. Много выборок в режиме ядра](../profiling/da0003-many-kernel-samples.md)|Было записано много выборок профилирования, которые произошли вне рамок выполнения целевого двоичного файла. Для сбора более точных данных можно использовать метод инструментирования.|  
|[DA0004. Потребление значительных ресурсов процессора](../profiling/da0004-high-processor-usage.md)|Данные профилирования показывают, что во время выполнения профилирования процессоры были постоянно заняты. Для сбора более точных данных можно использовать метод выборки.|  
|[DA0008. Собрано несколько образцов](../profiling/da0008-few-samples-collected.md)|Количество выборок, собранных в ходе сеанса профилирования, недостаточно и не является статистически значимым. Рекомендуется повторить профилирование, увеличив время работы приложения. Можно также использовать для сбора данных метод инструментирования.|  
|[DA0026. Обработка чрезмерного времени ядра ЦП](../profiling/da0026-excessive-kernel-cpu-time-processing.md)|Во время выполнения профилирования процессор значительное время находился в режиме ядра. Следует производить выборку, используя в качестве метрики системные вызовы, а не время.|  
|[DA0029. Неподдерживаемая версия среды CLR](../profiling/da0029-unsupported-clr-version.md)|Профилируемый двоичный файл используется версию [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], которая не поддерживается профилировщиком. В отчетах профилировщика невозможно разрешить имена символов.|  
|[DA0030. Сбор измерений взаимодействия уровней для проектов баз данных](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md)|Собрано значительное количество вызовов методов в пространстве имен <xref:System.Data?displayProperty=fullName>. Чтобы включить данные о вызовах базы данных, во время профилирования следует собирать данные о взаимодействии между уровнями.|
