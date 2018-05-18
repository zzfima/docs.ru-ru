---
title: Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: e2b0f1a6152df5d323164fb2eca102fcb973667e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования

Начать следует с того, что если вы создаете пользовательскую шину событий на основе RabbitMQ в контейнере, как это делается в приложении eShopOnContainers, ее следует использовать только в средах разработки и тестирования. Ее не следует применять в рабочей среде, если только вы не разрабатываете ее в рамках служебной шины, готовой к развертыванию в рабочей среде. Простая пользовательская шина событий может быть лишена многих критически важных для рабочей среды возможностей, которыми обладают коммерческие служебные шины.

Одна из пользовательских реализаций шины событий в eShopOnContainers по сути представляет собой библиотеку, использующую интерфейс API RabbitMQ (есть и еще одна реализация на основе служебной шины Azure). 

Реализация шины событий с помощью RabbitMQ позволяет микрослужбам подписываться на события, публиковать и принимать их, как показано на рисунке 8-21.

![](./media/image22.png)

**Рис. 8-21**. Реализация шины событий на основе RabbitMQ

В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus. Для этого применяется внедрение зависимостей, что позволяет переходить от этой версии для разработки и тестирования к рабочей версии.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

Реализация образца шины событий для разработки и тестирования на основе RabbitMQ представляет собой стандартный код. Она должна обрабатывать подключение к серверу RabbitMQ и предоставлять код для публикации события сообщения в очередях. Кроме того, должен быть реализован словарь коллекций, содержащий обработчики событий интеграции для каждого типа событий. Для каждого из этих типов событий могут применяться разные способы создания экземпляра и подписки для каждой микрослужбы-получателя, как показано на рисунке 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Реализация простого метода публикации с помощью RabbitMQ

Приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ, которая улучшена в [реальном коде](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) проекта eShopOnContainers. Изменять этот код обычно не нужно, если в него не требуется внести улучшения. Код получает соединение и канал с RabbitMQ, создает сообщение, а затем публикует его в очереди.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

[Реальный код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) метода Publish в приложении eShopOnContainers улучшен с помощью политики повтора [Polly](https://github.com/App-vNext/Polly), которая пытается выполнить задачу повторно некоторое число раз, если контейнер RabbitMQ не готов. Это может произойти, если контейнеры запускаются с помощью docker-compose. Например, контейнер RabbitMQ может запускаться медленнее других.

Как было сказано ранее, в RabbitMQ возможно множество конфигураций, поэтому этот код следует использовать только в средах разработки и тестирования.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Реализация кода подписки с помощью интерфейса API RabbitMQ

Так же как и в случае с кодом публикации, приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ. Изменять его также обычно не нужно, если его не требуется улучшить.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();
        
        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

С каждым типом событий связан канал для получения событий из RabbitMQ. Для каждого канала и типа событий может быть столько обработчиков событий, сколько требуется.

Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущей микрослужбе, а также связанный с ним объект IntegrationEvent. Затем добавляется обработчик событий в список обработчиков событий, которые может иметь каждый тип событий интеграции в клиентской микрослужбе. Если код клиента еще не подписался на событие, для данного типа событий создается канал, который позволяет получать события из RabbitMQ принудительным образом, когда они публикуются из любой другой службы.


>[!div class="step-by-step"]
[Назад] (integration-event-based-microservice-communications.md) [Далее] (subscribe-events.md)
