---
title: Сетка событий Azure — Бессерверных приложений
description: Сетка событий Azure — это бессерверное решение для доставки событий надежных и маршрутизации в большом масштабе на модель оплаты за событие.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212187"
---
# <a name="event-grid"></a>"Сетка событий"

[Сетка событий Azure](/azure/event-grid/overview) предоставляет независимой от сервера инфраструктурой приложений на основе событий. Можно опубликовать в сетке событий из любого источника и получать сообщения с любой платформы. "Сетка событий" также имеет встроенную поддержку событий из ресурсов Azure для упрощения интеграции с приложениями. Например можно подписаться на события хранилища BLOB-объектов для уведомления приложения при отправке файла. Приложение затем можно опубликовать сообщение сетки пользовательское событие, используется в другом облаке или локальных приложений. "Сетка событий" был разработан для надежно обрабатывающих массивного масштабирования. Вы получаете преимущества публикации и подписки на сообщения без издержек по настройке необходимую инфраструктуру.

![Логотип сетки событий](./media/event-grid-logo.png)

Основные возможности "Сетка событий":

* Полностью управляемой маршрутизацией событий.
* Рядом с доставки событий в реальном времени в нужном масштабе.
* Широкий покрытие внутри и вне Azure.

## <a name="scenarios"></a>Сценарии

"Сетка событий" адреса нескольких различных сценариях. В этом разделе рассматриваются три наиболее распространенные из них.

### <a name="ops-automation"></a>Автоматизация операций

![Автоматизация операций](./media/ops-automation.png)

