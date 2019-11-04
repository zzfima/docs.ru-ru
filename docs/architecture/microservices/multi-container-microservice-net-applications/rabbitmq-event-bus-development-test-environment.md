---
title: Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование RabbitMQ для реализации сообщений шины событий для событий интеграции для сред разработки или тестирования.
ms.date: 10/02/2018
ms.openlocfilehash: 7d51054d444ce1e35fabab94cc803e74dbd96f19
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089743"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="9f245-103">Реализация шины событий с помощью RabbitMQ для среды разработки или тестирования</span><span class="sxs-lookup"><span data-stu-id="9f245-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="9f245-104">Начать следует с того, что если вы создаете пользовательскую шину событий на основе RabbitMQ в контейнере, как это делается в приложении eShopOnContainers, ее следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="9f245-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="9f245-105">Ее не следует применять в рабочей среде, если только вы не разрабатываете ее в рамках служебной шины, готовой к развертыванию в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="9f245-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="9f245-106">Простая пользовательская шина событий может быть лишена многих критически важных для рабочей среды возможностей, которыми обладают коммерческие служебные шины.</span><span class="sxs-lookup"><span data-stu-id="9f245-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="9f245-107">Одна из пользовательских реализаций шины событий в eShopOnContainers по сути представляет собой библиотеку, использующую интерфейс API RabbitMQ (есть и еще одна реализация на основе служебной шины Azure).</span><span class="sxs-lookup"><span data-stu-id="9f245-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span>

<span data-ttu-id="9f245-108">Реализация шины событий с помощью RabbitMQ позволяет микрослужбам подписываться на события, публиковать и принимать их, как показано на рисунке 6–21.</span><span class="sxs-lookup"><span data-stu-id="9f245-108">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![RabbitMQ выступает в роли посредника между издателем сообщения и подписчиками и обрабатывает распространение.](./media/image22.png)

<span data-ttu-id="9f245-110">**Рис. 6–21.**</span><span class="sxs-lookup"><span data-stu-id="9f245-110">**Figure 6-21.**</span></span> <span data-ttu-id="9f245-111">Реализация шины событий на основе RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="9f245-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="9f245-112">В коде класс EventBusRabbitMQ реализует универсальный интерфейс IEventBus.</span><span class="sxs-lookup"><span data-stu-id="9f245-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="9f245-113">Для этого применяется внедрение зависимостей, что позволяет переходить от этой версии для разработки и тестирования к рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="9f245-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="9f245-114">Реализация образца шины событий для разработки и тестирования на основе RabbitMQ представляет собой стандартный код.</span><span class="sxs-lookup"><span data-stu-id="9f245-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="9f245-115">Она должна обрабатывать подключение к серверу RabbitMQ и предоставлять код для публикации события сообщения в очередях.</span><span class="sxs-lookup"><span data-stu-id="9f245-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="9f245-116">Кроме того, должен быть реализован словарь коллекций, содержащий обработчики событий интеграции для каждого типа событий. Для каждого из этих типов событий могут применяться разные способы создания экземпляра и подписки для каждой микрослужбы-получателя, как показано на рисунке 6–21.</span><span class="sxs-lookup"><span data-stu-id="9f245-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="9f245-117">Реализация простого метода публикации с помощью RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="9f245-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="9f245-118">Следующий код является ***упрощенной*** версией реализации шины событий для RabbitMQ, демонстрирующей весь сценарий.</span><span class="sxs-lookup"><span data-stu-id="9f245-118">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="9f245-119">Вам необязательно обрабатывать подключение таким образом.</span><span class="sxs-lookup"><span data-stu-id="9f245-119">You don't really handle the connection this way.</span></span> <span data-ttu-id="9f245-120">Чтобы увидеть полную реализацию, просмотрите фактический код в репозитории [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).</span><span class="sxs-lookup"><span data-stu-id="9f245-120">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span>

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

<span data-ttu-id="9f245-121">[Реальный код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) метода Publish в приложении eShopOnContainers улучшен с помощью политики повтора [Polly](https://github.com/App-vNext/Polly), которая пытается выполнить задачу повторно некоторое число раз, если контейнер RabbitMQ не готов.</span><span class="sxs-lookup"><span data-stu-id="9f245-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="9f245-122">Это может произойти, если контейнеры запускаются с помощью docker-compose. Например, контейнер RabbitMQ может запускаться медленнее других.</span><span class="sxs-lookup"><span data-stu-id="9f245-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="9f245-123">Как было сказано ранее, в RabbitMQ возможно множество конфигураций, поэтому этот код следует использовать только в средах разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="9f245-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="9f245-124">Реализация кода подписки с помощью интерфейса API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="9f245-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="9f245-125">Так же как и в случае с кодом публикации, приведенный ниже код представляет собой часть упрощенной реализации шины событий для RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="9f245-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="9f245-126">Изменять его также обычно не нужно, если его не требуется улучшить.</span><span class="sxs-lookup"><span data-stu-id="9f245-126">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="9f245-127">С каждым типом событий связан канал для получения событий из RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="9f245-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="9f245-128">Для каждого канала и типа событий может быть столько обработчиков событий, сколько требуется.</span><span class="sxs-lookup"><span data-stu-id="9f245-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="9f245-129">Метод Subscribe принимает объект IIntegrationEventHandler, который похож на метод обратного вызова в текущей микрослужбе, а также связанный с ним объект IntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="9f245-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="9f245-130">Затем добавляется обработчик событий в список обработчиков событий, которые может иметь каждый тип событий интеграции в клиентской микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="9f245-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="9f245-131">Если код клиента еще не подписался на событие, для данного типа событий создается канал, который позволяет получать события из RabbitMQ принудительным образом, когда они публикуются из любой другой службы.</span><span class="sxs-lookup"><span data-stu-id="9f245-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9f245-132">[Назад](integration-event-based-microservice-communications.md)
>[Вперед](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="9f245-132">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>
