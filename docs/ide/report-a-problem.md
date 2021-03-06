---
title: Сообщите о проблеме
description: Обзор средства "Сообщить о проблеме", включая состояния и определения проблем
ms.date: 11/15/2018
ms.custom: seodec18
ms.topic: conceptual
author: seaniyer
ms.author: seiyer
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 23ed63846eb11fd8eba95219aecaae3210e161fd
ms.sourcegitcommit: 1c8e07b98fc0a44b5ab90bcef77d9fac7b3eb452
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/25/2019
ms.locfileid: "56800535"
---
# <a name="overview-report-a-problem"></a>Общие сведения: Сообщение о проблеме

Средство "Сообщить о проблеме" позволяет сообществу разработчиков Visual Studio открывать вопросы. Каждый из ваших отчетов о проблеме становится рабочим элементом в нашей базовой инженерной системе, позволяя вам напрямую взаимодействовать с нашими командами разработчиков, чтобы помогать в выявлении и разрешении важных вопросов. Ваши отзывы, снабженные подробными диагностическими сведениями, крайне важны для улучшения семейства продуктов Visual Studio. Мы высоко ценим то, что вы находите время на сообщение о проблемах.

Кроме того, вы можете проголосовать за отзывы других членов сообщества, чтобы привлечь внимание к соответствующей проблеме и ускорить ее устранение.

## <a name="problem-status"></a>Состояние проблемы

После того как вы сообщите о проблеме, состояния обозначают место вашего обращения в рамках жизненного цикла. Когда сотрудники Майкрософт изучат ваш отзыв, они назначат ему соответствующее состояние.  Отслеживайте ход обработки своих отчетов о проблемах с помощью указанных ниже состояний по их значению и цветовой индикации.

![Состояние "Новое" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/New.jpg)

Состояние **Новое** указывает, что ошибка или проблема была описана впервые, и никакие действия пока не предпринимались.

- - -

![Состояние "Рассмотрено" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/Triaged.jpg)

Состояние **Рассмотрено** указывает, что выполнены предварительные действия, такие как модерация, перевод и начальная проверка на дублирование. Ваш запрос был передан на рассмотрение в соответствующую команду разработчиков.

- - -

![Состояние "На рассмотрении" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/UnderConsideration.jpg)

Состояние **На рассмотрении** указывает, что сотрудники Майкрософт анализируют влияние описанной вами проблемы на сообщество и назначат ей соответствующий приоритет. Если воздействие на сообщества пока неясно или незначительно, мы продолжим отслеживать проблему в этом состоянии.

- - -

![Состояние "Исследуется" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/UnderInvestigation.jpg)

Состояние **Исследуется** указывает, что инженеры активно работают над решением проблемы.

- - -

![Состояние "Требуется дополнительная информация" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/NeedMoreInfo.jpg)

