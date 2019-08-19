---
title: Сетка событий Azure — бессерверные приложения
description: Служба "Сетка событий Azure" — это бессерверное решение для обеспечения надежной доставки событий и маршрутизации в больших масштабах по модели с оплатой по событиям.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577577"
---
# <a name="event-grid"></a>Сетка событий

Служба " [Сетка событий Azure](/azure/event-grid/overview) " предоставляет бессерверную инфраструктуру для приложений на основе событий. Вы можете опубликовать в сетке событий из любого источника и использовать сообщения с любой платформы. Служба "Сетка событий" также имеет встроенную поддержку событий из ресурсов Azure для упрощения интеграции с вашими приложениями. Например, можно подписываться на события хранилища BLOB-объектов, чтобы уведомить приложение о передаче файла. Затем приложение может опубликовать пользовательское сообщение сетки событий, которое будет использоваться другими облачными или локальными приложениями. Сетка событий была разработана для надежного управления крупномасштабным масштабированием. Вы получаете преимущества публикации и подписки на сообщения без дополнительных затрат на настройку необходимой инфраструктуры.

![Эмблема сетки событий](./media/event-grid-logo.png)

Ниже перечислены основные возможности сетки событий.

* Полностью управляемая маршрутизация событий.
* Доставка событий почти в реальном времени в масштабе.
* Широкое покрытие как внутри, так и за пределами Azure.

## <a name="scenarios"></a>Сценарии

Сетка событий предназначено для нескольких различных сценариев. В этом разделе рассматриваются три наиболее распространенные из них.

### <a name="ops-automation"></a>Автоматизация операций

![Автоматизация операций](./media/ops-automation.png)

