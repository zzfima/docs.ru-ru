---
title: Сетка событий Azure. Бессерверные приложения
description: Служба "Сетка событий Azure" — это бессерверное решение, обеспечивающее надежную доставку и маршрутизацию событий в больших масштабах согласно модели с оплатой за событие.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3c577139c12567e762aabd58c9dc29457fa37aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522713"
---
# <a name="event-grid"></a>Сетка событий Azure

[Сетка событий Azure](/azure/event-grid/overview) предоставляет бессерверную инфраструктуру для приложений, работающих на основе событий. Здесь вы можете публиковать события из любого источника и использовать сообщения с любой платформы. В Сетке событий также есть встроенная поддержка событий из ресурсов Azure, что упрощает интеграцию с вашими приложениями. Например, можно настроить подписку на события хранилища BLOB-объектов и включить уведомления о передаче файла в приложении. Затем приложение сможет публиковать пользовательское сообщение сетки событий, и его будут использовать другие облачные или локальные приложения. Сетка событий разработана для надежного управления крупномасштабной архитектурой. Вы получаете такие преимущества, как подписка на сообщения и их публикация, без дополнительных затрат на настройку необходимой инфраструктуры.

![Логотип Сетки событий Azure](./media/event-grid-logo.png)

Сетки событий обеспечивает такие основные возможности:

- полностью управляемая маршрутизация событий;
- доставка событий почти в реальном времени в масштабе;
- широкое покрытие как в Azure, так и вне платформы.

## <a name="scenarios"></a>Сценарии

Сетка событий предназначена для нескольких различных сценариев. В этом разделе рассматриваются три самых распространенных из них.

### <a name="ops-automation"></a>Автоматизация операций

![Автоматизация операций](./media/ops-automation.png)

