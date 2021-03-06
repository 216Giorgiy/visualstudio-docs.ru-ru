---
title: Типизированные и нетипизированные наборы данных
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: c83ba0bb-5425-4d47-8891-6b4dbf937701
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: d6a16b8f0752ca2ab063f8bbbaa966836856eb4f
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55927728"
---
# <a name="typed-vs-untyped-datasets"></a>Типизированные и нетипизированные наборы данных
Типизированный набор данных представляет собой набор данных сначала является производным от базового <xref:System.Data.DataSet> класса, а затем использует сведения из **конструктор наборов данных**, который хранится в XSD-файл, чтобы создать новый, строго типизированным класс набора данных. Сведения из схемы (таблицы, столбцы и т. д.) создается и компилируются в этот новый класс набора данных как набор первого класса объектов и свойств. Так как типизированный набор данных наследует от базового <xref:System.Data.DataSet> класса, типизированный класс предполагается, что все функциональные возможности <xref:System.Data.DataSet> класса и может использоваться с методами, которые принимают экземпляр <xref:System.Data.DataSet> класс в качестве параметра.

 Нетипизированный набор данных, напротив, не имеет соответствующей встроенной схемы. Как и в типизированный набор данных, нетипизированный набор данных содержит таблицы, столбцы и т. д. — но те, они доступны только как коллекции. (Тем не менее, создав вручную таблицы и другие элементы данных в нетипизированный набор данных, можно экспортировать структуру набора данных в качестве схемы с помощью набора данных <xref:System.Data.DataSet.WriteXmlSchema%2A> метод.)

## <a name="contrast-data-access-in-typed-and-untyped-datasets"></a>Доступ к данным контрастности в типизированные и нетипизированные наборы данных
 Класс для типизированного набора данных имеет объектную модель, в котором его свойства принимают фактические имена таблиц и столбцов. Например если вы работаете с типизированный набор данных, может ссылаться на столбец, с помощью следующего кода:

 [!code-csharp[VbRaddataDatasets#4](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_1.cs)]
 [!code-vb[VbRaddataDatasets#4](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_1.vb)]

 Напротив Если вы работаете с нетипизированный набор данных, ниже приведен аналогичный код:

 [!code-csharp[VbRaddataDatasets#5](../data-tools/codesnippet/CSharp/typed-vs-untyped-datasets_2.cs)]
 [!code-vb[VbRaddataDatasets#5](../data-tools/codesnippet/VisualBasic/typed-vs-untyped-datasets_2.vb)]

 Типизированный доступ не только более удобными для чтения, а также полностью поддерживается технологией IntelliSense в Visual Studio **редактор кода**. Кроме того, что проще работать, синтаксис для типизированного набора данных предоставляет тип проверки во время компиляции, значительно уменьшая вероятность ошибок при присвоении значений элементам набора данных. Если изменить имя столбца в вашей <xref:System.Data.DataSet> класса и затем скомпилировать приложение, вы получите ошибку построения. Двойным щелчком этой ошибки сборки в **список задач**, вы можете перейти непосредственно к строке(-ам) кода, которые ссылаются на старое имя столбца. Доступ к таблицам и столбцам в типизированном наборе данных также немного быстрее, во время выполнения, так как доступ определяется во время компиляции, а не с помощью коллекций во время выполнения.

 Несмотря на то, что типизированных наборов данных имеют много преимуществ, нетипизированный набор данных полезен в различных обстоятельствах. Самый очевидный случай — когда схема не доступен для набора данных. Это может произойти, например, если приложение взаимодействует с компонентом, который возвращает набор данных, но вы не знаете заранее Каково его структуру. Аналогичным образом бывают случаи, при работе с данными, не имеет статической предопределенной структуры. В этом случае нецелесообразно использовать типизированный набор данных, так как вам пришлось повторно создавать класс типизированного набора данных при каждом изменении в структуре данных.

 Как правило бывает много случаев, когда можно динамически создать набор данных без схемы доступны. В этом случае набор данных является просто удобной структуре, в котором можно хранить данные до тех пор, пока данные могут быть представлены в виде реляционной структуры. В то же время можно воспользоваться преимуществами возможностей набора данных, такие как возможность сериализовать данные для передачи другому процессу или записать в XML-файл.

## <a name="see-also"></a>См. также

- [Средства набора данных](../data-tools/dataset-tools-in-visual-studio.md)