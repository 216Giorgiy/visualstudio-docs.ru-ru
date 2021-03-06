---
title: CA1004. Универсальные методы должны предоставлять параметр типа | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 458817ee19269735be181e08ed12ee1ecdee329f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58991739"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004. Универсальные методы должны предоставлять параметр типа
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|Категория|Microsoft.Design|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Сигнатура параметра универсального видимый извне метод содержит типы, которые соответствуют все параметры метода.

## <a name="rule-description"></a>Описание правила
 Вывод – это то, как аргумент типа универсального метода определяется по типу аргумента, переданного методу, а не по явному указанию аргумента типа. Чтобы задействовать вывод, сигнатура параметра универсального метода должна включать параметр, тип которого совпадает с параметром типа для метода. В этом случае аргумент типа указывать не обязательно. При использовании вывода для всех параметров типа синтаксис вызова универсальных и неуниверсальных методов экземпляра является одинаковым. Это повышает удобство использования универсальных методов.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение этого правила, измените структуру, так что сигнатура параметра содержит тот же тип для каждого параметра типа метода.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует. Использование универсальных типов в синтаксисе, который прост для понимания и использования сокращает время, необходимое для обучения и увеличивает скорость внедрения новых библиотек.

## <a name="example"></a>Пример
 Следующий пример показывает синтаксис вызова двух универсальных методов. Аргумент типа для `InferredTypeArgument` выводится и тип аргумента для `NotInferredTypeArgument` должен быть явно указан.

 [!code-csharp[FxCop.Design.Inference#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/cs/FxCop.Design.Inference.cs#1)]
 [!code-vb[FxCop.Design.Inference#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/vb/FxCop.Design.Inference.vb#1)]

## <a name="related-rules"></a>Связанные правила
 [CA1005: Избегайте слишком много параметров в универсальных типах](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Коллекции должны реализовывать универсальный интерфейс](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Не объявляйте статические элементы в универсальных типах](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Не следует раскрывать универсальные списки](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Не вкладывайте универсальные типы в сигнатурах членов](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1003: Используйте экземпляры обработчика универсальных событий](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Используйте универсальные типы в том случае, если это уместно](../code-quality/ca1007-use-generics-where-appropriate.md)