---
title: "\"Разное\", XML, текстовый редактор, диалоговое окно параметров | Документация Майкрософт"
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cfebf34b9fc45a94733b4b10cb22b74190ebb127
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667135"
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>«Разное», «XML», «Текстовый редактор», диалоговое окно «Свойства»
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

При помощи этого диалогового окна можно изменить настройки автоматического завершения и настройки схемы для XML Editor. Вы можете получить доступ к **параметры** диалоговое окно, в **средства** меню.  
  
> [!NOTE]
>  Эти параметры доступны при выборе **текстовый редактор** папке **XML** папку, а затем **Разное** параметр из **параметры** диалоговое окно.  
  
## <a name="auto-insert"></a>Автоматическая вставка  
 **Закрывающие теги**  
 Если установлен параметр автозаполнения, редактор автоматически добавляет закрывающий тег при вводе правой угловой скобки (>), чтобы закрыть открывающий тег, если тег еще не закрыт. Это поведение установлено по умолчанию.  
  
 Завершение пустого элемента не зависит от параметра автозаполнения. Можно автоматически заполнить пустой элемент, введя символ «обратная косая черта» (/).  
  
 **Кавычки атрибутов**  
 При вводе XML-атрибутов редактор вставляет символы `=" "` и устанавливает внутри них знак вставки (^).  
  
 По умолчанию выбрано.  
  
 **Объявления пространств имен**  
 Редактор автоматически вставляет декларации пространств имен там, где они необходимы.  
  
 По умолчанию выбрано.  
  
 **Прочая разметка (комментарии, CDATA)**  
 Комментарии, CDATA, DOCTYPE, инструкции по обработке и другие элементы разметки завершаются автоматически.  
  
 По умолчанию выбрано.  
  
## <a name="network"></a>Сеть  
 **Автоматически загружать определения DTD и схемы**  
 Схемы и определения DTD загружаются автоматически с адресов HTTP. В этой функции используется System.Net в режиме автоматического определения прокси-сервера.  
  
 По умолчанию выбрано.  
  
## <a name="outlining"></a>Структуризация  
 **Переходить в режим структурирования после открытия файлов**  
 Включает возможность структурирования при открытии файла.  
  
 По умолчанию выбрано.  
  
## <a name="caching"></a>Кэширование  
 **Схемы**  
 Определяет местоположение кэша схемы. «Обзор» (**...** ) открывает **Обзор каталога** диалоговое окно в текущее расположение кэша схемы. Можно выбрать другой каталог, или можно выбрать папку в диалоговом окне, щелкните правой кнопкой мыши и выберите **откройте** чтобы увидеть, что находится в каталоге.  
  
## <a name="see-also"></a>См. также  
 [Свойства XML-документа, окно "Свойства"](../xml-tools/xml-document-properties-properties-window.md)   
 [Компоненты редактора XML](../xml-tools/xml-editor-components.md)
