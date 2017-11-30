---
title: "Подписка на события"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Подписка на события"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a><span data-ttu-id="cfd9b-104">Подписка на события</span><span class="sxs-lookup"><span data-stu-id="cfd9b-104">Subscribing to events</span></span>

<span data-ttu-id="cfd9b-105">Первым шагом для использования шины событий является подписаться микрослужбами события, которые они хотят получать.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="cfd9b-106">Что необходимо сделать в микрослужбами получателя.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="cfd9b-107">Следующем простом коде показано, что микрослужбу каждый получатель должен реализовывать при запуске службы (то есть в начальный класс), он подписывается на события он требуется.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the Startup class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="cfd9b-108">Например микрослужбу basket.api необходимо подписаться ProductPriceChangedIntegrationEvent сообщений.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-108">For instance, the basket.api microservice needs to subscribe to ProductPriceChangedIntegrationEvent messages.</span></span> <span data-ttu-id="cfd9b-109">Это делает микрослужбу сведения обо всех изменениях цену продукта и позволяет его предупредить пользователя об изменениях, если этого продукта в корзину пользователя.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-109">This makes the microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

<span data-ttu-id="cfd9b-110">После выполнения этого кода микрослужбу подписчика будет осуществлять прослушивание по каналам RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="cfd9b-111">По прибытии сообщения типа ProductPriceChangedIntegrationEvent код вызывает обработчик событий, который передается в него и обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="cfd9b-112">Публикация событий через шину событий</span><span class="sxs-lookup"><span data-stu-id="cfd9b-112">Publishing events through the event bus</span></span>

<span data-ttu-id="cfd9b-113">Наконец отправителя сообщения (источник микрослужбу) публикует события интеграции с код, аналогичный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="cfd9b-114">(Это упрощенном примере, который не принимает атомарность в учетную запись). Аналогичный код будет реализовывать каждый раз, когда события должны быть распространены между несколькими микрослужбами, обычно непосредственно после фиксации данных или транзакций из микрослужбу источника.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="cfd9b-115">Во-первых объект события шины реализацию (на RabbitMQ на основе или service bus) будет вставлен на конструктор контроллера, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="cfd9b-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

<span data-ttu-id="cfd9b-116">Затем она используется с помощью методов своего устройства, как метод UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="cfd9b-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

