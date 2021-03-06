---
title: CA1724. Имена типов не должны совпадать с именами пространства имен
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f81327324de937df57edfb36cae34d613f6298a5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55953975"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724. Имена типов не должны совпадать с пространствами имен

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|Категория|Microsoft.Naming|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Имя типа соответствует имени указанного пространства имен, имеющий один или несколько типы, видимые извне. Сравнение имени выполняется без учета регистра.

## <a name="rule-description"></a>Описание правила

Имена типов, созданных пользователем не должны совпадать с именами на которые имеются ссылки пространств имен, имеющих типы, видимые извне. При нарушении этого правила приводит к уменьшению функциональности библиотеки.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Переименуйте тип таким образом, что он не совпадает с именем из указанного пространства имен, которое содержит типы, видимые извне.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Для разработки новых приложений, не известные сценарии возникнуть, когда необходимо подавить предупреждение из этого правила. Прежде чем можно подавить предупреждение, внимательно рассмотрите, каким образом пользователи библиотеки могут быть в замешательстве по соответствующим именем. Для доставки библиотек, возможно подавить предупреждение из этого правила.