---
title: Отображение пользовательского типа, с помощью DebuggerTypeProxy | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerTypeProxyAttribute class
- DebuggerTypeProxy attribute
ms.assetid: 943f3bb1-993e-4800-a47e-0af78b063014
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c379fbeb9d17f92dcc7067424ea06bb1a2805ed1
ms.sourcegitcommit: cd91a8a4f6086cda9ba6948be25864fc7d6b8e44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537547"
---
# <a name="tell-the-debugger-what-type-to-show-using-debuggertypeproxy-attribute-c-visual-basic-ccli"></a>Указать отладчику какие типов, чтобы отобразить использование атрибута DebuggerTypeProxy (C#, Visual Basic, C++выполняет)

Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> указывает прокси (заменяющий тип) для типа и изменяет способ отображения типа в окнах отладчика. При просмотре переменной, у которой есть прокси, прокси заменяет исходный тип при **отображении**. Окно переменных отладчика отображает только открытые члены прокси-типа. Закрытые члены не отображаются.

Данный атрибут может применяться к:

- Структуры
- Классы
- Сборки

> [!NOTE]
> Для машинного кода, этот атрибут поддерживается только в C++выполняет код.

Класс прокси-типа должен иметь конструктор, принимающий аргумент типа, который будет заменен прокси. Отладчик создает новый экземпляр класса прокси-типа всякий раз, когда требуется отобразить переменную конечного типа. Это может сказываться на производительности. Поэтому не следует выполнять в конструкторе больше действий, чем это действительно необходимо.

Для снижения потерь производительности вычислитель выражений не проверяет атрибуты при отображении прокси-типа до тех пор, пока тип не будет развернут щелчком по символу "+" в окне отладчика или путем применения атрибута <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Таким образом, не следует применять атрибуты к самому типу отображения. Атрибуты можно и нужно применять в основной части типа отображения.

Прокси-тип рекомендуется делать закрытым вложенным классом внутри класса, к которому применяется атрибут. В этом случае он может легко получить доступ к внутренним членам.

<xref:System.Diagnostics.DebuggerTypeProxyAttribute> может быть унаследован, поэтому если тип прокси-сервер указан в базовом классе его будут применяться ко всем производным классам, если эти производные классы не заданы собственные прокси-сервера типа.

Если атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> используется на уровне сборки, параметр `Target` указывает тип, который заменяется прокси.

Пример использования этого атрибута вместе с <xref:System.Diagnostics.DebuggerDisplayAttribute> и <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, см. в разделе[использование атрибута DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).

## <a name="using-generics-with-debuggertypeproxy"></a>Использование универсальных типов с атрибутом DebuggerTypeProxy

Поддержка универсальных типов ограничена. Для C# атрибут `DebuggerTypeProxy` поддерживает только открытые типы. Открытый тип (также называемый "не сконструированным" типом) — это универсальный тип, экземпляр которого создается без аргументов для параметров типа. Закрытые типы (также называемые сконструированными типами) не поддерживаются.

Синтаксис для открытого типа выглядит следующим образом:

`Namespace.TypeName<,>`

Этот синтаксис необходимо использовать при использовании универсального типа в качестве целевого типа в атрибуте `DebuggerTypeProxy`. Атрибут `DebuggerTypeProxy` предположит параметры типа самостоятельно.

Дополнительные сведения об открытых и закрытых типах в C# см. в разделе [спецификации языка C#](/dotnet/csharp/language-reference/language-specification), откройте раздел 20.5.2 и закрытые типы.

В Visual Basic синтаксис для открытых типов не поддерживается, поэтому данный способ для Visual Basic не подходит. Вместо этого необходимо использовать строковое представление имени открытого типа.

`"Namespace.TypeName'2"`

## <a name="see-also"></a>См. также

- [Использование атрибута DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)
- [Создание настраиваемых представлений собственных объектов](../debugger/create-custom-views-of-dot-managed-objects.md)
- [Повышение эффективности отладки с помощью атрибутов просмотра отладчика](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
