---
title: 'UML-схемы классов: Справочник по | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.common.generalization.properties
- vs.teamarch.logicalclassdiagram.toolbox
- vs.teamarch.UMLModelExplorer.association
- vs.teamarch.common.unspecifiedtype.properties
- vs.teamarch.logicalclassdiagram.diagram
- vs.teamarch.UMLModelExplorer.logicalclassdiagram
- vs.teamarch.UMLModelExplorer.generalization
- vs.teamarch.common.unspecifiedtype
helpviewer_keywords:
- UML diagrams, class
- diagrams - modeling, class
- UML, class diagrams
- class diagrams - UML
- diagrams - modeling, UML class
ms.assetid: b7c88be0-0d86-4d65-af74-f37e8812d20f
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 07930dc31651d11aedccc6c597070bbba62ff0b9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58993652"
---
# <a name="uml-class-diagrams-reference"></a>UML-схемы классов: Ссылка
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Схема классов UML описывает структуры объектов и информации, используемые приложением как для внутренних задач, так и в рамках взаимодействия с пользователями. Она описывает информацию без ссылки на какую-либо конкретную реализацию. Ее классы и отношения можно реализовать различными способами, например в виде таблиц базы данных, XML-узлов или композиций программных объектов.  
  
> [!NOTE]
>  Этот раздел посвящен UML-схемам классов. Существует другой вид схемы классов  схема классов .NET, которая используется для визуализации программного кода. Дополнительные сведения см. в разделе [проектирование и Просмотр классов и типов](http://go.microsoft.com/fwlink/?LinkId=142231).  
  
 Чтобы создать схему классов UML на **архитектура** меню, выберите **создать схему UML или схему слоев**. Дополнительные сведения о рисовании UML-схемах классов см. в разделе [UML-схемы классов: Рекомендации по](../modeling/uml-class-diagrams-guidelines.md). Дополнительные сведения о способах создания и схем моделирования см. в разделе [моделей и схем UML, изменить](../modeling/edit-uml-models-and-diagrams.md).  
  
 Чтобы узнать, какие версии Visual Studio поддерживают эту функцию, см. раздел [Поддержка версий для инструментов моделирования и архитектуры](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="reading-class-diagrams"></a>Чтение схем классов  
 В таблице в этом разделе описаны элементы, которые можно увидеть на схеме классов UML. Сведения о свойствах этих элементов см. в следующих разделах:  
  
- [Свойства типов на схемах классов UML](../modeling/properties-of-types-on-uml-class-diagrams.md)  
  
- [Свойства атрибутов на схемах классов UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md)  
  
- [Свойства операций на схемах классов UML](../modeling/properties-of-operations-on-uml-class-diagrams.md)  
  
- [Свойства ассоциаций на схемах классов UML](../modeling/properties-of-associations-on-uml-class-diagrams.md)  
  
  ![Три класса, представляющие связи и свойства](../modeling/media/uml-classovreading.png "UML_ClassOvReading")  
  
| **Фигуры** |       **Элемент**        |                                                                                                                                                             **Описание**                                                                                                                                                              |
|-----------|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     1     |        **Класс**         |                                                           Определение объектов, совместно обладающих заданными характеристиками структуры или поведения. Дополнительные сведения см. в разделе [свойства типов на UML схемах классов](../modeling/properties-of-types-on-uml-class-diagrams.md).                                                            |
|     1     |        Классификатор        |                                                                                                             Общее имя для класса, интерфейса или перечисления. Компоненты, варианты использования и субъекты также являются классификаторами.                                                                                                             |
|     2     | Элемент управления "Свернуть/развернуть" |                                                                                         Если сведения о классификаторе не отображаются, щелкните элемент развертывания в верхней левой части классификатора. Может также потребоваться щелкнуть элемент [+] для каждого сегмента.                                                                                         |
|     3     |      **Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))       |   Типизированное значение, прикрепленное к каждому экземпляру классификатора.<br /><br /> Чтобы добавить атрибут, щелкните **атрибуты** раздела и нажмите клавишу **ввод**. Введите сигнатуру атрибута. Дополнительные сведения см. в разделе [схемах классов свойства атрибутов на UML](../modeling/properties-of-attributes-on-uml-class-diagrams.md).   |
|     4     |      **Операция**       | Метод или функция, которые могут выполняться экземплярами классификатора. Чтобы добавить операцию, нажмите кнопку **операций** раздела и нажмите клавишу **ввод**. Введите сигнатуру операции. Дополнительные сведения см. в разделе [схемах классов свойства операций на UML](../modeling/properties-of-operations-on-uml-class-diagrams.md). |
|     5     |     **Ассоциации**      |                                                                  Отношение между членами двух классификаторов. Дополнительные сведения см. в разделе [свойства ассоциаций на UML схемах классов](../modeling/properties-of-associations-on-uml-class-diagrams.md).                                                                   |
|    5а     |     **Статистическая обработка**      |                                                                                                    Ассоциация, представляющая отношение совместного владения. **Статистической обработки** свойство роли владельца имеет значение **Shared**.                                                                                                     |
|    5б     |     **Композиция**      |                                                                                                      Ассоциация, представляющая отношение целого и части. **Статистической обработки** свойство роли владельца имеет значение **составного**.                                                                                                      |
|     6     |   **Имя ассоциации**   |                                                                                                                                         Имя ассоциации. Имя можно оставить пустым.                                                                                                                                          |
|     7     |      **Имя роли**       |                       Имя роли, представляющей один конец ассоциации. Может использоваться для ссылки на связанный объект. В предыдущем примере для любого заказа `O``O.ChosenMenu` является связанным меню.<br /><br /> Каждая роль имеет свои собственные свойства, перечисленные в свойствах ассоциации.                       |
|     8     |     **Кратность**     |                                         Указывает, сколько объектов на этом конце могут быть связаны с каждым объектом на другом конце. В примере каждый заказ должен быть связан только с одним меню.<br /><br /> **\\**\* означает, что верхний предел на число ссылок, который может предоставляться отсутствует.                                         |
|     9     |    **Обобщение**    |  *Конкретных* классификатор наследует часть своего определения от *Общие* классификатора. Общий классификатор находится на той стороне соединителя, где изображен наконечник стрелки. Атрибуты, ассоциации и операции наследуются специальным классификатором.<br /><br /> Используйте **наследования** средство, чтобы создать обобщение между двумя классификаторами.   |
  
 ![Пакет, содержащий интерфейс и перечисление](../modeling/media/uml-classovpackage.png "UML_ClassOvPackage")  
  
