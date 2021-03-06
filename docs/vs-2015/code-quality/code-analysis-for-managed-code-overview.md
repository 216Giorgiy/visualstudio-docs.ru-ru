---
title: Общие сведения об анализе управляемого кода | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: overview
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
ms.assetid: 12ec0dab-46a4-43d8-984a-440730ef37a9
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a38909eb0917b3ad5b02d5e953c17c950c7c819e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54782855"
---
# <a name="code-analysis-for-managed-code-overview"></a>Общие сведения об анализе управляемого кода
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Анализа управляемого кода позволяет проанализировать управляемые сборки и получить такие сведения о сборках, как нарушения правил программирования и разработки, изложенных в руководствах по разработке Microsoft .NET Framework.  
  
 Средство анализа представляет проводимые во время анализа проверки в виде предупреждающих сообщений. В предупреждающих сообщениях указываются все проблемы, связанные с программированием и разработкой, и, по возможности, сведения о методах их устранения.  
  
## <a name="ide-integrated-development-environment-integration"></a>Интеграция в интегрированную среду разработки  
 Разработчики могут выполнять анализ кода проекта автоматически или вручную.  
  
 Для выполнения анализа кода при каждой сборке проекта выберите **Включить анализ кода в сборке (определяет константу CODE_ANALYSIS)** на странице свойств проекта. Дополнительные сведения см. в разделе [Как включить и отключить автоматический анализ кода](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).  
  
 Чтобы запустить анализ кода проекта вручную, в меню **Анализ** выберите пункт **Запустить анализ кода на**_имя_проекта_. Дополнительные сведения см. в разделе [Как включить и отключить автоматический анализ кода](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).  
  
## <a name="rule-sets"></a>Наборы правил  
 Правила анализа управляемого кода группируются в *наборы правил*. Пользователь может воспользоваться стандартными наборами правил Майкрософт или создать настраиваемый набор правил в соответствии со своими нуждами. Дополнительные сведения см. в разделе [Использование наборов правил для группировки правил анализа кода](../code-quality/using-rule-sets-to-group-code-analysis-rules.md).  
  
## <a name="in-source-suppression"></a>Подавление предупреждений в исходном коде  
 Зачастую удобно указать, что предупреждение неприменимо. Это позволяет сообщить разработчику и другими лицам, которые, возможно, будут проверять код позже, что предупреждение рассмотрено и либо отложено, либо проигнорировано.  
  
 Подавление предупреждений в исходном коде производится при помощи пользовательских атрибутов. Чтобы подавить предупреждение, добавьте атрибут `SuppressMessage` в исходный код, как показано в следующем примере:  
  
 ```csharp
 [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
 Public class MyClass
 {
     // code
 }
 ```
  
 Дополнительные сведения см. в разделе [Подавление предупреждений при помощи атрибута SuppressMessage](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md).  
  
## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Запуск анализа кода в рамках политики возврата  
 Каждая организация может предъявлять определенные требования к возвратам. В частности, может требоваться соблюдение следующих правил:  
  
- Возвращаемый код не содержит ошибок построения.  
  
- Анализ кода был проведен в рамках последнего построения.  
  
  Этого можно достичь, задав политики возврата. Дополнительные сведения см. в разделе [Улучшение качества кода с помощью политик возврата командного проекта](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).  
  
## <a name="team-build-integration"></a>Интеграция командного построения  
 Существует возможность использования интегрированных возможностей системы построения для запуска средства анализа в рамках процесса построения. Дополнительные сведения см. в разделе [Сборка приложения](http://msdn.microsoft.com/library/a971b0f9-7c28-479d-a37b-8fd7e27ef692).  
  
## <a name="see-also"></a>См. также раздел  
 [Использование наборов правил для группировки правил анализа кода](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)   
 [Практическое руководство. Включение и отключение автоматического анализа кода](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
