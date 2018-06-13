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
ms.locfileid: "33580241"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="02cef-103">Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования</span><span class="sxs-lookup"><span data-stu-id="02cef-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="02cef-104">Начать следует с того, что если вы создаете пользовательскую шину событий на основе RabbitMQ в контейнере, как это делается в приложении eShopOnContainers, ее следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="02cef-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="02cef-105">Ее не следует применять в рабочей среде, если только вы не разрабатываете ее в рамках служебной шины, готовой к развертыванию в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="02cef-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="02cef-106">Простая пользовательская шина событий может быть лишена многих критически важных для рабочей среды возможностей, которыми обладают коммерческие служебные шины.</span><span class="sxs-lookup"><span data-stu-id="02cef-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="02cef-107">Одна из пользовательских реализаций шины событий в eShopOnContainers по сути представляет собой библиотеку, использующую интерфейс API RabbitMQ (есть и еще одна реализация на основе служебной шины Azure).</span><span class="sxs-lookup"><span data-stu-id="02cef-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span> 

<span data-ttu-id="02cef-108">Реализация шины событий с помощью RabbitMQ позволяет микрослужбам подписываться на события, публиковать и принимать их, как показано на рисунке 8-21.</span><span class="sxs-lookup"><span data-stu-id="02cef-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="02cef-109">**Рис. 8-21**.</span><span class="sxs-lookup"><span data-stu-id="02cef-109">**Figure 8-21.**</span></span> <span data-ttu-id="02cef-110">Реализация шины событий на основе RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="02cef-110">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="02cef-111">В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus.</span><span class="sxs-lookup"><span data-stu-id="02cef-111">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="02cef-112">Для этого применяется внедрение зависимостей, что позволяет переходить от этой версии для разработки и тестирования к рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="02cef-112">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="02cef-113">Реализация образца шины событий для разработки и тестирования на основе RabbitMQ представляет собой стандартный код.</span><span class="sxs-lookup"><span data-stu-id="02cef-113">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="02cef-114">Она должна обрабатывать подключение к серверу RabbitMQ и предоставлять код для публикации события сообщения в очередях.</span><span class="sxs-lookup"><span data-stu-id="02cef-114">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="02cef-115">Кроме того, должен быть реализован словарь коллекций, содержащий обработчики событий интеграции для каждого типа событий. Для каждого из этих типов событий могут применяться разные способы создания экземпляра и подписки для каждой микрослужбы-получателя, как показано на рисунке 8-21.</span><span class="sxs-lookup"><span data-stu-id="02cef-115">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="02cef-116">Реализация простого метода публикации с помощью RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="02cef-116">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="02cef-117">Приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ, которая улучшена в [реальном коде](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) проекта eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="02cef-117">The following code is part is a simplified event bus implementation for RabbitMQ, improved in the [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of eShopOnContainers.</span></span> <span data-ttu-id="02cef-118">Изменять этот код обычно не нужно, если в него не требуется внести улучшения.</span><span class="sxs-lookup"><span data-stu-id="02cef-118">You usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="02cef-119">Код получает соединение и канал с RabbitMQ, создает сообщение, а затем публикует его в очереди.</span><span class="sxs-lookup"><span data-stu-id="02cef-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="02cef-120">[Реальный код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) метода Publish в приложении eShopOnContainers улучшен с помощью политики повтора [Polly](https://github.com/App-vNext/Polly), которая пытается выполнить задачу повторно некоторое число раз, если контейнер RabbitMQ не готов.</span><span class="sxs-lookup"><span data-stu-id="02cef-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="02cef-121">Это может произойти, если контейнеры запускаются с помощью docker-compose. Например, контейнер RabbitMQ может запускаться медленнее других.</span><span class="sxs-lookup"><span data-stu-id="02cef-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="02cef-122">Как было сказано ранее, в RabbitMQ возможно множество конфигураций, поэтому этот код следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="02cef-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="02cef-123">Реализация кода подписки с помощью интерфейса API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="02cef-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="02cef-124">Так же как и в случае с кодом публикации, приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="02cef-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="02cef-125">Изменять его также обычно не нужно, если его не требуется улучшить.</span><span class="sxs-lookup"><span data-stu-id="02cef-125">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="02cef-126">С каждым типом событий связан канал для получения событий из RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="02cef-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="02cef-127">Для каждого канала и типа событий может быть столько обработчиков событий, сколько требуется.</span><span class="sxs-lookup"><span data-stu-id="02cef-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="02cef-128">Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущей микрослужбе, а также связанный с ним объект IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="02cef-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="02cef-129">Затем добавляется обработчик событий в список обработчиков событий, которые может иметь каждый тип событий интеграции в клиентской микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="02cef-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="02cef-130">Если код клиента еще не подписался на событие, для данного типа событий создается канал, который позволяет получать события из RabbitMQ принудительным образом, когда они публикуются из любой другой службы.</span><span class="sxs-lookup"><span data-stu-id="02cef-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="02cef-131">[Назад] (integration-event-based-microservice-communications.md) [Далее] (subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="02cef-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
