---
title: CA2201. Не порождайте исключения зарезервированных типов
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9db603567cb73827546bc488bf57aba641d97054
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946006"
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201. Не порождайте исключения зарезервированных типов

|||
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|CheckId|CA2201|
|Категория|Microsoft.Usage|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина

Метод создает тип исключения, который является слишком общим или, зарезервированные для среды выполнения.

## <a name="rule-description"></a>Описание правила

Следующие типы исключений имеют слишком общий характер, чтобы предоставляет достаточно сведений для пользователя:

- <xref:System.Exception?displayProperty=fullName>

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.SystemException?displayProperty=fullName>

Следующие типы исключений зарезервированы и должен быть создан только действием среда CLR:

- <xref:System.ExecutionEngineException?displayProperty=fullName>

- <xref:System.IndexOutOfRangeException?displayProperty=fullName>

- <xref:System.NullReferenceException?displayProperty=fullName>

- <xref:System.OutOfMemoryException?displayProperty=fullName>

**Не создавайте общих исключений**

Если вы throw исключения общего типа, таких как <xref:System.Exception> или <xref:System.SystemException> в библиотеке или платформе, вынуждает объекты-получатели перехватывать все исключения, включая неизвестных исключений, которые они не знают, как обрабатывать.

Вместо этого создать более производный тип, уже существует в структуре или создать собственный тип, производный от <xref:System.Exception>.

**Генерировать определенные исключения**

В следующей таблице показаны параметры и исключения, которые могут вызывать при проверке параметров, включая значение параметра в методе доступа set свойства:

|Описание параметра|Исключение|
|---------------------------|---------------|
|`null` Справочник по|<xref:System.ArgumentNullException?displayProperty=fullName>|
|За пределами допустимого диапазона значений (таких как индекс для коллекции или перечня)|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|Недопустимый `enum` значение|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|Содержит формат, который не соответствует спецификациям параметров метода (например, строка формата для `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|
|В противном случае недопустим|<xref:System.ArgumentException?displayProperty=fullName>|

Когда операция недопустима для текущего состояния объекта throw <xref:System.InvalidOperationException?displayProperty=fullName>

Исключение при выполнении операции над объект, который был удален <xref:System.ObjectDisposedException?displayProperty=fullName>

Если операция не поддерживается (например, в переопределенный **методы Stream.Write** в Stream, открыт для чтения) throw <xref:System.NotSupportedException?displayProperty=fullName>

Если преобразование может привести к переполнению (например, перегрузка оператора явного приведения) исключение <xref:System.OverflowException?displayProperty=fullName>

В других случаях, рекомендуется создать собственный тип, производный от <xref:System.Exception> и создает исключение, которое.

## <a name="how-to-fix-violations"></a>Устранение нарушений

Чтобы устранить нарушение этого правила, измените тип вызванного исключения для определенного типа, который не является одним из зарезервированных типов.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений

Для этого правила отключать вывод предупреждений не следует.

## <a name="related-rules"></a>Связанные правила

- [CA1031: Не перехватывайте типы общих исключений](../code-quality/ca1031-do-not-catch-general-exception-types.md)