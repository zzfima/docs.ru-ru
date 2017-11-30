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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="f7b62-104">Реализация событий шины с помощью RabbitMQ для среды разработки или тестирования</span><span class="sxs-lookup"><span data-stu-id="f7b62-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="f7b62-105">Нам необходимо начать с о том, что при создании вашего пользовательского события шина на RabbitMQ, выполняющийся в контейнере, как и приложение eShopOnContainers, его следует использовать только для разработки и тестовых средах.</span><span class="sxs-lookup"><span data-stu-id="f7b62-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="f7b62-106">Не следует использовать его для производственной среды, если вы создаете его как часть рабочей среде service bus.</span><span class="sxs-lookup"><span data-stu-id="f7b62-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="f7b62-107">Готовый важных возможностей, коммерческих служебной шины имеет могут отсутствовать шины простое пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="f7b62-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="f7b62-108">Пользовательская реализация eShopOnContainers шины события, по сути, представляет библиотеку с помощью RabbitMQ API.</span><span class="sxs-lookup"><span data-stu-id="f7b62-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="f7b62-109">Реализация позволяет микрослужбами подписаться на события, публиковать события и получать события, как показано на рисунке 8-21.</span><span class="sxs-lookup"><span data-stu-id="f7b62-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="f7b62-110">**На рисунке 8-21.**</span><span class="sxs-lookup"><span data-stu-id="f7b62-110">**Figure 8-21.**</span></span> <span data-ttu-id="f7b62-111">Реализация RabbitMQ шине событий</span><span class="sxs-lookup"><span data-stu-id="f7b62-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="f7b62-112">В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus.</span><span class="sxs-lookup"><span data-stu-id="f7b62-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="f7b62-113">Следующий пример основан на внедрение зависимостей так, что можно менять из этой версии для разработки и тестирования в рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="f7b62-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="f7b62-114">Реализация RabbitMQ шиной образец разработки и тестирования событий является стандартный код.</span><span class="sxs-lookup"><span data-stu-id="f7b62-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="f7b62-115">При этом приходится обрабатывать соединение с сервером RabbitMQ и выполнять код для публикации событий сообщение в очереди.</span><span class="sxs-lookup"><span data-stu-id="f7b62-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="f7b62-116">Он также должен реализовать словарь коллекций интеграции обработчиков событий для каждого типа события; Эти типы событий может иметь разные подписок для каждого получателя микрослужбу и другой экземпляр, как показано на рисунке 8-21.</span><span class="sxs-lookup"><span data-stu-id="f7b62-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="f7b62-117">Реализация простой метод с RabbitMQ "публикации"</span><span class="sxs-lookup"><span data-stu-id="f7b62-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="f7b62-118">Следующий код является частью реализации eShopOnContainers событий шины RabbitMQ, поэтому обычно не нужно закодировать, за исключением усовершенствования.</span><span class="sxs-lookup"><span data-stu-id="f7b62-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="f7b62-119">Код получает подключение и канал RabbitMQ, создает сообщение и затем публикует сообщение в очередь.</span><span class="sxs-lookup"><span data-stu-id="f7b62-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="f7b62-120">[Фактический код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) публикации метод в приложении eShopOnContainers повышается с помощью [Polly](https://github.com/App-vNext/Polly) повторите политику, которая повторных определенное число раз в случае, если контейнер RabbitMQ — не готов.</span><span class="sxs-lookup"><span data-stu-id="f7b62-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="f7b62-121">Это может произойти, когда docker составления запускается контейнеры; Например контейнер RabbitMQ начать медленнее, чем другие контейнеры.</span><span class="sxs-lookup"><span data-stu-id="f7b62-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="f7b62-122">Как упоминалось ранее, существует множество возможных конфигураций в RabbitMQ, поэтому этот код следует использовать только для сред разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="f7b62-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="f7b62-123">Реализация кода подписки с помощью API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="f7b62-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="f7b62-124">Как опубликовать кодом, следующий код — это упрощение часть реализации шины событий для RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="f7b62-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="f7b62-125">Опять же обычно не необходимо изменить его, если он повышается.</span><span class="sxs-lookup"><span data-stu-id="f7b62-125">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="f7b62-126">Каждый тип событий имеет связанные канала для получения событий из RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="f7b62-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="f7b62-127">Может иметь любое количество обработчиков событий каждого типа событий и канала при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f7b62-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="f7b62-128">Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущем микрослужбу, и его связанный объект IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="f7b62-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="f7b62-129">Затем код добавляет в список обработчиков событий, которые может включать каждого типа события интеграции на клиентом микрослужбу этого обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="f7b62-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="f7b62-130">Если клиентский код не уже подписался на событие, код создает канал для типа событий, он может получать события в стиле push из RabbitMQ при публикации события из любой другой службы.</span><span class="sxs-lookup"><span data-stu-id="f7b62-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f7b62-131">[Предыдущие] (интеграция событие основе микрослужбу communications.md) [Далее] (подписаться events.md)</span><span class="sxs-lookup"><span data-stu-id="f7b62-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
