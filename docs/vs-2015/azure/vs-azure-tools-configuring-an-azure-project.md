---
title: Настройка проекта облачной службы в Visual Studio | Документация Майкрософт
description: Узнайте, как настроить проект облачной службы Azure в Visual Studio, в зависимости от требований для этого проекта.
author: ghogen
manager: douge
assetId: 609d6965-05cc-47b1-82dc-c76a92d4f295
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/06/2017
ms.author: ghogen
ms.openlocfilehash: 7417bc117de7dc472f413dd9145944cad2d48bb4
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "51002954"
---
# <a name="configure-an-azure-cloud-service-project-with-visual-studio"></a>Настройка проекта облачной службы Azure в Visual Studio
Можно настроить проект облачной службы Azure, в зависимости от требований для этого проекта. Можно задать свойства проекта для следующих категорий:

- **Публикация облачной службы в Azure** -можно задать свойство, чтобы убедиться в том, что существующей облачной службы, развернутой в Azure не будет случайно удалено.
- **Запуск или отладка облачной службы на локальном компьютере** -можно выбрать конфигурацию службы и указать, следует ли запускать эмулятор хранилища Azure.
- **Проверка пакета облачной службы при его создании** -можно обрабатывать все предупреждения как ошибки, чтобы она могла проверить, что выполняет развертывание пакета облачной службы без всяких ошибок. 

## <a name="steps-to-configure-an-azure-cloud-service-project"></a>Действия, чтобы настроить проект облачной службы Azure
1. Откройте или создайте проект облачной службы в Visual Studio

1. В **обозревателе решений**, щелкните правой кнопкой мыши проект и в контекстном меню выберите **свойства**.
   
1. На странице свойств проекта выберите **разработки** вкладки.

    ![Меню "Свойства проекта"](./media/vs-azure-tools-configuring-an-azure-project/solution-explorer-project-properties-menu.png)

1. Задайте **выдавать запрос перед удалением существующего развертывания** для **True**. Этот параметр позволяет убедиться, что вы не случайно удалите существующее развертывание в Azure

1. Выберите нужный **конфигурации службы** чтобы указать, какая конфигурация службы будет использоваться при запуске или отладке облачной службы локально. Дополнительные сведения о том, как изменить конфигурацию службы для роли см. в разделе [Настройка ролей для облачной службы Azure с помощью Visual Studio](./vs-azure-tools-configure-roles-for-cloud-service.md).

1. Задайте **Запуск эмулятора хранилища Azure** для **True** для запуска эмулятора хранения Azure, при запуске или отладке облачной службы локально.

1. Задайте **обрабатывать предупреждения как ошибки** для **True** чтобы запретить публикацию при наличии ошибок проверки пакетов.

1. Задайте **использовать порты веб-проекта** для **True** чтобы убедиться в том, что веб-роль использует тот же порт при каждом локальном запуске в IIS Express.

1. На панели инструментов Visual Studio, выберите **Сохранить**.

## <a name="next-steps"></a>Следующие шаги
- [Настройка проекта Azure с помощью нескольких конфигураций службы](vs-azure-tools-multiple-services-project-configurations.md)
