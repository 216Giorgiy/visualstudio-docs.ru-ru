---
title: Обработчики изменений значений свойств домена | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, overriding event handlers
ms.assetid: 96d8f392-045e-4bc5-b165-fbaa470a3e16
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 500364d42c3c47b471102deee8f95193648183b8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60095637"
---
# <a name="domain-property-value-change-handlers"></a>Обработчики изменений значений свойств доменов
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Когда в доменном языке [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] меняется свойство домена, в обработчике свойства домена вызываются методы `OnValueChanging()` и `OnValueChanged()`. Чтобы отреагировать на внесенное изменение, можно переопределить эти методы.  
  
## <a name="overriding-the-property-handler-methods"></a>Переопределение методов обработчика свойства   
 Каждое свойство домена вашего доменного языка обрабатывается классом, вложенным в родительский класс домена. Его имя указывается в формате *PropertyName*PropertyHandler. Вы можете проверить этот класс обработчика свойств в файле **Dsl\Generated Code\DomainClasses.cs**. В этом классе непосредственно перед изменением значения вызывается метод `OnValueChanging()`, а сразу после изменения — метод `OnValueChanged()`.  
  
 Например, предположим, у вас есть класс домена с именем `Comment` , имеет строковое свойство домена с именем `Text` и целочисленное свойство с именем `TextLengthCount`. Чтобы вызвать `TextLengthCount` всегда, чтобы содержать длину `Text` строки, можно написать следующий код в отдельном файле в проекте Dsl:  
  
```  
// Domain Class "Comment":  
public partial class Comment   
{  
  // Domain Property "Text":  
  partial class TextPropertyHandler  
  {  
    protected override void OnValueChanging(CommentBase element, string oldValue, string newValue)  
    {  
      base.OnValueChanging(element, oldValue, newValue);  
  
      // To update values outside the Store, write code here.  
  
      // Let the transaction manager handle undo:  
      Store store = element.Store;  
      if (store.InUndoRedoOrRollback || store.InSerializationTransaction) return;  
  
      // Update values in the Store:  
      this.TextLengthCount = newValue.Length;  
    }  
  }  
}  
  
```  
  
 Об обработчиках свойств необходимо помнить следующее.  
  
- Методы обработчика свойств вызываются, когда пользователь вносит изменения в свойство домена, а также когда код программы назначает свойству другое значение.  
  
- Методы вызываются, только когда значение действительно меняется. Обработчик не вызывается, если код программы назначает значение, равное текущему.  
  
- Вычисляемые и пользовательские свойства доменов хранения не имеют методов OnValueChanged и OnValueChanging.  
  
- Обработчик изменений нельзя использовать для изменения нового значения. Если это необходимо, например для ограничения значения в определенном диапазоне, определите правило `ChangeRule`.  
  
- Обработчик изменений нельзя добавить в свойство, представляющее роль отношения. Вместо этого настройте правила `AddRule` и `DeleteRule` в классе отношения. Они запускаются, когда связи создаются или изменяются. Дополнительные сведения см. в разделе [распространение изменений в модели правил](../modeling/rules-propagate-changes-within-the-model.md).  
  
### <a name="changes-in-and-out-of-the-store"></a>Изменения внутри хранилища и за его пределами  
 Методы обработчика свойств вызываются внутри транзакции, запустившей изменение. Это значит, что можно внести и другие изменения в хранилище, не открывая новую транзакцию. Изменения могут привести к дополнительным вызовам обработчика.  
  
 Когда транзакция отменяется, выполняется заново или откатывается, вносить изменения в хранилище, то есть в элементы модели, отношения, фигуры, схемы соединителей или их свойства, не нужно.  
  
 Более того, обновлять значения не нужно и тогда, когда модель загружается из файла.  
  
 Изменения в модели следует защищать тестом следующего вида:  
  
```  
if (!store.InUndoRedoOrRollback   
         && !store. InSerializationTransaction)  
{ this.TextLength = ...; // in-store changes   
}  
```  
  
 Если же обработчик свойств распространяет изменения за пределы хранилища, например в файл, базу данных или переменные вне хранилища, эти изменения обязательно необходимо внести и обеспечить обновление внешних значений при выполнении операций отмены или повторного выполнения.  
  
