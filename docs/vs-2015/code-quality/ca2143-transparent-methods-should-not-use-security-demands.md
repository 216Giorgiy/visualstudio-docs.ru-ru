---
title: CA2143. Прозрачные методы не должны использовать требования безопасности | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2143
ms.assetid: 5d3923d7-cf40-4512-bc5c-0db0e0d6e25a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5f9983f832c8793140f79e9b835e26e44fae1927
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58992042"
---
# <a name="ca2143-transparent-methods-should-not-use-security-demands"></a>CA2143. Прозрачные методы не должны использовать требования безопасности
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotDemand|
|CheckId|CA2143|
|Категория|Microsoft.Security|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Tranparent тип или метод декларативно помечается <xref:System.Security.Permissions.SecurityAction?displayProperty=fullName> `.Demand` запросу или вызовы методов <xref:System.Security.CodeAccessPermission.Demand%2A?displayProperty=fullName> метод.

## <a name="rule-description"></a>Описание правила
 Прозрачный для системы безопасности код не должен отвечать за проверку безопасности операции и поэтому не должен требовать разрешений. Прозрачный для системы безопасности код должен использовать полные требования для принятия решений по безопасности, и критичный в плане безопасности код не должен полагаться на прозрачный код, чтобы создать полное требование. Вместо этого следует надежными с точки зрения любой код, который выполняет проверки безопасности, такие как требования безопасности.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Как правило, чтобы устранить нарушение этого правила, пометьте метод <xref:System.Security.SecuritySafeCriticalAttribute> атрибута. Можно также удалить требование.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Для этого правила отключать вывод предупреждений не следует.

## <a name="example"></a>Пример
 Правило файлы на следующий код, поскольку прозрачный метод создает требование декларативной безопасности.

 [!code-csharp[FxCop.Security.CA2143.TransparentMethodsShouldNotDemand#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2143.transparentmethodsshouldnotdemand/cs/ca2143 - transparentmethodsshouldnotdemand.cs#1)]

## <a name="see-also"></a>См. также
 [CA2142: Прозрачный код не должен быть защищен с помощью требований LinkDemand](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