"Сетка событий" может помочь скорость автоматизации и упрощает применение политик, уведомляя о [службы автоматизации Azure](https://docs.microsoft.com/azure/automation) после подготовки инфраструктуры.

### <a name="application-integration"></a>Интеграция приложений

![Интеграция приложений](./media/app-integration.png)

"Сетка событий" можно использовать для подключения приложения к другим службам. С помощью стандартных протоколов HTTP, даже для устаревших приложений можно легко изменить для публикации сообщений "Сетка событий". Веб-перехватчики доступны для других служб и платформ для получения сообщений "Сетка событий".

### <a name="serverless-apps"></a>Бессерверные приложения

![Бессерверные приложения](./media/serverless-apps.png)

"Сетка событий" может активировать функции Azure, Logic Apps или собственный код. Главным преимуществом с помощью сетки событий является применение *принудительной* механизм для отправки сообщений при возникновении событий. Архитектура принудительной потребляет меньше ресурсов и масштабируется лучше, чем *опроса* механизмы. Опроса необходимо проверить наличие обновлений на регулярной основе.

## <a name="event-grid-vs-other-azure-messaging-services"></a>"Сетка событий" и других служб Azure для обмена сообщениями

Azure предоставляет несколько служб обмена сообщениями, включая [концентраторов событий](https://docs.microsoft.com/azure/event-hubs) и [служебной шины](https://docs.microsoft.com/azure/service-bus-messaging). Каждый предназначен для определенного набора вариантов использования. Следующей схеме представлен общий обзор различий между службами.

![Обмена сообщениями сравнения в Azure](./media/azure-messaging-services.png)

Более подробное сравнение см. в разделе [сравнение служб обмена сообщениями](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Целевые показатели по производительности

С помощью сетки событий, можно воспользоваться преимуществами следующих производительности гарантирует:

* Subsecond end-to-end задержки на 99-го процентиля.
* доступность 99,99%.
* 10 млн событий в секунду для каждого региона.
* 100 миллионов подписки на регион.
* Издатель задержке в 50 мс.
* 24-часовом повторных попыток с экспоненциальной отсрочки для гарантированной доставки в окне 1 день.
* Прозрачную региональную отработку отказа.

## <a name="event-grid-schema"></a>Схема сетки событий

Сетка событий использует со стандартной схемой программы-оболочки для пользовательских событий. Схема выглядит подобно конверт, обертывающий ваш пользовательский элемент data. Ниже приведен пример сообщения "Сетка событий".

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

Все о сообщение является стандартным, за исключением `data` свойство. Вы можете проверить сообщение и использовать `eventType` и `dataVersion` выполнить десериализацию настраиваемых часть полезных данных.

## <a name="azure-resources"></a>ресурсов Azure

Главным преимуществом с помощью сетки событий является автоматическое сообщения, созданные Azure. В Azure, ресурсы автоматически опубликовать *разделе* , позволяет подписаться на различные события. Ниже перечислены типы ресурсов, типы сообщений и событий, которые были доступны автоматически.

| Ресурсов Azure | Тип события. | Описание |
| -------------- | ---------- | ----------- |
| Подписка Azure | Microsoft.Resources.ResourceWriteSuccess | Возникает при создании ресурса, или операция обновления завершается успешно. |
| | Microsoft.Resources.ResourceWriteFailure | Вызывается, когда Создание ресурса или происходит сбой операции обновления. |
| | Microsoft.Resources.ResourceWriteCancel | Возникает при создании ресурса, или операция обновления отмене. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Возникает при успешном удалении ресурса. |
|  | Microsoft.Resources.ResourceDeleteFailure | Возникает при неудачном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteCancel | Вызывается, когда отменяется операция удаления ресурса. Это событие происходит при отмене развертывания шаблона. |
| Хранилище BLOB-объектов | Microsoft.Storage.BlobCreated | Возникает при создании большого двоичного объекта. |
| | Microsoft.Storage.BlobDeleted | Возникает при удалении большого двоичного объекта. |
| Концентраторы событий | Microsoft.EventHub.CaptureFileCreated | Возникает при создании файла записи.
| Центр Интернета вещей | Microsoft.Devices.DeviceCreated | Публикуется при регистрации устройства в центре Интернета вещей. |
| | Microsoft.Devices.DeviceDeleted | Публикуется при удалении устройства из центра Интернета вещей. |
| Группы ресурсов | Microsoft.Resources.ResourceWriteSuccess | Возникает при создании ресурса, или операция обновления завершается успешно. |
| | Microsoft.Resources.ResourceWriteFailure | Вызывается, когда Создание ресурса или происходит сбой операции обновления. |
| | Microsoft.Resources.ResourceWriteCancel | Возникает при создании ресурса, или операция обновления отмене. |
| | Microsoft.Resources.ResourceDeleteSuccess | Возникает при успешном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteFailure | Возникает при неудачном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteCancel | Вызывается, когда отменяется операция удаления ресурса. Это событие происходит при отмене развертывания шаблона. |

Дополнительные сведения см. в разделе [схема событий службы "Сетка событий Azure"](https://docs.microsoft.com/azure/event-grid/event-schema).

"Сетка событий" доступны из любого типа приложения, даже если он работает локально.

## <a name="conclusion"></a>Заключение

В этой главе вы узнали о платформе Azure без сервера, который состоит из функций Azure, Logic Apps и "Сетка событий". Можно использовать эти ресурсы для построения архитектуры полностью бессерверного приложения или создать гибридное решение, которое взаимодействует с другими облачными ресурсами, а также на локальных серверах. Вместе с платформой данных в бессерверной, такие как [Azure SQL](https://docs.microsoft.com/azure/sql-database) или [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), вы можете создавать полностью управляемая облачная собственного приложения.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

* [Планы службы приложений](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Аналитика Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure: Перенос приложения в облако с помощью бессерверных функций Azure](https://channel9.msdn.com/events/Connect/2017/E102)
* [Сетка событий Azure](https://docs.microsoft.com/azure/event-grid/overview)
* [Схема событий службы "Сетка событий" Azure](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Концентраторы событий Azure](https://docs.microsoft.com/azure/event-hubs)
* [Документация по функциям Azure](https://docs.microsoft.com/azure/azure-functions)
* [Триггеры функций Azure и основные понятия привязки](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
* [Служебная шина Azure](https://docs.microsoft.com/azure/service-bus-messaging)
* [Хранилище таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Сравнение функций 1.x и 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [Подключение к локальным источникам данных с Azure на локальный шлюз данных](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Создание первой функции на портале Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Создание первой функции с помощью Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Создание первой функции с помощью Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Функции поддерживаемые языки](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Мониторинг функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Работа с прокси функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Назад](logic-apps.md)
>[Вперед](durable-azure-functions.md)
