---
title: Компоненты отладчика | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: 31
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 12f865e7d4c44cfa4002b330ed85ec95f95a8ef9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58993837"
---
# <a name="debugger-components"></a>Компоненты отладчика
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Отладчик реализуется в виде пакета VSPackage и управление сеансом отладки всего. Сеанс отладки включает в себя следующие элементы:  
  
- **Отладка пакета:** [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Отладчик предоставляет тот же интерфейс пользователя, независимо от того, что выполняется отладка.  
  
- **Диспетчер отладки сеансов (SDM):** Предоставляет согласованный программный интерфейс для [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] отладчика для управления широкий набор ядер отладки. Она реализуется [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
- **Диспетчер отладки процессов (PDM):** Для всех выполняющихся экземплярах управляет [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], список всех программ, которые могут быть или выполняется отладка. Она реализуется [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
- **Отладка ядра (DE):** Отвечает за мониторинг программа отлаживается; состояние выполняющейся программе SDM и PDM взаимодействия и взаимодействия с вычислитель выражений и поставщик символов для анализа в реальном времени о состоянии памяти программы и переменные. Она реализуется [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (для языков, поддерживаемых) и сторонних поставщиков, которые требуется поддерживать собственные время выполнения.  
  
- **Средство оценки выражений (EE):** Обеспечивает поддержку динамической оценки переменных и выражений, предоставленные пользователем, при остановке программы в определенной точке. Она реализуется [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (для языков, поддерживаемых) и сторонних поставщиков, которые требуется поддерживать собственные языки.  
  
- **Поставщик символов (SP):** Также называется обработчик символов, сопоставляет символы отладки программы к запущенному экземпляру программы, так что можно предоставить полезные сведения (например, исходный код уровня отладки и вычисления выражений). Она реализуется [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (для среда CLR [со средой CLR] символов и базы данных программы [PDB] символов формата файла) и сторонних поставщиков, имеющих собственные собственный метод хранения отладочную информацию.  
  
  В примере ниже показан отношениях эти элементы отладчика Visual Studio.  
  
  ![Общие сведения о компонентах отладки](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пакет отладки](../../extensibility/debugger/debug-package.md)  
 Обсуждение отладки пакета, который выполняется в [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] оболочки и обрабатывает весь пользовательский Интерфейс.  
  
 [Диспетчер отладки процессов](../../extensibility/debugger/process-debug-manager.md)  
 Обзор функций PDM, — это диспетчер процессов, которые можно отлаживать.  
  
 [Диспетчер отладки сеансов](../../extensibility/debugger/session-debug-manager.md)  
 Определяет SDM, которая обеспечивает единое представление сеанс отладки в интегрированную среду разработки. SDM управляет DE.  
  
 [Модуль отладки](../../extensibility/debugger/debug-engine.md)  
 Документирует отладки служб, которые предоставляет DE.  
  
 [Рабочие режимы](../../extensibility/debugger/operational-modes.md)  
 Общие сведения о трех режимов, в которых может работать интегрированной среды разработки: режим конструктора, режим выполнения и режим приостановки выполнения. Также рассматриваются механизмы переходов.  
  
 [Вычислитель выражений](../../extensibility/debugger/expression-evaluator.md)  
 Описание назначения EE во время выполнения.  
  
 [Поставщик символов](../../extensibility/debugger/symbol-provider.md)  
 Описывает, как это сделать, в реализации, поставщик символов оценивает переменных и выражений.  
  
 [Визуализатор типов и пользовательское средство просмотра](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 Описывает тип визуализатора и пользовательское средство просмотра, и какую роль играет средство оценки выражений, в поддержке оба.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Отладчик: основные понятия](../../extensibility/debugger/debugger-concepts.md)  
 Описывает основные архитектурные понятия отладки.  
  
 [Контексты отладчика](../../extensibility/debugger/debugger-contexts.md)  
 Объясняет, как DE действует одновременно в рамках кода, документацию и контекстов вычисления выражения. Описание для каждого из трех контекстов, расположение, положения или оценки, относящиеся к его.  
  
 [Задачи отладки](../../extensibility/debugger/debugging-tasks.md)  
 Содержит ссылки на различные задачи отладки, такие как запуск программы и оценки выражений.  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
