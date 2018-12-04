---
title: Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование RabbitMQ для реализации сообщений шины событий для событий интеграции для сред разработки или тестирования.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 6d855b56a7fd00b316dde599683900ad2db758d7
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672349"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="4579e-103">Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования</span><span class="sxs-lookup"><span data-stu-id="4579e-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="4579e-104">Начать следует с того, что если вы создаете пользовательскую шину событий на основе RabbitMQ в контейнере, как это делается в приложении eShopOnContainers, ее следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="4579e-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="4579e-105">Ее не следует применять в рабочей среде, если только вы не разрабатываете ее в рамках служебной шины, готовой к развертыванию в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="4579e-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="4579e-106">Простая пользовательская шина событий может быть лишена многих критически важных для рабочей среды возможностей, которыми обладают коммерческие служебные шины.</span><span class="sxs-lookup"><span data-stu-id="4579e-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="4579e-107">Одна из пользовательских реализаций шины событий в eShopOnContainers по сути представляет собой библиотеку, использующую интерфейс API RabbitMQ (есть и еще одна реализация на основе служебной шины Azure).</span><span class="sxs-lookup"><span data-stu-id="4579e-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span>

<span data-ttu-id="4579e-108">Реализация шины событий с помощью RabbitMQ позволяет микрослужбам подписываться на события, публиковать и принимать их, как показано на рисунке 6–21.</span><span class="sxs-lookup"><span data-stu-id="4579e-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![RabbitMQ выступает в роли посредника между издателем сообщения и подписчиками и обрабатывает распространение.](./media/image22.png)

<span data-ttu-id="4579e-110">**Рис. 6–21.**</span><span class="sxs-lookup"><span data-stu-id="4579e-110">**Figure 6-21.**</span></span> <span data-ttu-id="4579e-111">Реализация шины событий на основе RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="4579e-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="4579e-112">В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus.</span><span class="sxs-lookup"><span data-stu-id="4579e-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="4579e-113">Для этого применяется внедрение зависимостей, что позволяет переходить от этой версии для разработки и тестирования к рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="4579e-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="4579e-114">Реализация образца шины событий для разработки и тестирования на основе RabbitMQ представляет собой стандартный код.</span><span class="sxs-lookup"><span data-stu-id="4579e-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="4579e-115">Она должна обрабатывать подключение к серверу RabbitMQ и предоставлять код для публикации события сообщения в очередях.</span><span class="sxs-lookup"><span data-stu-id="4579e-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="4579e-116">Кроме того, должен быть реализован словарь коллекций, содержащий обработчики событий интеграции для каждого типа событий. Для каждого из этих типов событий могут применяться разные способы создания экземпляра и подписки для каждой микрослужбы-получателя, как показано на рисунке 6–21.</span><span class="sxs-lookup"><span data-stu-id="4579e-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="4579e-117">Реализация простого метода публикации с помощью RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="4579e-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="4579e-118">Приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ, которая улучшена в [реальном коде](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) проекта eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="4579e-118">The following code is part of a simplified event bus implementation for RabbitMQ, improved in the [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of eShopOnContainers.</span></span> <span data-ttu-id="4579e-119">Изменять этот код обычно не нужно, если в него не требуется внести улучшения.</span><span class="sxs-lookup"><span data-stu-id="4579e-119">You usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="4579e-120">Код получает соединение и канал с RabbitMQ, создает сообщение, а затем публикует его в очереди.</span><span class="sxs-lookup"><span data-stu-id="4579e-120">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="4579e-121">[Реальный код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) метода Publish в приложении eShopOnContainers улучшен с помощью политики повтора [Polly](https://github.com/App-vNext/Polly), которая пытается выполнить задачу повторно некоторое число раз, если контейнер RabbitMQ не готов.</span><span class="sxs-lookup"><span data-stu-id="4579e-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="4579e-122">Это может произойти, если контейнеры запускаются с помощью docker-compose. Например, контейнер RabbitMQ может запускаться медленнее других.</span><span class="sxs-lookup"><span data-stu-id="4579e-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="4579e-123">Как было сказано ранее, в RabbitMQ возможно множество конфигураций, поэтому этот код следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="4579e-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="4579e-124">Реализация кода подписки с помощью интерфейса API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="4579e-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="4579e-125">Так же как и в случае с кодом публикации, приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="4579e-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="4579e-126">Изменять его также обычно не нужно, если его не требуется улучшить.</span><span class="sxs-lookup"><span data-stu-id="4579e-126">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="4579e-127">С каждым типом событий связан канал для получения событий из RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="4579e-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="4579e-128">Для каждого канала и типа событий может быть столько обработчиков событий, сколько требуется.</span><span class="sxs-lookup"><span data-stu-id="4579e-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="4579e-129">Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущей микрослужбе, а также связанный с ним объект IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="4579e-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="4579e-130">Затем добавляется обработчик событий в список обработчиков событий, которые может иметь каждый тип событий интеграции в клиентской микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="4579e-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="4579e-131">Если код клиента еще не подписался на событие, для данного типа событий создается канал, который позволяет получать события из RabbitMQ принудительным образом, когда они публикуются из любой другой службы.</span><span class="sxs-lookup"><span data-stu-id="4579e-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4579e-132">[Назад](integration-event-based-microservice-communications.md)
>[Вперед](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="4579e-132">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>