```csharp
[Route("update")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

<span data-ttu-id="cfd9b-117">Таким образом так как источник микрослужбу простой микрослужбу CRUD, этот код помещается справа в контроллер веб-API.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> <span data-ttu-id="cfd9b-118">В более сложных микрослужбами он может быть реализован в классе CommandHandler справа после фиксации исходных данных.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-118">In more advanced microservices, it could be implemented in the CommandHandler class, right after the original data is committed.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="cfd9b-119">Проектирование атомарность и гибкости при публикации на шине событий</span><span class="sxs-lookup"><span data-stu-id="cfd9b-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="cfd9b-120">При публикации события интеграции с помощью распределенным обменом сообщениями системы, например ваш шины событий и имеет проблем с единым блоком обновление исходной базы данных и публикация события.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="cfd9b-121">Для экземпляра в упрощенном примере приведенный выше код фиксирует данные в базу данных при цена продукта изменяется и затем публикует сообщение ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="cfd9b-122">Изначально может выглядеть essential атомарным образом выполнить следующие операции.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="cfd9b-123">Однако при использовании распределенных транзакций с использованием базы данных и сообщения компонента service broker, как и в старых системах, таких как [очередь сообщений (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), это не рекомендуется по соображениям, описываемого [Крепления Теорема](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="cfd9b-124">По сути микрослужбами используется для построения высокой надежности и масштабируемой системы.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="cfd9b-125">Упрощение немного, теоремы CAP говорит, то нельзя создать базу данных (или микрослужбу, которому принадлежит его модели) постоянно доступны и в полной мере согласованно *и* нечувствительного к ошибкам для любого раздела.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="cfd9b-126">Необходимо выбрать два из этих трех свойств.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="cfd9b-127">В основе микрослужбами архитектур необходимо выбрать доступности и отказоустойчивость и следует уменьшения входа строгая согласованность.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="cfd9b-128">Таким образом, в большинстве современных микрослужбу приложений на основе обычно не требуется для использования распределенных транзакций в обмене сообщениями, как и при реализации [распределенные транзакции](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) зависимости от распределенной транзакции Windows Координатор (DTC) с [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="cfd9b-129">Вернемся к начальной проблемы и его пример.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="cfd9b-130">Если служба завершает работу после обновления базы данных (в этом случае сразу после строки кода, \_контекста. SaveChangesAsync()), но прежде чем публикации события интеграции общей системы могут оказаться несогласованными.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="cfd9b-131">Это может быть критически важных, в зависимости от конкретной операцию, которую вы имеете дело с бизнес.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="cfd9b-132">Как уже упоминалось в разделе "Архитектура" может иметь несколько способов решения этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="cfd9b-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="cfd9b-133">С помощью полного [источники событий шаблон](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="cfd9b-134">С помощью [интеллектуального анализа данных журнала транзакций](http://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="cfd9b-135">С помощью [шаблон папки "Исходящие"](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="cfd9b-136">Это транзакций таблицы будут сохранены события интеграции (расширение локальных транзакций).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="cfd9b-137">Для этого сценария использование полного шаблона Event Sourcing (ES) является одним из лучших подходов, если не *лучшим*.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="cfd9b-138">Однако во многих сценариях приложений не можно реализовать полной системы ES.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="cfd9b-139">ES означает хранение только события домена в транзакционной базе данных, вместо сохранения данных текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="cfd9b-140">Сохранение только события домена может иметь значительные преимущества, такие как наличие журнал системы доступны и не сможет определить состояние системы в любой момент в прошлом.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="cfd9b-141">Однако реализации полной системы ES необходимо переработайте большая часть системы и предоставляет много осложнений и требований.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="cfd9b-142">Например, может потребоваться использовать базу данных, специально предназначенных для источники событий, таких как [хранилища событий](https://geteventstore.com/), или базы данных ориентированные на Azure Cosmos DB, MongoDB, Cassandra, CouchDB или RavenDB.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="cfd9b-143">ES — это отличный подход для этой проблемы, но не простейшим решением, если вы уже знакомы с источники событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="cfd9b-144">Возможность использования журнала транзакций, интеллектуального анализа данных первоначально выглядит очень прозрачным.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="cfd9b-145">Однако чтобы использовать этот подход, микрослужбу имеет для соединения с журнала транзакций реляционной СУБД, такие как журнал транзакций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="cfd9b-146">Это возможно, нежелательно.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-146">This is probably not desirable.</span></span> <span data-ttu-id="cfd9b-147">Другим недостатком является то, что нижнего уровня обновления записываются в журнал транзакций может быть на том же уровне, как события высокого уровня интеграции.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="cfd9b-148">В этом случае процесс реконструирования эти операции журнала транзакций могут затруднить.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="cfd9b-149">Сбалансированный подход зависит от используемых таблицу транзакций базы данных и упрощенный шаблон ES.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="cfd9b-150">Можно использовать в состояние, например «все готово для публикации события,» которого задано в оригинальном событии при фиксации в таблицу событий интеграции.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="cfd9b-151">Затем, при попытке публикации события в канале событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="cfd9b-152">Если действие публикации события завершается успешно, запустить другой транзакции в исходной службе и переместите состояние из «все готово для публикации события» «событие уже опубликован.»</span><span class="sxs-lookup"><span data-stu-id="cfd9b-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="cfd9b-153">Если действие публикации события в событии шины завершается с ошибкой, данные по-прежнему не будет согласовано в микрослужбу источника — он по-прежнему отмечен как «Готово к публикации события» и по отношению к остальным службам, его в конечном итоге будет согласованным.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="cfd9b-154">Можно всегда имеют фоновых заданий, проверка состояния транзакции или события интеграции.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="cfd9b-155">Если задание поиск события в состоянии «Готово к публикации события», можно попытаться повторно публиковать события в канале событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="cfd9b-156">Обратите внимание, что при таком подходе, сохранении только события интеграции для каждого источника микрослужбу и только события, которые вы хотите связаться с другими микрослужбами или внешними системами.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="cfd9b-157">В отличие от этого в полной системы ES, хранятся также все события домена.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="cfd9b-158">Таким образом этот сбалансированный подход — это упрощенная система ES.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="cfd9b-159">Вам требуется список события интеграции с их текущее состояние («готовность к публикации» и «публикации»).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="cfd9b-160">Однако необходимо реализовать для события интеграции этих состояний.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="cfd9b-161">И, при таком подходе вы не обязательно должны хранить все данные домена как события в транзакционной базе данных, как и в полной системы ES.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="cfd9b-162">Если вы уже используете реляционной базы данных, можно использовать таблицу транзакций, события интеграции хранилища.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="cfd9b-163">Для достижения атомарности в приложении, используется в два этапа, на основании локальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="cfd9b-164">По сути имеется таблица IntegrationEvent в той же базе данных, в которой имеется сущности домена.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="cfd9b-165">Эту таблицу работает как страховку для достижения атомарности, чтобы включить события интеграции сохраняются в те же операции, которые фиксируются данные домена.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="cfd9b-166">Шаг за шагом процесс выглядит следующим образом: приложение начинает транзакцию локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="cfd9b-167">Затем обновляет состояние домена сущностей и вставляет в таблицу событий интеграции событие.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="cfd9b-168">Наконец он фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="cfd9b-169">Вы получаете требуемой атомарность.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-169">You get the desired atomicity.</span></span>

<span data-ttu-id="cfd9b-170">При реализации процесс публикации событий, существуют следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="cfd9b-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="cfd9b-171">Опубликовать событие интеграции сразу же после фиксации транзакции и использовать другой локальной транзакции, чтобы пометить события в качестве публикуемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="cfd9b-172">Затем таблица используется только в качестве артефакта для отслеживания событий интеграции в случае проблем в удаленном микрослужбами и выполнять Компенсационный выходной действия на основе событий хранимых интеграции.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="cfd9b-173">Используйте таблицу как тип очереди.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="cfd9b-174">Отдельное приложение потока или процесса запрашивает таблицу событий интеграции, публикует события в канале событий, а затем использует локальную транзакцию для пометки события как опубликованные.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="cfd9b-175">На рисунке 8-22 показана архитектура для первого из этих подходов.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="cfd9b-176">**На рисунке 8-22**.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-176">**Figure 8-22**.</span></span> <span data-ttu-id="cfd9b-177">Атомарность при публикации события в канале событий</span><span class="sxs-lookup"><span data-stu-id="cfd9b-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="cfd9b-178">Этот подход показан на рисунке 8-22 отсутствует дополнительных рабочих микрослужбу, ответственный за проверки и подтверждения успешности интеграции опубликованного события.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="cfd9b-179">В случае сбоя этого микрослужбу дополнительные проверки рабочих можно считывать события из таблицы и повторно опубликуйте их.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="cfd9b-180">О второй подход: используйте таблицу EventLog очереди и для публикации сообщения всегда используют микрослужбу работника.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="cfd9b-181">В этом случае процесс подобное показан на рисунке 8-23.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="cfd9b-182">В следующем примере показано дополнительных микрослужбу и таблица является единственным источником при публикации события.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="cfd9b-183">**На рисунке 8-23**.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-183">**Figure 8-23**.</span></span> <span data-ttu-id="cfd9b-184">Атомарность при публикации событий в шине событий с микрослужбу работника</span><span class="sxs-lookup"><span data-stu-id="cfd9b-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="cfd9b-185">Для простоты образец eShopOnContainers используется первый подход (с без дополнительных процессов или проверки микрослужбами) плюс шины событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="cfd9b-186">Однако eShopOnContainers не обрабатывает все случаи возможных сбоев.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="cfd9b-187">В реальном приложении развернут в облаке должны поддерживать тот факт, что со временем могут возникнуть проблемы, и должны быть реализованы, проверьте и повторите отправку логику.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="cfd9b-188">С помощью таблицы в качестве очереди может быть более эффективным, чем первый подход при наличии этой таблицы как единый источник события при их публикации через шину событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="cfd9b-189">Реализация атомарность при публикации события интеграции через шину событий</span><span class="sxs-lookup"><span data-stu-id="cfd9b-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="cfd9b-190">В следующем коде показано, как можно создать одну транзакцию, включающие несколько объектов DbContext — один относящиеся к исходным данным выполняется обновление и второй контекста связано с таблицей IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="cfd9b-191">Обратите внимание, что транзакции в приведенном ниже примере кода не будет устойчивой, имея любые проблемы соединения с базой данных во время, когда выполняется код.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="cfd9b-192">Это может произойти в облачных систем, таких как база данных SQL Azure, которого может переместить базы данных между серверами.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="cfd9b-193">Реализация устойчивым транзакций разных контекстах, в разделе [реализация устойчивым соединений Entity Framework Core SQL](#implementing_resilient_EFCore_SQL_conns) данного руководства.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="cfd9b-194">Для ясности в примере показан весь процесс в одну часть кода.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="cfd9b-195">Однако реализация eShopOnContainers действительно рефакторинга и разбить на несколько классов эту логику, чтобы было проще для поддержки.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

    if (catalogItem == null) return NotFound();

    bool raiseProductPriceChangedEvent = false;

    IntegrationEvent priceChangedEvent = null;

    if (catalogItem.Price != productToUpdate.Price)
        raiseProductPriceChangedEvent = true;

    if (raiseProductPriceChangedEvent) // Create event if price has changed
    {
        var oldPrice = catalogItem.Price;
        priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
            productToUpdate.Price,
            oldPrice);
    }

    // Update current product
    catalogItem = productToUpdate;
    // Achieving atomicity between original DB and the IntegrationEventLog
    // with a local transaction

    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);

        await _catalogContext.SaveChangesAsync();

        // Save to EventLog only if product price changed
        if(raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
   }

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

<span data-ttu-id="cfd9b-196">После создания события интеграции ProductPriceChangedIntegrationEvent транзакцию, которая хранит исходную операцию домена (обновление элемента каталога) также сохраняемости события из таблицы журнала событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="cfd9b-197">В результате одной транзакции, и вы всегда сможете проверить, были ли отправлены сообщения о событиях.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="cfd9b-198">Таблица журнала событий обновляется атомарным образом с исходной операцией базы данных, с помощью локальной транзакции к той же базе данных.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="cfd9b-199">В случае неудачи любой из операций, возникает исключение и откатить транзакцию любой завершенной операции, таким образом поддержания согласованности между операций домена и отправки сообщения о событиях.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="cfd9b-200">Получение сообщений из подписки: обработчиков событий в приемник микрослужбами</span><span class="sxs-lookup"><span data-stu-id="cfd9b-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="cfd9b-201">Помимо логики подписки событий необходимо реализовать внутренний код для интеграции обработчиков событий (например, метод обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="cfd9b-202">Обработчик событий задается где получение и обработку сообщения события определенного типа.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="cfd9b-203">Обработчик событий получает экземпляр события от шины событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="cfd9b-204">Затем она выполняет поиск компонента для обработки связанных с этим событием интеграции, распространение и сохранение как изменение в состоянии микрослужбу приемника события.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="cfd9b-205">Например если событие ProductPriceChanged инициируется в микрослужбу каталога, обрабатывается в микрослужбу корзины и изменяет состояние в этот получатель корзины микрослужбу также, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

<span data-ttu-id="cfd9b-206">Обработчик событий должен проверить, существует ли продукт в любом из случаев корзины.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="cfd9b-207">Он также обновляет цену для каждого элемента корзины связанные строки.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="cfd9b-208">Наконец он создает предупреждение, выдаваемое пользователю об изменении цены, как показано на рисунке 8-24.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="cfd9b-209">**Рис. 8-24**.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-209">**Figure 8-24**.</span></span> <span data-ttu-id="cfd9b-210">Отображение изменение цены товара в корзину, как взаимодействуют с события интеграции</span><span class="sxs-lookup"><span data-stu-id="cfd9b-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="cfd9b-211">Идемпотентности в сообщения событий обновления</span><span class="sxs-lookup"><span data-stu-id="cfd9b-211">Idempotency in update message events</span></span>

<span data-ttu-id="cfd9b-212">Важным аспектом событий обновления сообщений является сбой в любой момент при обмене данными должны быть причиной сообщения для повторной попытки.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="cfd9b-213">В противном случае в фоновом режиме может попытаться опубликовать событие, которое уже опубликован, создание состояние гонки.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="cfd9b-214">Вам необходимо убедитесь в том, чтобы обновления были идемпотентными или что они предоставляют достаточно сведений, чтобы убедиться, что можно определить повторяется, отменить изменения и отправить ответ назад только один.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="cfd9b-215">Как отмечалось ранее, идемпотентности означает, что операция может выполняться несколько раз без изменения результатов.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="cfd9b-216">В среде обмена сообщениями Если в качестве при обмене данными события, события идемпотентными несколько раз может быть передан без изменения результатов для микрослужбу получателя.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="cfd9b-217">Это необходимо из-за особенностей самого события или из-за способа система обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="cfd9b-218">Сообщение идемпотентности важен в любое приложение, которое использует обмен сообщениями, а не только в приложения, которые реализуют шаблон шины событий.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="cfd9b-219">Пример операции идемпотентными — инструкция SQL, который вставляет данные в таблицу только в том случае, если эти данные еще не в таблице.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="cfd9b-220">Он не имеет значения, сколько раз запускается, вставить инструкцию SQL; результат будет таким же, таблица будет содержать эти данные.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="cfd9b-221">Также может быть идемпотентности следующим образом, необходимые при работе с сообщениями, если потенциально отправляться сообщения и поэтому обработанные более одного раза.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="cfd9b-222">Для экземпляра Если логику повторных попыток приводит отправителя для отправки точно повторяется более одного раза, необходимо убедитесь в том, что это идемпотентными.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="cfd9b-223">Существует возможность разработки идемпотентными сообщения.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="cfd9b-224">Например, можно создать событие, которое говорит» значение цена продукта \$25» вместо «добавить \$5 цену продукта.»</span><span class="sxs-lookup"><span data-stu-id="cfd9b-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="cfd9b-225">Вы может безопасно обработать первое сообщение любое число раз и результат будет таким же.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="cfd9b-226">Это не касается второе сообщение.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-226">That is not true for the second message.</span></span> <span data-ttu-id="cfd9b-227">Но даже в первом случае может не потребоваться обработать первое событие, поскольку система также мог быть отправлен более новые события изменения цен и будет перезапись новая цена.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="cfd9b-228">Другим примером может служить событие завершения заказа распространены на несколько подписчиков.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="cfd9b-229">Очень важно, что сведения о заказе обновляться в других системах, только один раз, даже при наличии события повторяющихся сообщений для одного события завершения заказа.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="cfd9b-230">Удобно иметь какой-то удостоверение каждого события, чтобы вы могли создавать логику, которая обеспечивает, что каждое событие обрабатывается только один раз на приемник.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="cfd9b-231">Определенные операции по обработке сообщений по своей природе является идемпотентной.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="cfd9b-232">Например если система создает эскизы изображений, может не важно, сколько раз сообщение о созданного эскиза обрабатывается; Результатом является создаются эскизы и они одинаковы каждый раз.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="cfd9b-233">С другой стороны операции, такие как вызов платежный шлюз взимать плату кредитной карты может оказаться идемпотентными вообще.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="cfd9b-234">В этих случаях необходимо обеспечить обработку сообщения несколько раз, предполагается, что эффект.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cfd9b-235">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="cfd9b-235">Additional resources</span></span>

-   <span data-ttu-id="cfd9b-236">**Учитывая идемпотентности сообщение** (подзаголовок на этой странице) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="cfd9b-237">Дедупликация интеграции сообщения о событиях</span><span class="sxs-lookup"><span data-stu-id="cfd9b-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="cfd9b-238">Можно гарантировать, что события сообщений, отправленных и обработано только один раз для подписчика на разных уровнях.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="cfd9b-239">Можно использовать функцию дедупликации, предлагаемых инфраструктуры обмена сообщениями, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="cfd9b-240">Другой, чтобы реализовать пользовательскую логику в вашей микрослужбу назначения.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="cfd9b-241">Наличие проверки на уровне приложения и уровне транспорта является лучшим решением.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="cfd9b-242">Дедупликация сообщение события на уровне EventHandler</span><span class="sxs-lookup"><span data-stu-id="cfd9b-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="cfd9b-243">Путем реализации определенных логики, при обработке события в обработчиках событий сообщений — один из способов обеспечить обработку события только один раз с любой приемник.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="cfd9b-244">Например, именно этот подход используется в приложении eShopOnContainers, как видно в [исходный код](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) класса OrdersController при получении команды CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="cfd9b-245">(В данном случае мы используем команду запроса HTTP не команду с помощью сообщений, но имеет аналогичную логику, необходимо внести идемпотентными команд на основе сообщений.)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="cfd9b-246">Дедупликация сообщения при использовании RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="cfd9b-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="cfd9b-247">При возникновении периодически возникающие сетевые сбои, сообщения могут повторяться и получатель сообщения должен быть готов для обработки этих повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="cfd9b-248">По возможности приемники должен обрабатывать сообщения идемпотентными способом, что лучше, чем явно обрабатывая их при дедупликации.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="cfd9b-249">Согласно [RabbitMQ документации](https://www.rabbitmq.com/reliability.html#consumer), «если сообщение доставлено получателю, а затем повторно поставлен в очередь (поскольку она не была подтверждена, перед удалением подключения потребителя, например), то RabbitMQ будет устанавливать флаг redelivered на он при попытку доставки (ли к одному клиенту или другой).</span><span class="sxs-lookup"><span data-stu-id="cfd9b-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="cfd9b-250">Если установлен флаг «redelivered», получатель должны учитывать, поскольку сообщения могут уже обработаны.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="cfd9b-251">Однако, не гарантируется; сообщение может никогда не достигнут получателя после его оставить брокер обмена сообщениями, возможно из-за сетевых проблем.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="cfd9b-252">С другой стороны Если флаг «redelivered» не задано, это гарантирует, что сообщение не было отправлено несколько раз.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="cfd9b-253">Таким образом получатель должен для нее сообщения или сообщения процесса способом идемпотентными только в том случае, если флаг «redelivered» устанавливается в сообщении.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cfd9b-254">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="cfd9b-254">Additional resources</span></span>

-   <span data-ttu-id="cfd9b-255">**Событие обмена сообщениями**
    [*http://soapatterns.org/design\_шаблонов и события\_управляемых\_обмена сообщениями*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="cfd9b-256">**Джимми Богард (Jimmy Bogard). Рефакторинг по направлению к устойчивости: Оценка взаимозависимости**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="cfd9b-257">**Публикация-подписка на канал**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-257">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="cfd9b-258">**Взаимодействие между ограниченных контекстах**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="cfd9b-259">**Итоговая согласованность**
    [*https://en.wikipedia.org/wiki/Eventual\_согласованности*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="cfd9b-260">**Филипп Brown. Стратегии для интеграции ограниченных контекстах**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="cfd9b-261">**Крис Ричардсон. Разработка транзакций Микрослужбами с использованием статистических функций, источники событий и CQRS — часть 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="cfd9b-262">**Крис Ричардсон. Использование модели событий**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-262">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="cfd9b-263">**Знакомство с источники событий**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="cfd9b-264">**База данных хранилища событий**.</span><span class="sxs-lookup"><span data-stu-id="cfd9b-264">**Event Store database**.</span></span> <span data-ttu-id="cfd9b-265">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="cfd9b-265">Official site.</span></span>
    [<span data-ttu-id="cfd9b-266">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="cfd9b-266">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="cfd9b-267">**Патрик Nommensen. Управляемые событиями управления данными для Микрослужбами**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*</span><span class="sxs-lookup"><span data-stu-id="cfd9b-267">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="cfd9b-268">**Теорема CAP**
    [*https://en.wikipedia.org/wiki/CAP\_Теорема*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-268">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="cfd9b-269">**Что такое ограничение Теорема? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-269">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="cfd9b-270">**Основные сведения о согласованности данных**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-270">**Data Consistency Primer**
[*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="cfd9b-271">**Рик Сейлинг. Теорема CAP: Почему «все разные» облако и Интернете**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-271">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="cfd9b-272">**Эрик Brewer. Ограничение Двенадцатилетнего позже: как «Правила» были изменены**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-272">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="cfd9b-273">**Участие в транзакции (DTC) внешние** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-273">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="cfd9b-274">**Шина обслуживания Azure. Обмен сообщениями через посредника: Поиск повторяющихся**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-274">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="cfd9b-275">**Руководство по надежности** (RabbitMQ документация) [ *https://www.rabbitmq.com/reliability.html\#потребителя*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-275">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="cfd9b-276">[Предыдущие] (rabbitmq-event-bus-development-test-environment.md) [Далее] (test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="cfd9b-276">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
