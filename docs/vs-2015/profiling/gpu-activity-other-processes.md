---
title: Активность GPU (другие процессы) | Документы Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a3b0e97d82d67916aa71f932038930dba48c17e4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54787523"
---
# <a name="gpu-activity-other-processes"></a>Активность GPU (другие процессы)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Сегменты **Активность GPU (другие процессы)** в представлении потоков визуализатора параллелизма представляют моменты времени, когда GPU выполнял обработку запросов от имени других процессов в системе. Эти запросы отправляются в GPU как пакеты прямого доступа к памяти (DMA).  Длина сегмента представляет количество времени, затраченного на обработку пакета графическим процессором.  
  
 При выборе такого типа сегмента в отчете на вкладке **Текущие** отображаются сведения об обработанном пакете.  Эти сведения включают время ожидания пакета в очереди оборудования, связанной с ядром DirectX; процесс, отправивший пакет; и время, которое потребовалось для обработки пакета.
