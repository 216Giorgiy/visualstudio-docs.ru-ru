---
title: '&lt;документ&gt; элемент (Разработка решений Office в Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 36d822d60d1a28d48f660f6d358b75bf4a913048
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54866390"
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;документ&gt; элемент (Разработка решений Office в Visual Studio)
  `document` Элемент `vstov4` пространства имен хранятся сведения о настройках для настроек уровня документа.

## <a name="syntax"></a>Синтаксис

```xml
<document solutionId />
```

## <a name="elements-and-attributes"></a>Элементы и атрибуты
 Требуется только для настроек уровня документа. Элемент `document` находится в пространстве имен `vstov4` . Элемент `document` имеет перечисленные ниже атрибуты.

|Атрибут|Описание|
|---------------|-----------------|
|`solutionId`|Обязательный. GUID, используемый средствами Visual Studio для Office runtime для уникальной идентификации решения уровня документа. Это значение хранится в виде _AssemblyLocation пользовательского свойства документа. Дополнительные сведения см. в разделе [Общие сведения о свойствах пользовательского документа](../vsto/custom-document-properties-overview.md).|

 У элемента`document` нет дочерних элементов.

## <a name="document-level-customization-example"></a>Пример настройки на уровне документа

### <a name="description"></a>Описание:
 В следующем примере кода показано `document` элемент в решении Office уровня документа, развернутых с помощью [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Данный пример кода является частью большего примера, приведенного в [манифесты приложений для решений Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Код

```xml
<vstov4:document
  solutionId="73e" />
```

## <a name="see-also"></a>См. также

- [Манифесты приложений для решений Office](../vsto/application-manifests-for-office-solutions.md)
- [Манифесты развертывания для решений Office](../vsto/deployment-manifests-for-office-solutions.md)
- [Манифест приложения ClickOnce](../deployment/clickonce-application-manifest.md)