Служба "Сетка событий" позволяет ускорить автоматизацию и упростить принудительное применение политик, уведомляя службу [автоматизации Azure](https://docs.microsoft.com/azure/automation) при подготовке инфраструктуры.

### <a name="application-integration"></a>Интеграция приложений

![Интеграция приложений](./media/app-integration.png)

Службу "Сетка событий" можно использовать для подключения приложения к другим службам. Используя стандартные протоколы HTTP, даже устаревшие приложения можно легко изменить для публикации сообщений в сетке событий. Веб-перехватчики доступны для других служб и платформ для использования сообщений сетки событий.

### <a name="serverless-apps"></a>Бессерверные приложения

![Бессерверные приложения](./media/serverless-apps.png)

Служба "Сетка событий" может активировать функции Azure, Logic Apps или собственный пользовательский код. Главное преимущество использования сетки событий заключается в том, что она использует механизм *push-уведомлений* для отправки сообщений при возникновении событий. Архитектура push-уведомлений потребляет меньше ресурсов и масштабируется лучше , чем механизмы опроса. Опрос должен проверять наличие обновлений через равные промежутки времени.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Сетка событий и другие службы обмена сообщениями Azure

Azure предоставляет несколько служб обмена сообщениями, включая [концентраторы событий](https://docs.microsoft.com/azure/event-hubs) и [служебную шину](https://docs.microsoft.com/azure/service-bus-messaging). Каждая из них предназначена для решения определенного набора вариантов использования. На следующей схеме представлен общий обзор различий между службами.

![Сравнение обмена сообщениями Azure](./media/azure-messaging-services.png)

Более подробное сравнение см. в разделе [Сравнение служб обмена сообщениями](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Целевые показатели производительности

С помощью сетки событий можно использовать следующие гарантии производительности:

* Сквозная задержка от конца к концу в 99-м процентиль.
* доступность 99,99%.
* 10 000 000 событий в секунду для каждого региона.
* 100 000 000 подписки на регион.
* 50 — задержка MS Publisher.
* 24-часовая повторная попытка с экспоненциальной задержкой для гарантированной доставки в окне 1 день.
* Прозрачная региональная отработка отказа.

## <a name="event-grid-schema"></a>Схема сетки событий

Сетка событий использует стандартную схему для обертывания пользовательских событий. Схема похожа на оболочку, которая заключает в оболочку пользовательский элемент данных. Ниже приведен пример сообщения сетки событий.

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

Все сведения о сообщении являются стандартными, `data` за исключением свойства. Вы можете проверить сообщение и использовать `eventType` и `dataVersion` для десериализации пользовательской части полезных данных.

## <a name="azure-resources"></a>ресурсов Azure

Основным преимуществом использования службы "Сетка событий" является автоматическое сообщение, создаваемое Azure. В Azure ресурсы автоматически публикуются в *разделе* , который позволяет подписываться на различные события. В следующей таблице перечислены типы ресурсов, типы сообщений и события, которые доступны автоматически.

| Ресурс Azure | Тип события. | Описание |
| -------------- | ---------- | ----------- |
| Подписка Azure | Microsoft. Resources. Ресаурцевритесукцесс | Возникает при завершении операции создания или обновления ресурса. |
| | Microsoft. Resources. Ресаурцевритефаилуре | Возникает при сбое операции создания или обновления ресурса. |
| | Microsoft. Resources. ResourceWriteCancel | Возникает при отмене операции создания или обновления ресурса. |
|  | Microsoft. Resources. ResourceDeleteSuccess | Возникает при завершении операции удаления ресурса. |
|  | Microsoft. Resources. Ресаурцеделетефаилуре | Возникает при сбое операции удаления ресурса. |
| | Microsoft. Resources. ResourceDeleteCancel | Возникает при отмене операции удаления ресурса. Это событие происходит при отмене развертывания шаблона. |
| Хранилище больших двоичных объектов | Microsoft. Storage. BlobCreated | Возникает при создании большого двоичного объекта. |
| | Microsoft. Storage. BlobDeleted | Возникает при удалении большого двоичного объекта. |
| Концентраторы событий | Microsoft. EventHub. Каптурефилекреатед | Вызывается при создании файла записи.
| Центр Интернета вещей | Microsoft. Devices. Девицекреатед | Публикуется при регистрации устройства в центре Интернета вещей. |
| | Microsoft. Devices. Девицеделетед | Публикуется при удалении устройства из центра Интернета вещей. |
| Группы ресурсов | Microsoft. Resources. Ресаурцевритесукцесс | Возникает при завершении операции создания или обновления ресурса. |
| | Microsoft. Resources. Ресаурцевритефаилуре | Возникает при сбое операции создания или обновления ресурса. |
| | Microsoft. Resources. ResourceWriteCancel | Возникает при отмене операции создания или обновления ресурса. |
| | Microsoft. Resources. ResourceDeleteSuccess | Возникает при завершении операции удаления ресурса. |
| | Microsoft. Resources. Ресаурцеделетефаилуре | Возникает при сбое операции удаления ресурса. |
| | Microsoft. Resources. ResourceDeleteCancel | Возникает при отмене операции удаления ресурса. Это событие происходит при отмене развертывания шаблона. |

Дополнительные сведения см. в статье [схема событий службы "Сетка событий Azure](https://docs.microsoft.com/azure/event-grid/event-schema)".

Вы можете получить доступ к сетке событий из любого типа приложения, даже если оно выполняется локально.

## <a name="conclusion"></a>Заключение

В этой главе вы узнали о бессерверной платформе Azure, которая состоит из функций Azure, Logic Apps и службы "Сетка событий". Эти ресурсы можно использовать для создания полностью бессерверной архитектуры приложений или для создания гибридного решения, взаимодействующего с другими облачными ресурсами и локальными серверами. В сочетании с серверной платформой данных, такой как [Azure SQL](https://docs.microsoft.com/azure/sql-database) или [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), можно создавать полностью управляемые облачные приложения для машинного кода.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

* [Планы службы приложений](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Аналитика Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Службы Перенесите свое приложение в облако с помощью безсерверных функций Azure](https://channel9.msdn.com/events/Connect/2017/E102)
* [Сетка событий Azure](https://docs.microsoft.com/azure/event-grid/overview)
* [Схема событий службы "Сетка событий Azure"](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Концентраторы событий Azure](https://docs.microsoft.com/azure/event-hubs)
* [Документация по функциям Azure](https://docs.microsoft.com/azure/azure-functions)
* [Основные понятия триггеров и привязок в функциях Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Служебная шина Azure](https://docs.microsoft.com/azure/service-bus-messaging)
* [Хранилище таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Сравнение функций 1. x и 2. x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Подключение к локальным источникам данных с помощью локального шлюза данных Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Создайте свою первую функцию в портал Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Создайте первую функцию с помощью Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Создание первой функции с помощью Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Поддерживаемые языки функций](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Работа с Прокси-серверы Функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Назад](logic-apps.md)
>[Вперед](durable-azure-functions.md)
