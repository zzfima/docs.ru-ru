---
title: "Реализация событий шины с помощью RabbitMQ для среды разработки или тестирования"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация событий шины с помощью RabbitMQ для среды разработки или тестирования"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Реализация событий шины с помощью RabbitMQ для среды разработки или тестирования

Нам необходимо начать с о том, что при создании вашего пользовательского события шина на RabbitMQ, выполняющийся в контейнере, как и приложение eShopOnContainers, его следует использовать только для разработки и тестовых средах. Не следует использовать его для производственной среды, если вы создаете его как часть рабочей среде service bus. Готовый важных возможностей, коммерческих служебной шины имеет могут отсутствовать шины простое пользовательское событие.

Пользовательская реализация eShopOnContainers шины события, по сути, представляет библиотеку с помощью RabbitMQ API. Реализация позволяет микрослужбами подписаться на события, публиковать события и получать события, как показано на рисунке 8-21.

![](./media/image22.png)

**На рисунке 8-21.** Реализация RabbitMQ шине событий

В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus. Следующий пример основан на внедрение зависимостей так, что можно менять из этой версии для разработки и тестирования в рабочей версии.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

Реализация RabbitMQ шиной образец разработки и тестирования событий является стандартный код. При этом приходится обрабатывать соединение с сервером RabbitMQ и выполнять код для публикации событий сообщение в очереди. Он также должен реализовать словарь коллекций интеграции обработчиков событий для каждого типа события; Эти типы событий может иметь разные подписок для каждого получателя микрослужбу и другой экземпляр, как показано на рисунке 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Реализация простой метод с RabbitMQ "публикации"

Следующий код является частью реализации eShopOnContainers событий шины RabbitMQ, поэтому обычно не нужно закодировать, за исключением усовершенствования. Код получает подключение и канал RabbitMQ, создает сообщение и затем публикует сообщение в очередь.

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

[Фактический код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) публикации метод в приложении eShopOnContainers повышается с помощью [Polly](https://github.com/App-vNext/Polly) повторите политику, которая повторных определенное число раз в случае, если контейнер RabbitMQ — не готов. Это может произойти, когда docker составления запускается контейнеры; Например контейнер RabbitMQ начать медленнее, чем другие контейнеры.

Как упоминалось ранее, существует множество возможных конфигураций в RabbitMQ, поэтому этот код следует использовать только для сред разработки и тестирования.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Реализация кода подписки с помощью API RabbitMQ

Как опубликовать кодом, следующий код — это упрощение часть реализации шины событий для RabbitMQ. Опять же обычно не необходимо изменить его, если он повышается.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

Каждый тип событий имеет связанные канала для получения событий из RabbitMQ. Может иметь любое количество обработчиков событий каждого типа событий и канала при необходимости.

Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущем микрослужбу, и его связанный объект IntegrationEvent. Затем код добавляет в список обработчиков событий, которые может включать каждого типа события интеграции на клиентом микрослужбу этого обработчика событий. Если клиентский код не уже подписался на событие, код создает канал для типа событий, он может получать события в стиле push из RabbitMQ при публикации события из любой другой службы.


>[!div class="step-by-step"]
[Предыдущие] (интеграция событие основе микрослужбу communications.md) [Далее] (подписаться events.md)
