---
title: DA0029. Неподдерживаемая версия среды CLR | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a3855b8975684b088b2838a866db36e6ec19e665
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635544"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029. Неподдерживаемая версия среды CLR

|||
|-|-|
|Идентификатор правила|DA0029|
|Категория|Использование средств профилирования|
|Способ профилирования|Профилирование из командной строки|
|Сообщение|В процессе сбора данных обнаружена неподдерживаемая версия среды CLR. Невозможно надлежащим образом устранить конфликт управляемых символов.|
|Тип правила|Сведения.|

## <a name="cause"></a>Причина
 Предпринята попытка профилирования приложения, в котором используется платформа [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)], не поддерживаемая Средствами профилирования.

## <a name="rule-description"></a>Описание правила
 Это предупреждение выдается по той причине, что Средствам профилирования не удается разрешить символы в управляемом коде, выполняющемся в приложении. Средства профилирования не могут разрешать символы управляемого кода в приложениях для платформы [!INCLUDE[net_v11_long](../profiling/includes/net_v11_long_md.md)].

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Отсутствует.