### <a name="canceling-a-change"></a>Отмена изменения  
 Если изменение необходимо предотвратить, можно откатить текущую транзакцию. Это позволит, например, гарантировать, что свойство остается в определенном диапазоне.  
  
```  
if (newValue > 10)   
{ store.TransactionManager.CurrentTransaction.Rollback();  
  System.Windows.Forms.MessageBox.Show("Value must be less than 10");  
}  
  
```  
  
### <a name="alternative-technique-calculated-properties"></a>Альтернативный способ: вычисляемые свойства  
 В предыдущем примере показано, как использовать метод OnValueChanged() для распространения значений из одного свойства домена в другое. Каждое свойство имеет свое сохраненное значение.  
  
 Вместо этого можно определить в качестве вычисляемого производное свойство. В этом случае свойство не имеет собственного хранилища, а определяющая функция оценивается там, где это значение требуется. Дополнительные сведения см. в разделе [вычисляемые и пользовательские свойства хранилища](../modeling/calculated-and-custom-storage-properties.md).  
  
 Вместо предыдущего примера, можно задать **вид** поле `TextLengthCount` быть **Calculated** в определении DSL. Нужно предоставить собственный **получить** метод для этого свойства домена. **Получить** метод возвращает текущую длину `Text` строка.  
  
 Потенциальный недостаток вычисляемых свойств заключается в том, что выражение оценивается при каждом использовании значения, что может снижать производительность. Также к вычисляемым свойствам не применяются методы OnValueChanging() и OnValueChanged().  
  
### <a name="alternative-technique-change-rules"></a>Альтернативный способ: метод ChangeRule  
 Если метод ChangeRule определен, он выполняется в конце транзакции, изменяющей значение свойства.  Дополнительные сведения см. в разделе [распространение изменений в модели правил](../modeling/rules-propagate-changes-within-the-model.md).  
  
 Если в одной транзакции вносятся сразу несколько изменений, метод ChangeRule выполняется после их завершения. В отличие от этого, OnValue... методы выполняются в том случае, когда некоторые изменения не были выполнены. В зависимости от целей метод ChangeRule может оказаться более подходящим.  
  
 ChangeRule можно также использовать для корректировки нового значения свойства, чтобы сохранить его в определенном диапазоне.  
  
> [!WARNING]
>  Если правило вносит изменения в содержимое хранилища, могут запускаться другие правила и обработчики свойства. Если правило изменяет свойство, которое его запустило, оно будет вызвано вновь. Обязательно следите за тем, чтобы определения правил не приводили к бесконечному запуску.  
  
```  
using Microsoft.VisualStudio.Modeling;   
...  
// Change rule on the domain class Comment:  
[RuleOn(typeof(Comment), FireTime = TimeToFire.TopLevelCommit)]   
class MyCommentTrimRule : ChangeRule  
{  
  public override void   
    ElementPropertyChanged(ElementPropertyChangedEventArgs e)  
  {  
    base.ElementPropertyChanged(e);  
    Comment comment = e.ModelElement as Comment;  
  
    if (comment.Text.StartsWith(" ") || comment.Text.EndsWith(" "))  
      comment.Text = comment.Text.Trim();  
    // If changed, rule will trigger again.  
  }  
}  
  
// Register the rule:   
public partial class MyDomainModel   
{  
 protected override Type[] GetCustomDomainModelTypes()   
 { return new Type[] { typeof(MyCommentTrimRule) };   
 }  
}  
  
```  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Код в приведенном ниже примере переопределяет обработчик свойств домена и уведомляет пользователя об изменении свойства класса домена `ExampleElement`.  
  
### <a name="code"></a>Код  
  
```  
using DslModeling = global::Microsoft.VisualStudio.Modeling;  
using DslDesign = global::Microsoft.VisualStudio.Modeling.Design;  
  
namespace msft.FieldChangeSample  
{  
  public partial class ExampleElement  
  {  
    internal sealed partial class NamePropertyHandler  
    {  
      protected override void OnValueChanged(ExampleElement element,  
         string oldValue, string newValue)  
      {  
        if (!this.Store.InUndoRedoOrRollback)  
        {  
           // make in-store changes here...  
        }  
        // This part is called even in undo:  
        System.Windows.Forms.MessageBox.Show("Value Has Changed");  
        base.OnValueChanged(element, oldValue, newValue);  
      }  
    }  
  }  
}  
```  