Служба "Сетка событий" позволяет ускорить автоматизацию и упростить принудительное применение политик, уведомляя [службу автоматизации Azure](https://docs.microsoft.com/azure/automation) о готовности инфраструктуры к работе.

### <a name="application-integration"></a>Интеграция приложений

![Интеграция приложений](./media/app-integration.png)

Сетку событий можно использовать для связи приложения с другими службами. С помощью стандартных протоколов HTTP даже устаревшие приложения легко изменить, чтобы настроить публикацию сообщений Сетки событий. Веб-перехватчики других служб и платформ также могут использовать сообщения Сетки событий.

### <a name="serverless-apps"></a>Бессерверные приложения

![Бессерверные приложения](./media/serverless-apps.png)

Служба "Сетка событий" может активировать код Функций Azure, Logic Apps или пользовательский код. Главное преимущество этой службы в том, что для отправки сообщений при возникновении событий используется механизм *push*-уведомлений. Такая архитектура потребляет меньше ресурсов и масштабируется проще, чем при использовании механизмов *опроса*. При опросе должно проверяться наличие обновлений через равные промежутки времени.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Сравнение Сетки событий и других служб сообщений Azure

Azure предусматривает несколько служб сообщений, в том числе [Центры событий](https://docs.microsoft.com/azure/event-hubs) и [Служебную шину](https://docs.microsoft.com/azure/service-bus-messaging). Каждая из них предназначена для определенного набора вариантов использования. На схеме ниже показан общий обзор различий между этими службами.

![Сравнение служб сообщений Azure](./media/azure-messaging-services.png)

Более подробные сведения см. в статье о [сравнении служб сообщений](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Цели анализа производительности

Сетка событий является гарантией таких преимуществ производительности:

- совокупная задержка менее секунды при 99 процентиле;
- Доступность на уровне 99,99 %.
- 10 миллионов событий на регион в секунду;
- 100 миллионов подписок на регион;
- задержка для издателя в 50 мс;
- возможность повтора попыток на протяжении 24 часов с экспоненциальной задержкой гарантирует доставку в пределах 1-дневного окна;
- прозрачная отработка отказа между регионами.

## <a name="event-grid-schema"></a>Схема службы "Сетка событий"

Сетка событий использует стандартную схему для обертывания пользовательских событий. Схема похожа на конверт, в который заключается пользовательский элемент данных. Ниже приведен пример сообщения Сетки событий.

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

Все в сообщении является стандартным, кроме свойства `data`. Вы можете проверить сообщение, использовав `eventType` и `dataVersion` для десериализации пользовательской части полезных данных.

## <a name="azure-resources"></a>ресурсов Azure

Важное преимущество Сетки событий — автоматические сообщения, создаваемые Azure. В Azure ресурсы автоматически публикуются в определенном *разделе*, что позволяет подписываться на различные события. В таблице ниже перечислены типы ресурсов и сообщений, а также события, доступные автоматически.

| Ресурс Azure | Тип события. | Описание |
| -------------- | ---------- | ----------- |
| Подписка Azure | Microsoft.Resources.ResourceWriteSuccess | Возникает при успешном создании или обновлении ресурса. |
| | Microsoft.Resources.ResourceWriteFailure | Возникает при неудачном создании или обновлении ресурса. |
| | Microsoft.Resources.ResourceWriteCancel | Возникает при отмене создания или обновления ресурса. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Возникает при успешном удалении ресурса. |
|  | Microsoft.Resources.ResourceDeleteFailure | Возникает при неудачном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteCancel | Возникает при отмене удаления ресурса. Это событие происходит при отмене развертывания шаблона. |
| Хранилище BLOB-объектов | Microsoft.Storage.BlobCreated | Возникает при создании BLOB-объекта. |
| | Microsoft.Storage.BlobDeleted | Возникает при удалении BLOB-объекта. |
| Центры событий | Microsoft.EventHub.CaptureFileCreated | Вызывается при создании файла записи.
| Центр Интернета вещей | Microsoft.Devices.DeviceCreated | Публикуется при регистрации устройства в Центре Интернета вещей. |
| | Microsoft.Devices.DeviceDeleted | Публикуется при удалении устройства из Центра Интернета вещей. |
| Группы ресурсов | Microsoft.Resources.ResourceWriteSuccess | Возникает при успешном создании или обновлении ресурса. |
| | Microsoft.Resources.ResourceWriteFailure | Возникает при неудачном создании или обновлении ресурса. |
| | Microsoft.Resources.ResourceWriteCancel | Возникает при отмене создания или обновления ресурса. |
| | Microsoft.Resources.ResourceDeleteSuccess | Возникает при успешном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteFailure | Возникает при неудачном удалении ресурса. |
| | Microsoft.Resources.ResourceDeleteCancel | Возникает при отмене удаления ресурса. Это событие происходит при отмене развертывания шаблона. |

Дополнительные сведения о схеме событий службы "Сетка событий Azure" см. [здесь](https://docs.microsoft.com/azure/event-grid/event-schema).

Сетка событий доступна из приложений всех типов, даже если они работают локально.

## <a name="conclusion"></a>Заключение

В этой статье вы узнали о бессерверной платформе Azure, на которой сочетаются Функции Azure, Logic Apps и служба "Сетка событий". Эти ресурсы можно использовать для сборки приложения с полностью бессерверной архитектурой или гибридного решения, взаимодействующего с другими облачными ресурсами и локальными серверами. В сочетании с бессерверной платформой данных, такой как [SQL Azure](https://docs.microsoft.com/azure/sql-database) или [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction), можно создавать полностью управляемые и полностью облачные приложения.

## <a name="recommended-resources"></a>Рекомендуемые ресурсы

- [Обзор планов Службы приложений Azure](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [Application Insights](https://docs.microsoft.com/azure/application-insights)
- [Аналитика Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [Общие сведения Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102) (Перенос приложения в облако с помощью бессерверных Функций Azure)
- [Сетка событий Azure](https://docs.microsoft.com/azure/event-grid/overview)
- [Схема событий службы "Сетка событий Azure"](https://docs.microsoft.com/azure/event-grid/event-schema)
- [Центры событий Azure](https://docs.microsoft.com/azure/event-hubs)
- [Документация по Функциям Azure](https://docs.microsoft.com/azure/azure-functions)
- [Основные понятия. Триггеры и привязки в функциях Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
- [Служебная шина Azure](https://docs.microsoft.com/azure/service-bus-messaging)
- [хранилище таблиц Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [Сравнение Функций Azure версии 1.x и 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
- [Подключение к локальным источникам данных с помощью локального шлюза данных Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [Создание первой функции на портале Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [Создание первой функции с помощью Azure CLI](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [Создание первой функции с помощью Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [Поддерживаемые языки функций](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [Мониторинг Функций Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
- [Work with Azure Functions Proxies](https://docs.microsoft.com/azure/azure-functions/functions-proxies) (Работа с Прокси-серверами Функций Azure)

>[!div class="step-by-step"]
>[Назад](logic-apps.md)
>[Вперед](durable-azure-functions.md)