|Фигура|Элемент|Описание|  
|-----------|-------------|-----------------|  
|10|**Interface**|Определение части наблюдаемого извне поведения объекта. Дополнительные сведения см. в разделе [свойства типов на UML схемах классов](../modeling/properties-of-types-on-uml-class-diagrams.md).|  
|11|**Перечисление**|Классификатор, состоящий из набора значений литералов.|  
|12|**Пакет**|Группа классификаторов, ассоциаций, действий, жизненных циклов, компонентов и пакетов. Логическая схема классов показывает, что классификаторы членов и пакеты содержатся в пакете.<br /><br /> Имена действуют в пределах пакетов, чтобы **Class1** в **Package1** отличается от **Class1** вне этого пакета. Имя пакета отображается как часть **полное имя** свойств его содержимого.<br /><br /> Можно задать **связанный пакет** свойство любой UML-схемы для ссылки на пакет. После этого все элементы, создаваемые на этой схеме, становятся частью этого пакета. Они будут отображаться в пакете в **Обозреватель моделей UML**.|  
|13|**Import**|Отношение между пакетами, указывающее на то, что один пакет включает в себя все определения другого.|  
|14|**зависимость**|Определение или реализация зависимого классификатора может измениться, если изменяется классификатор, на который указывает стрелка.|  
  
 ![Реализация, показанная с помощью соединителя и без описания операций](../modeling/media/uml-classovrealize.png "UML_ClassOvRealize")  
  
|Фигура|**Элемент**|Описание|  
|-----------|-----------------|-----------------|  
|15|**Реализация**|Класс реализует операции и атрибуты, определенные интерфейсом.<br /><br /> Используйте **наследования** средство, чтобы создать реализацию между классом и интерфейсом.|  
|16|**Реализация**|Альтернативное представление того же самого отношения. Метка на символе, представляющем собой круг на вертикальной линии, определяет интерфейс.<br /><br /> Чтобы создать это представление, выберите существующее отношение реализации. Рядом с ассоциацией отображается тег действия. Щелкните тег действия и нажмите кнопку **Показывать без описания операций**.|  
  
## <a name="see-also"></a>См. также  
 [Изменение моделей и схем UML](../modeling/edit-uml-models-and-diagrams.md)   
 [Схемы классов UML: Рекомендации](../modeling/uml-class-diagrams-guidelines.md)   
 [Свойства типов на UML-схемах классов](../modeling/properties-of-types-on-uml-class-diagrams.md)   
 [Свойства атрибутов на UML-схемах классов](../modeling/properties-of-attributes-on-uml-class-diagrams.md)   
 [Свойства операций на UML-схемах классов](../modeling/properties-of-operations-on-uml-class-diagrams.md)   
 [Свойства ассоциаций на схемах классов UML](../modeling/properties-of-associations-on-uml-class-diagrams.md)