Состояние **Требуется дополнительная информация** указывает, что нам нужны от вас дополнительные диагностические сведения, чтобы продвинуться в расследовании.  [Сведения о том, как реагировать на запросы "Требуется дополнительная информация".](./how-to-report-a-problem-with-visual-studio.md#when-further-information-is-needed-need-more-info)

- - -

![Состояние "Исправлено — ожидает выпуска" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/FixedPendingRelease.jpg)

Состояние **Исправлено — ожидает выпуска** указывает, что мы нашли решение проблемы и включим его в предстоящую предварительную версию или предстоящий выпуск.  Если исправление предоставляется в предварительной версии, проблема помечается тегом "fixed in" (исправлено в), указывающим на соответствующую предварительную версию.

- - -

![Состояние "Закрыто — исправлено" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedFixed.jpg)

Состояние **Закрыто — исправлено** указывает, что мы выпустили исправление для проблемы. Проблема также помечается тегом "fixed in:" (исправлено в), указывающим версию выпуска.

- - -

![Состояние "Закрыто — дубликат" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedDuplicate.jpg)

Состояние **Закрыто — дубликат** указывает, что эта проблема уже описана в другом отзыве. Мы предоставим вам ссылку, по которой можно отслеживать исходный отчет о проблеме.

- - -

![Состояние "Закрыто — низкий приоритет" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedLowerPriority.jpg)

Состояние **Закрыто — низкий приоритет** используется потому, что мы стремимся обеспечить наибольшую выгоду для своего сообщества разработчиков и обрабатывать проблемы, оказывающие наибольшее влияние на клиентов, в приоритетном порядке. Хотя мы не можем решить эту проблему в данный момент, можете быть уверены, что все ваши отзывы приносят пользу и способствуют улучшению Visual Studio.

- - -

![Состояние "Закрыто — не ошибка" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedNotaBug.jpg)

Состояние **Закрыто — не ошибка** указывает, что описанные функции предусмотрены проектом.

- - -

![Состояние "Закрыто — недостаточно сведений" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedNotEnoughInfo.jpg)

Состояние **Закрыто — недостаточно сведений** указывает, что у нас недостаточно информации для изучения этой проблемы. Мы с радостью пересмотрим этот отзыв после появления необходимой информации.

- - -

![Состояние "Закрыто — другой продукт" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedOtherProduct.jpg)

Состояние **Закрыто — другой продукт** указывает, что данная проблема относится к другому продукту. Конкретный продукт и связанные с ним ссылки указаны в комментарии от Майкрософт.

- - -

![Состояние "Закрыто — не будет исправлено" для отчета о проблеме в сообществе разработчиков](../ide/media/ProblemStates/ClosedWontFix.jpg)

Состояние **Закрыто — не будет исправлено** указывает, что мы не будем заниматься данной проблемой из-за слишком малого влияния на продукт или сообщество. Дополнительные сведения см. в комментарии от корпорации Майкрософт.  Хотя мы не можем решить эту проблему, можете быть уверены, что все ваши отзывы приносят пользу и способствуют улучшению Visual Studio.

- - -

## <a name="faq"></a>часто задаваемые вопросы

### <a name="how-can-i-increase-the-chance-of-my-problem-getting-resolved-quickly"></a>Как повысить шансы на быстрое разрешение моей проблемы?

Мы рекомендуем использовать поиск, чтобы убедиться, что ваша проблема еще не была описана. Если вы нашли существующий вопрос по вашей проблеме, проголосуйте за него.

 Предоставьте всю доступную информацию, чтобы помочь нашим специалистам воспроизвести проблему.  Эти сведения включают необходимые шаги для воспроизведения, фрагменты кода, снимки экрана, записи для воспроизведения, файлы журналов и другие артефакты.  Вот [как можно сообщить о проблеме в Visual Studio](./how-to-report-a-problem-with-visual-studio.md).

### <a name="how-is-my-feedback-prioritized"></a>Как назначается приоритет для моего отзыва?

Мы получаем от своих клиентов большое количество ценных отзывов. Чтобы принести максимальную пользу всем членам сообщества разработчиков, мы выводим оптимальное значение к каждому из вас, приоритизируем работу по тем отзывам, которые больше всего затрагивают это сообщество.

Даже если мы не в состоянии лично ответить на ваш отзыв, уверяем вас, что мы высоко ценим ваше мнение. Ваш отзыв обязательно будет направлен подходящей команде.

Мы действительно ценим то, что вы решили уделить время улучшению Visual Studio.

### <a name="what-actions-can-i-take-if-im-not-satisfied-with-the-resolution"></a>Какие действия можно предпринять, если решение меня не устраивает?

Наши специалисты делают все возможное, чтобы диагностировать и устранить возникающие у вас проблемы, однако в некоторых случаях их рекомендации могут не удовлетворять вас в полной мере. Оставьте комментарий для отзыва, указав, что именно вас не устраивает, и мы постараемся удовлетворить ваши потребности.

### <a name="how-will-i-get-notified-of-progress-on-my-feedback"></a>Как меня будут уведомлять о ходе обработки моего отзыва?

Команды инженеров Майкрософт будут взаимодействовать с вами, оставляя комментарии для отзыва и изменяя состояние вашего запроса по мере его обработки. Следите за уведомлениями по электронной почте, отправляемыми при смене состояния запроса или публикации комментария.  Вы можете настроить частоту уведомлений в параметрах профиля и настроек на сайте сообщества разработчиков.

### <a name="why-cant-i-add-a-problem-for-visual-studio-ide-on-the-developer-community-website"></a>Почему не удается добавить проблему для интегрированной среды разработки Visual Studio на веб-сайте сообщества разработчиков?

Отчеты о проблеме, созданные в Visual Studio, содержат диагностические сведения. Это важные сведения, которые предоставляют нашим инженерам контекст для полного понимания вашей проблемы и работы по ее устранению.

При отправке отчета через Visual Studio вы легко можете поделиться с нами обширной диагностической информацией, которая позволяет нам быстрее найти качественное решение, например крупными файлами журнала, сведениями о сбоях, снимками экрана, записями для воспроизведения и другими артефактами.