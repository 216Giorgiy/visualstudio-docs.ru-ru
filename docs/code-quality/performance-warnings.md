---
title: предупреждения производительности
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.performancerules
helpviewer_keywords:
- warnings, performance
- performance warnings
- performance, warnings
- managed code analysis warnings, performance warnings
ms.assetid: e014ac3a-02e6-46d9-942c-3491dd63782f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d44c9a4a5c59907c527c47523c6c758adaf7ee51
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938037"
---
# <a name="performance-warnings"></a>предупреждения производительности
Предупреждения о производительности поддерживают библиотеки высокой производительности и приложения.

## <a name="in-this-section"></a>В этом разделе

| Правило | Описание |
| - | - |
| [CA1800: Не делайте лишних приведений](../code-quality/ca1800-do-not-cast-unnecessarily.md) | Повторяющиеся приведения снижают производительность, особенно если приведения выполняются в компактных операторах итераций. |
| [CA1801: Проверьте неиспользуемые параметры](../code-quality/ca1801-review-unused-parameters.md) | Сигнатура метода включает параметр, не использующийся в основной части метода. |
| [CA1802: При необходимости использовать литералы](../code-quality/ca1802-use-literals-where-appropriate.md) | Поле объявляется статичным и доступным только для чтения (Shared и ReadOnly в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) и инициализируется со значением, вычисляемым во время компиляции. Поскольку значение, присвоенное конечному полю, вычисляется во время компиляции, замените объявление полем const (Const в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) таким образом, чтобы значение вычисляется во время компиляции, а не во время выполнения. |
| [CA1804: Удалите неиспользуемые локальные переменные](../code-quality/ca1804-remove-unused-locals.md) | Неиспользуемые локальные переменные и ненужные присвоения увеличивают размер сборки и снижают производительность. |
| [CA1806: Не игнорируйте результаты метода](../code-quality/ca1806-do-not-ignore-method-results.md) | Новый объект создается, но никогда не используется, вызывается метод, который создает и возвращает новую строку и новая строка никогда не используется или метода объекта модели компонентов (COM) или P/Invoke возвращает HRESULT или код ошибки, никогда не используется. |
| [CA1809: Избегайте чрезмерного использования локальных переменных](../code-quality/ca1809-avoid-excessive-locals.md) | Обычно для оптимизации производительности рекомендуется хранить значение не в памяти, а в регистре процессора. Это называется регистрацией значения.  Чтобы увеличить вероятность того, что все локальные переменные, следует ограничить их, Ограничьте число локальных переменных до 64. |
| [CA1810: Инициализируйте статические поля ссылочного типа встроенными](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md) | Если в типе объявляется явный статический конструктор, компилятор JIT добавляет проверку в каждый статический метод и конструктор экземпляров этого типа, чтобы убедиться, что статический конструктор уже вызывался ранее. Проверки статических конструкторов могут привести к снижению производительности. |
| [CA1811: Не используйте Невызываемый закрытый код](../code-quality/ca1811-avoid-uncalled-private-code.md) | Закрытый или внутренний член (на уровне сборки) не имеет вызывающих объектов в сборке, он не вызывается средой CLR и он не вызывается через делегат. |
| [CA1812: Избегайте неиспользуемых внутренних классов](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md) | Экземпляр типа уровня сборки не создается кодом в сборке. |
| [CA1813: Избегайте распечатанных атрибутов](../code-quality/ca1813-avoid-unsealed-attributes.md) | Библиотеки классов .NET Framework предоставляет методы для извлечения пользовательских атрибутов. По умолчанию эти методы осуществляют поиск иерархии наследования атрибутов. Если запечатать атрибут, поиск в иерархии наследования выполняться не будет, в результате чего может повыситься производительность. |
| [CA1814: Используйте массивы массивов вместо многомерных](../code-quality/ca1814-prefer-jagged-arrays-over-multidimensional.md) | Массив массивов — это массив, элементы которого сами являются массивами. Массивы, которые составляют элементы могут иметь различные размеры, что может привести к экономить пространство для некоторых наборов данных. |
| [CA1815: СЛЕДУЕТ Переопределяйте операторы Equals и равенства для типов значений](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md) | В унаследованной реализации Equals для типов значений используется библиотека отражения и сравнивается содержимое всех полей. Отражение является процессом, требующим с точки зрения вычислений больших затрат, и сравнение каждого поля на равенство может быть лишним. Если предполагается, что пользователи будут сравнивать, сортировать экземпляры или использовать их в качестве ключей хэш-таблиц, тип значения должен реализовывать Equals. |
| [CA1816: Вызовите GC. SuppressFinalize правильно](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md) | Метод, являющийся реализацией Dispose, не вызывает сборщик Мусора. SuppressFinalize, или метод, не являющийся реализацией Dispose, вызывает сборщик Мусора. SuppressFinalize или метод вызывает сборщик Мусора. SuppressFinalize и передает другое (Me в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). |
| [CA1819: Свойства не должны возвращать массивы](../code-quality/ca1819-properties-should-not-return-arrays.md) | Массивы, возвращаемые свойствами, не защищен от записи, даже если свойство доступно только для чтения. Чтобы защитить массив от изменений, свойство должно возвращать копию массива. Как правило, пользователи не понимают требований к производительности при вызове такого свойства. |
| [CA1820: Проверьте наличие пустых строк, длины строки](../code-quality/ca1820-test-for-empty-strings-using-string-length.md) | Сравнивать строки с использованием свойства String.Length или метода String.IsNullOrEmpty значительно быстрее, чем с помощью Equals. |
| [CA1821: удалите пустые завершающие методы](../code-quality/ca1821-remove-empty-finalizers.md) | Если возможно, старайтесь не использовать финализаторы, поскольку из-за отслеживания жизненного срока объектов снижается производительность программы. Пустой метод завершения создает дополнительную нагрузку на систему без каких-либо преимуществ. |
| [CA1822: Пометьте члены как статические](../code-quality/ca1822-mark-members-as-static.md) | Члены, не обращающиеся к данным экземпляра и не вызывающие методы экземпляра, можно пометить как статические (Shared в [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Если пометить методы как статические, компилятор предоставит этим членам невиртуальные места вызова. Это обеспечивает значительное повышение производительности при работе с кодом, для которого важна высокая производительность системы. |
| [CA1823: Избегайте неиспользуемых частных полей](../code-quality/ca1823-avoid-unused-private-fields.md) | Обнаружены закрытые поля, доступ к которым, судя по всему, не предоставляется в сборке. |
| [CA1824: СЛЕДУЕТ Пометьте сборки атрибутом NeutralResourcesLanguageAttribute](../code-quality/ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md) | Атрибут NeutralResourcesLanguage сообщает ResourceManager о языке, используемом для отображения независящих от языка и региональных параметров ресурсов для сборки. При этом повышается эффективность поиска первого загружаемого ресурса и может сократиться рабочее множество. |
