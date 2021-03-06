---
title: IDebugExpressionEvaluator2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2 interface
ms.assetid: cebe649f-1c77-4d33-854f-30d4f00eceb4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f7ae45b86db973e1358e5010b628a34bdd1d03e7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56718161"
---
# <a name="idebugexpressionevaluator2"></a>IDebugExpressionEvaluator2
> [!IMPORTANT]
>  В Visual Studio 2015 таким образом, реализации вычислители выражений является устаревшим. Сведения о реализации вычислители выражений CLR, см. в разделе [вычислители выражений CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) и [управляемых образец средства оценки выражений](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Представляет улучшенная версия вычислитель выражений (EE).

## <a name="syntax"></a>Синтаксис

```
IDebugExpressionEvaluator2 : IDebugExpressionEvaluator
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Этот интерфейс реализуется вычислитель выражений.

## <a name="methods"></a>Методы
 В дополнение к методам на [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) интерфейс, этот интерфейс реализует следующие методы:

|Метод|Описание:|
|------------|-----------------|
|[GetService](../../../extensibility/debugger/reference/idebugexpressionevaluator2-getservice.md)|Извлекает объект службы по заданному идентификатору.|
|[PreloadModules](../../../extensibility/debugger/reference/idebugexpressionevaluator2-preloadmodules.md)|Предварительно загружает модули, заданное поставщиком указанного символа.|
|[SetCallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcallback.md)|Включает средство оценки выражений (EE) для указания интерфейс обратного вызова, который ядро отладки (DE) будет использовать для чтения настроек метрик.|
|[SetCorPath](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcorpath.md)|Задает путь к общеязыковой среды выполнения (CLR), загрузить в отладчик.|
|[SetIDebugIDECallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setidebugidecallback.md)|Включает модуль отладки для передачи в обратный вызов средство оценки выражений во время инициализации.|
|[Terminate](../../../extensibility/debugger/reference/idebugexpressionevaluator2-terminate.md)|Останавливает и удаляет средство оценки выражений.|

## <a name="requirements"></a>Требования
 Заголовок: EE.h

 Пространство имен: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll