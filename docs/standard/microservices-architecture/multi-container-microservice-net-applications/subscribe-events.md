---
title: Подписка на события
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Подписка на события
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 5e53e0a3578c19b09f5327f444d1a5c013ad4cd9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194076"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="029cd-103">Подписка на события</span><span class="sxs-lookup"><span data-stu-id="029cd-103">Subscribing to events</span></span>

<span data-ttu-id="029cd-104">Первый шаг при использовании шины событий — подписать микрослужбы на события, которые они должны получать.</span><span class="sxs-lookup"><span data-stu-id="029cd-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="029cd-105">Это нужно сделать для микрослужб-получателей.</span><span class="sxs-lookup"><span data-stu-id="029cd-105">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="029cd-106">В следующем простом коде видно, что должна реализовать каждая микрослужба-получатель при запуске службы (то есть в классе `Startup`), чтобы подписаться на нужные события.</span><span class="sxs-lookup"><span data-stu-id="029cd-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="029cd-107">В этом случае микрослужба `basket.api` должна подписаться на сообщения `ProductPriceChangedIntegrationEvent` и `OrderStartedIntegrationEvent`.</span><span class="sxs-lookup"><span data-stu-id="029cd-107">In this case, the `basket.api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span> 

<span data-ttu-id="029cd-108">Например, при подписке на событие `ProductPriceChangedIntegrationEvent` микрослужба корзины узнает об изменении цены товара и уведомляет пользователя об этом изменении, если товар находится в корзине пользователя.</span><span class="sxs-lookup"><span data-stu-id="029cd-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent, 
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent, 
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="029cd-109">После выполнения этого кода микрослужба-подписчик будет ожидать передачи данных по каналам RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="029cd-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="029cd-110">При поступлении сообщения типа ProductPriceChangedIntegrationEvent код вызывает обработчика событий, который передается ему и обрабатывает событие.</span><span class="sxs-lookup"><span data-stu-id="029cd-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="029cd-111">Публикация событий через шину событий</span><span class="sxs-lookup"><span data-stu-id="029cd-111">Publishing events through the event bus</span></span>

<span data-ttu-id="029cd-112">Наконец, отправитель сообщения (исходная микрослужба) публикует события интеграции с кодом, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="029cd-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="029cd-113">(Это упрощенный пример, не учитывающий атомарность.) Применяйте аналогичный код в случае, когда событие необходимо распространить по нескольким микрослужбам, обычно сразу после фиксации данных или транзакций из исходной микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="029cd-113">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="029cd-114">Сначала объект реализации шины событий (на основе RabbitMQ или служебной шины) будет внедрен в конструктор контроллера, как в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="029cd-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="029cd-115">Затем вы используете его из методов контроллера, например UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="029cd-115">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="029cd-116">В этом случае, поскольку источником является простая микрослужба CRUD, этот код помещается прямо в контроллер веб-API.</span><span class="sxs-lookup"><span data-stu-id="029cd-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> 
 
<span data-ttu-id="029cd-117">В более сложных микрослужбах, например на основе подходов CQRS, это можно реализовать в классе `CommandHandler` в методе `Handle()`.</span><span class="sxs-lookup"><span data-stu-id="029cd-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span> 


### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="029cd-118">Проектирование атомарности и устойчивости при публикации в шине событий</span><span class="sxs-lookup"><span data-stu-id="029cd-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="029cd-119">При публикации событий интеграции с помощью распределенной системы обмена сообщениями, такой как шина событий, вы сталкиваетесь с проблемой атомарного обновления исходной базы данных и публикации события.</span><span class="sxs-lookup"><span data-stu-id="029cd-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="029cd-120">Например, в упрощенном примере, приведенном выше, код фиксирует данные в базе данных, когда меняется цена продукта, а затем публикует сообщение ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="029cd-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="029cd-121">Сначала может показаться важным, чтобы обе операции выполнялись атомарно.</span><span class="sxs-lookup"><span data-stu-id="029cd-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="029cd-122">Однако при использовании распределенных транзакций с базами данных и брокером сообщений, как в прежних системах, например [очередь сообщений (Майкрософт)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), это не рекомендуется по причинам, описанным в [теореме CAP](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="029cd-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="029cd-123">По сути, вы используете микрослужбы для создания масштабируемых систем с высокой доступностью.</span><span class="sxs-lookup"><span data-stu-id="029cd-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="029cd-124">В упрощенном виде теорема CAP гласит, что невозможно создать базу данных (или микрослужбу, владеющую своей моделью), которая была бы всегда доступной, строго согласованной *и* устойчивой к разделению.</span><span class="sxs-lookup"><span data-stu-id="029cd-124">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="029cd-125">Можно выбрать только два свойства из трех.</span><span class="sxs-lookup"><span data-stu-id="029cd-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="029cd-126">В архитектурах на основе микрослужб рекомендуется выбирать доступность и устойчивость в ущерб строгой согласованности.</span><span class="sxs-lookup"><span data-stu-id="029cd-126">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="029cd-127">Поэтому в большинстве современных приложений на базе микрослужб вы обычно не используете распределенные транзакции при обмене сообщениями, как вы это делаете при реализации [распределенных транзакций](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) на основе координатора распределенных транзакций Windows (DTC) с [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="029cd-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="029cd-128">Давайте вернемся к начальной проблеме и примеру.</span><span class="sxs-lookup"><span data-stu-id="029cd-128">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="029cd-129">Если служба аварийно завершает работу после обновления базы данных (в этом случае сразу после строки кода с \_context.SaveChangesAsync()), но до публикации события интеграции, вся система может утратить согласованность.</span><span class="sxs-lookup"><span data-stu-id="029cd-129">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="029cd-130">Это может быть критически важным для бизнеса в зависимости от конкретной операции.</span><span class="sxs-lookup"><span data-stu-id="029cd-130">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="029cd-131">Как уже упоминалось в разделе об архитектуре, существует несколько подходов к решению этой проблемы:</span><span class="sxs-lookup"><span data-stu-id="029cd-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="029cd-132">Использование полной модели [источников событий](https://msdn.microsoft.com/library/dn589792.aspx).</span><span class="sxs-lookup"><span data-stu-id="029cd-132">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="029cd-133">[Интеллектуальный анализ данных журнала транзакций](https://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="029cd-133">Using [transaction log mining](https://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="029cd-134">Использование [шаблона Outbox](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="029cd-134">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="029cd-135">Это таблица транзакций, в которой хранятся события интеграции (расширяющие локальную транзакцию).</span><span class="sxs-lookup"><span data-stu-id="029cd-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="029cd-136">В этом сценарии одним из лучших, если не *лучшим*, подходом будет использование полного шаблона источников событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="029cd-137">Однако часто вы не можете реализовать полную систему источников событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="029cd-138">Источник событий подразумевает хранение в базе данных о транзакциях только событий в предметной области, а не данных о текущем состоянии.</span><span class="sxs-lookup"><span data-stu-id="029cd-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="029cd-139">Хранить только события в предметной области очень удобно. Например, у вас есть история системы, и вы можете определить состояние системы в любой момент в прошлом.</span><span class="sxs-lookup"><span data-stu-id="029cd-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="029cd-140">Однако реализация полной системы источников событий требует перестройки большей части системы и приводит к другим сложностям и требованиям.</span><span class="sxs-lookup"><span data-stu-id="029cd-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="029cd-141">В частности, придется использовать базу данных, созданную специально для источников событий, например [хранилище событий](https://geteventstore.com/), или документоориентированную базу данных, например Azure Cosmos DB, MongoDB, Cassandra, CouchDB или RavenDB.</span><span class="sxs-lookup"><span data-stu-id="029cd-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="029cd-142">Модель источников событий может стать отличным решением этой проблемы, но не самым простым, особенно если вы еще не знакомы с этой концепцией.</span><span class="sxs-lookup"><span data-stu-id="029cd-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="029cd-143">Вариант с анализом журнала транзакций, на первый взгляд, выглядит понятным.</span><span class="sxs-lookup"><span data-stu-id="029cd-143">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="029cd-144">Но такой подход подразумевает соединение микрослужбы с журналом транзакций реляционной СУБД, например журналом транзакций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="029cd-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="029cd-145">Иногда это нежелательно.</span><span class="sxs-lookup"><span data-stu-id="029cd-145">This is probably not desirable.</span></span> <span data-ttu-id="029cd-146">Еще один недостаток заключается в том, что обновления низкого уровня, записанные в журнал транзакций, могут не соответствовать событиям интеграции высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="029cd-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="029cd-147">Это может затруднять реконструирование операций в журнале транзакций.</span><span class="sxs-lookup"><span data-stu-id="029cd-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="029cd-148">В качестве компромисса можно использовать комбинацию таблицы базы данных о транзакциях и упрощенного шаблона источников событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="029cd-149">Например, вы можете использовать состояние "готово к публикации события", которое вы задаете в исходном событии при его фиксации в таблице событий интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-149">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="029cd-150">Затем вы пытаетесь опубликовать событие в шине события.</span><span class="sxs-lookup"><span data-stu-id="029cd-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="029cd-151">Если действие публикации события выполняется успешно, вы запускаете еще одну транзакцию в исходной службе и изменяете состояние с "готово к публикации события" на "событие опубликовано".</span><span class="sxs-lookup"><span data-stu-id="029cd-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="029cd-152">Если действие публикации события в шине событий не выполняется, данные не утратят согласованность в исходной микрослужбе — они останутся в состоянии "готово к публикации события", и это будет согласовываться с остальными службами.</span><span class="sxs-lookup"><span data-stu-id="029cd-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="029cd-153">Вы всегда можете запустить фоновые задания для проверки состояния транзакций или событий интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="029cd-154">Когда задание находит событие в состоянии "готово к публикации события", оно пытается повторно опубликовать событие в шине событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-154">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="029cd-155">При таком подходе вы сохраняете только события интеграции для каждой исходной микрослужбы и только события, которые вы хотите передать другим микрослужбам или внешним системам.</span><span class="sxs-lookup"><span data-stu-id="029cd-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="029cd-156">В отличие от полной системы источников событий, когда вы также храните все события в предметной области.</span><span class="sxs-lookup"><span data-stu-id="029cd-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="029cd-157">Такой сбалансированный подход — это упрощенная система источников событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="029cd-158">Вам нужен список событий интеграции с их текущим состоянием ("готово к публикации" или "опубликовано").</span><span class="sxs-lookup"><span data-stu-id="029cd-158">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="029cd-159">Но эти состояния нужно применять только к событиям интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="029cd-160">При таком подходе вам не нужно хранить все данные предметной области в виде событий в базе данных о транзакциях, как в полной системе источников событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="029cd-161">Если вы уже используете реляционную базу данных, можете хранить события интеграции в таблице транзакций.</span><span class="sxs-lookup"><span data-stu-id="029cd-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="029cd-162">Чтобы приложение было атомарным, используйте двухэтапный процесс на основе локальных транзакций.</span><span class="sxs-lookup"><span data-stu-id="029cd-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="029cd-163">Фактически, таблица IntegrationEvent хранится в той же базе денных, что и сущности предметной области.</span><span class="sxs-lookup"><span data-stu-id="029cd-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="029cd-164">Эта таблица используется для гарантии атомарности, чтобы вы включали хранимые события интеграции в те же транзакции, которые фиксируются в данных предметной области.</span><span class="sxs-lookup"><span data-stu-id="029cd-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="029cd-165">Процесс выполняется следующим образом. Приложение запускает транзакцию в локальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="029cd-165">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="029cd-166">Затем оно обновляет состояние сущностей предметной области и вставляет событие в таблицу событий интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-166">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="029cd-167">Наконец, оно фиксирует транзакцию.</span><span class="sxs-lookup"><span data-stu-id="029cd-167">Finally, it commits the transaction.</span></span> <span data-ttu-id="029cd-168">Вы получаете необходимую атомарность.</span><span class="sxs-lookup"><span data-stu-id="029cd-168">You get the desired atomicity.</span></span>

<span data-ttu-id="029cd-169">Для выполнения этапов публикации события у вас есть следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="029cd-169">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="029cd-170">Опубликуйте событие интеграции сразу после фиксации транзакции и используйте другую локальную транзакцию, чтобы отметить события в таблице как опубликованные.</span><span class="sxs-lookup"><span data-stu-id="029cd-170">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="029cd-171">Затем используйте таблицу просто как объект для отслеживания событий интеграции в случае проблем в удаленных микрослужбах и выполняйте необходимые действия, основываясь на хранящихся событиях интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-171">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="029cd-172">Используйте таблицу как очередь.</span><span class="sxs-lookup"><span data-stu-id="029cd-172">Use the table as a kind of queue.</span></span> <span data-ttu-id="029cd-173">Отдельный поток или процесс приложения обращается к таблице событий интеграции, публикует события в шине событий, а затем выполняет местную транзакцию, чтобы отметить события как опубликованные.</span><span class="sxs-lookup"><span data-stu-id="029cd-173">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="029cd-174">На рисунке 8-22 показана архитектура для первого из этих подходов.</span><span class="sxs-lookup"><span data-stu-id="029cd-174">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="029cd-175">**Рис. 8-22**.</span><span class="sxs-lookup"><span data-stu-id="029cd-175">**Figure 8-22**.</span></span> <span data-ttu-id="029cd-176">Атомарность при публикации события в шине событий</span><span class="sxs-lookup"><span data-stu-id="029cd-176">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="029cd-177">В подходе, проиллюстрированном на рисунке 8-22, отсутствует дополнительная рабочая микрослужба, которая проверяет и подтверждает успешную публикацию событий интеграции.</span><span class="sxs-lookup"><span data-stu-id="029cd-177">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="029cd-178">В случае сбоя эта дополнительная проверяющая микрослужба может считать события из таблицы и опубликовать их повторно.</span><span class="sxs-lookup"><span data-stu-id="029cd-178">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="029cd-179">При втором подходе вы используете таблицу EventLog в качестве очереди и всегда применяете рабочую микрослужбу для публикации сообщений.</span><span class="sxs-lookup"><span data-stu-id="029cd-179">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="029cd-180">Подобный процесс показан на рисунке 8-23.</span><span class="sxs-lookup"><span data-stu-id="029cd-180">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="029cd-181">Здесь изображена дополнительная микрослужба, и таблица является единственным источником при публикации событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-181">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="029cd-182">**Рис. 8-23**.</span><span class="sxs-lookup"><span data-stu-id="029cd-182">**Figure 8-23**.</span></span> <span data-ttu-id="029cd-183">Атомарность при публикации события в шине событий с рабочей микрослужбой</span><span class="sxs-lookup"><span data-stu-id="029cd-183">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="029cd-184">Для простоты в примере приложения eShopOnContainers используется первый подход (без дополнительных процессов или проверяющих микрослужб) и шина событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-184">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="029cd-185">Однако eShopOnContainers не обрабатывает все возможные случаи сбоев.</span><span class="sxs-lookup"><span data-stu-id="029cd-185">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="029cd-186">В реальном приложении, развернутом в облаке, вы должны учитывать факт неизбежности сбоев и реализовывать эту логику проверки и повторной отправки.</span><span class="sxs-lookup"><span data-stu-id="029cd-186">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="029cd-187">Таблица в качестве очереди эффективнее первого подхода, если эта таблица является единственным источником событий при их публикации через шину событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-187">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="029cd-188">Реализация атомарности при публикации события интеграции через шину событий</span><span class="sxs-lookup"><span data-stu-id="029cd-188">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="029cd-189">В следующем коде показано, как можно создать одну транзакцию с несколькими объектами DbContext — один контекст связан с исходными обновляемыми данными, а второй — с таблицей IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="029cd-189">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="029cd-190">Обратите внимание, что транзакция в приведенном ниже примере кода не будет устойчивой, если при выполнении кода возникнут проблемы с подключением к базе данных.</span><span class="sxs-lookup"><span data-stu-id="029cd-190">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="029cd-191">Это может произойти в облачных системах, таких как база данных SQL Azure, которые могут перемещать базы данных между серверами.</span><span class="sxs-lookup"><span data-stu-id="029cd-191">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="029cd-192">Реализация устойчивых транзакций в нескольких контекстах описана в разделе [Реализация устойчивых SQL-соединений с платформой Entity Framework Core](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md).</span><span class="sxs-lookup"><span data-stu-id="029cd-192">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="029cd-193">Чтобы было понятнее, в следующем примере показан весь процесс в одном фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="029cd-193">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="029cd-194">Но в приложении eShopOnContainers для простоты выполнен рефакторинг и разделение этой логики на несколько классов.</span><span class="sxs-lookup"><span data-stu-id="029cd-194">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate) 
{
  var catalogItem = 
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id == 
                                                               productToUpdate.Id); 
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

  // Just save the updated product if the Product's Price hasn't changed.
  if (!raiseProductPriceChangedEvent) 
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
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

      // Publish the intergation event through the event bus
      _eventBus.Publish(priceChangedEvent); 

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent); 
  }

  return Ok();
}

```

<span data-ttu-id="029cd-195">После создания события интеграции ProductPriceChangedIntegrationEvent транзакция, хранящая операцию в исходной предметной области (обновление позиции каталога), также включает сохранение события в таблице EventLog.</span><span class="sxs-lookup"><span data-stu-id="029cd-195">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="029cd-196">В результате получается одна транзакция, и вы всегда можете проверить, были ли отправлены сообщения о событии.</span><span class="sxs-lookup"><span data-stu-id="029cd-196">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="029cd-197">Таблица журнала событий обновляется атомарно операцией исходной базы данных с помощью локальной транзакции в этой же базе данных.</span><span class="sxs-lookup"><span data-stu-id="029cd-197">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="029cd-198">Если происходит сбой операции, выдается исключение, и транзакция откатывает выполненную операцию, поддерживая согласованность между операциями предметной области и отправленными сообщениями о событии.</span><span class="sxs-lookup"><span data-stu-id="029cd-198">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="029cd-199">Получение сообщений из подписок: обработчики событий в микрослужбах-получателях</span><span class="sxs-lookup"><span data-stu-id="029cd-199">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="029cd-200">Помимо логики подписки на события вам необходимо реализовать внутренний код для обработчиков событий интеграции (например, метод обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="029cd-200">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="029cd-201">В обработчике событий вы указываете, где будут получаться и обрабатываться сообщения о событиях определенного типа.</span><span class="sxs-lookup"><span data-stu-id="029cd-201">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="029cd-202">Сначала обработчик событий получает экземпляр события от шины событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-202">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="029cd-203">Затем он выполняет поиск компонента, нуждающегося в обработке и связанного с этим событием интеграции, распространяя и сохраняя событие как изменение состояния в микрослужбе-получателе.</span><span class="sxs-lookup"><span data-stu-id="029cd-203">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="029cd-204">Например если событие ProductPriceChanged инициируется в микрослужбе каталога, оно обрабатывается в микрослужбе корзины и изменяет состояние в этой микрослужбе-получателе, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="029cd-204">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="029cd-205">Обработчик событий должен проверить, существует ли товар в экземплярах корзины.</span><span class="sxs-lookup"><span data-stu-id="029cd-205">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="029cd-206">Он также обновляет цену товара в каждой соответствующей позиции строки корзины.</span><span class="sxs-lookup"><span data-stu-id="029cd-206">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="029cd-207">Наконец, он создает для пользователя предупреждение об изменении цены, как показано на рисунке 8-24.</span><span class="sxs-lookup"><span data-stu-id="029cd-207">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="029cd-208">**Рис. 8-24**.</span><span class="sxs-lookup"><span data-stu-id="029cd-208">**Figure 8-24**.</span></span> <span data-ttu-id="029cd-209">Отображение изменения цены товара в корзине на основе данных о событиях интеграции</span><span class="sxs-lookup"><span data-stu-id="029cd-209">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="029cd-210">Идемпотентность в событиях сообщения об обновлении</span><span class="sxs-lookup"><span data-stu-id="029cd-210">Idempotency in update message events</span></span>

<span data-ttu-id="029cd-211">Важный аспект событий сообщения об обновлении заключается в том, что при сбое взаимодействия сообщение должно отправляться повторно.</span><span class="sxs-lookup"><span data-stu-id="029cd-211">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="029cd-212">В противном случае фоновая задача попытается опубликовать уже опубликованное событие, создавая состояние гонки.</span><span class="sxs-lookup"><span data-stu-id="029cd-212">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="029cd-213">Убедитесь, что обновления либо являются идемпотентными, любо предоставляют достаточно информации, чтобы вы могли найти дублирующие данные, отменить их и отправить обратно только один ответ.</span><span class="sxs-lookup"><span data-stu-id="029cd-213">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="029cd-214">Как отмечалось ранее, идемпотентность означает, что операция может выполняться несколько раз без изменения результатов.</span><span class="sxs-lookup"><span data-stu-id="029cd-214">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="029cd-215">В среде обмена сообщениями, например при передаче событий, событие является идемпотентным, если его можно доставить несколько раз без изменения результатов для микрослужбы-получателя.</span><span class="sxs-lookup"><span data-stu-id="029cd-215">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="029cd-216">Это необходимо из-за особенностей самого события или из-за способа обработки событий в системе.</span><span class="sxs-lookup"><span data-stu-id="029cd-216">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="029cd-217">Идемпотентность сообщений важна в любом приложении, где используется обмен сообщениями, а не только в приложениях с шаблоном шины событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-217">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="029cd-218">Пример идемпотентной операции — инструкция SQL, которая вставляет данные в таблицу только в том случае, если этих данных еще нет в таблице.</span><span class="sxs-lookup"><span data-stu-id="029cd-218">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="029cd-219">Сколько бы раз вы ни выполняли эту инструкцию SQL по вставке, результат не изменится — таблица будет содержать эти данные.</span><span class="sxs-lookup"><span data-stu-id="029cd-219">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="029cd-220">Такая идемпотентность также может быть необходима при работе с сообщениями, если сообщения могут быть отправлены и, следовательно, обработаны несколько раз.</span><span class="sxs-lookup"><span data-stu-id="029cd-220">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="029cd-221">Например, если по логике повтора отправитель несколько раз посылает одно и то же сообщение, необходимо обеспечить идемпотентность.</span><span class="sxs-lookup"><span data-stu-id="029cd-221">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="029cd-222">Вы можете создать идемпотентные сообщения.</span><span class="sxs-lookup"><span data-stu-id="029cd-222">It is possible to design idempotent messages.</span></span> <span data-ttu-id="029cd-223">Например, можно создать событие, которое предписывает "установить цену товара \$25" вместо "увеличить цену товара на \$5".</span><span class="sxs-lookup"><span data-stu-id="029cd-223">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="029cd-224">Первое сообщение можно безопасно обрабатывать сколько угодно раз, результат не изменится.</span><span class="sxs-lookup"><span data-stu-id="029cd-224">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="029cd-225">Со вторым сообщением будет иначе.</span><span class="sxs-lookup"><span data-stu-id="029cd-225">That is not true for the second message.</span></span> <span data-ttu-id="029cd-226">Но даже в первом случае можно отказаться от обработки первого события, поскольку система уже могла послать обновленное событие изменения цены, и тогда будет изменена уже новая цена.</span><span class="sxs-lookup"><span data-stu-id="029cd-226">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="029cd-227">Еще один пример — событие выполнения заказа, распространяемое нескольким подписчикам.</span><span class="sxs-lookup"><span data-stu-id="029cd-227">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="029cd-228">Важно обновлять сведения о заказах в других системах однократно, даже если существуют дублирующие события сообщений для одного события выполнения заказа.</span><span class="sxs-lookup"><span data-stu-id="029cd-228">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="029cd-229">У события должен быть какой-то идентификатор, чтобы вы могли создать логику, по которой каждое событие обрабатывается получателем только один раз.</span><span class="sxs-lookup"><span data-stu-id="029cd-229">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="029cd-230">Иногда обработка сообщений является идемпотентной сама по себе.</span><span class="sxs-lookup"><span data-stu-id="029cd-230">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="029cd-231">Например, если система создает эскизы изображений, неважно, сколько раз будет обработано сообщение о созданном эскизе, результат неизменен — эскизы созданы.</span><span class="sxs-lookup"><span data-stu-id="029cd-231">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="029cd-232">С другой стороны, такие операции, как вызов шлюза оплаты для списания средств с кредитной карты, могут быть совсем не идемпотентными.</span><span class="sxs-lookup"><span data-stu-id="029cd-232">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="029cd-233">В этих случаях необходимо гарантировать, что обработка сообщения несколько раз приведет к ожидаемым результатам.</span><span class="sxs-lookup"><span data-stu-id="029cd-233">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="029cd-234">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="029cd-234">Additional resources</span></span>

-   <span data-ttu-id="029cd-235">**Соблюдение идемпотентности сообщений** (подраздел на этой странице) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="029cd-235">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="029cd-236">Дедупликация сообщений о событиях интеграции</span><span class="sxs-lookup"><span data-stu-id="029cd-236">Deduplicating integration event messages</span></span>

<span data-ttu-id="029cd-237">Вы можете гарантировать, что события сообщения будут отправлены или обработаны только один раз для подписчика, на разных уровнях.</span><span class="sxs-lookup"><span data-stu-id="029cd-237">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="029cd-238">Например, можно использовать функцию дедупликации в вашей инфраструктуре обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="029cd-238">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="029cd-239">Или можно применить пользовательскую логику в микрослужбе назначения.</span><span class="sxs-lookup"><span data-stu-id="029cd-239">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="029cd-240">Лучший вариант — проверки и на уровне транспортировки, и на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="029cd-240">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="029cd-241">Дедупликация событий сообщения на уровне EventHandler</span><span class="sxs-lookup"><span data-stu-id="029cd-241">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="029cd-242">Один из способов убедиться, что событие будет обработано получателями только один раз, — применить определенную логику при обработке событий сообщения в обработчиках событий.</span><span class="sxs-lookup"><span data-stu-id="029cd-242">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="029cd-243">Например, такой подход используется в приложении eShopOnContainers, как видно в [исходном коде](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) класса OrdersController, который получает команду CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="029cd-243">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="029cd-244">(В данном случае мы используем команду HTTP-запроса, а не команду на основе сообщений, но для обеспечения идемпотентности команды сообщения используется аналогичная логика.)</span><span class="sxs-lookup"><span data-stu-id="029cd-244">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="029cd-245">Дедупликация сообщений при использовании RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="029cd-245">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="029cd-246">В случае периодических сбоев в сети сообщения могут дублироваться, и получатель сообщений должен быть готов к обработке повторяющихся сообщений.</span><span class="sxs-lookup"><span data-stu-id="029cd-246">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="029cd-247">По возможности получатели должны обрабатывать сообщения идемпотентно. Это лучше, чем явная обработка с дедупликацией.</span><span class="sxs-lookup"><span data-stu-id="029cd-247">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="029cd-248">Согласно [документации RabbitMQ](https://www.rabbitmq.com/reliability.html#consumer), если сообщение доставлено получателю, а затем повторно поставлено в очередь (например, оно не было подтверждено до разрыва соединения с получателем), RabbitMQ пометит его как доставляемое повторно, когда оно снова будет доставляться (этому же получателю или другому).</span><span class="sxs-lookup"><span data-stu-id="029cd-248">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="029cd-249">Если сообщение имеет метку "доставляется повторно", получатель должен учитывать это, поскольку он мог уже обработать это сообщение.</span><span class="sxs-lookup"><span data-stu-id="029cd-249">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="029cd-250">Но это необязательно. Сообщение могло так и не дойти до получателя после отправки из брокера сообщений, например из-за проблем в сети.</span><span class="sxs-lookup"><span data-stu-id="029cd-250">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="029cd-251">С другой стороны, если нет метки "доставляется повторно", сообщение гарантированно было отправлено только один раз.</span><span class="sxs-lookup"><span data-stu-id="029cd-251">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="029cd-252">Таким образом, получатель должен дедуплицировать или обрабатывать сообщения идемпотентно только в том случае, если они имеют метку "доставляется повторно".</span><span class="sxs-lookup"><span data-stu-id="029cd-252">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="029cd-253">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="029cd-253">Additional resources</span></span>

-   <span data-ttu-id="029cd-254">**Ветвление eShopOnContainers с использованием NServiceBus (Particular Software)**
    [*https://go.particular.net/eShopOnContainers*](https://go.particular.net/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="029cd-254">**Forked eShopOnContainers using NServiceBus (Particular Software)**
[*https://go.particular.net/eShopOnContainers*](https://go.particular.net/eShopOnContainers)</span></span>

-   <span data-ttu-id="029cd-255">**Обмен сообщениями на основе событий**
    [*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="029cd-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="029cd-256">**Джимми Богард (Jimmy Bogard). Рефакторинг для обеспечения отказоустойчивости: оценка взаимозависимости**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="029cd-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="029cd-257">**Канал публикации и подписки**
    [*https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="029cd-257">**Publish-Subscribe channel**
[*https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="029cd-258">**Взаимодействие между ограниченными контекстами**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="029cd-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="029cd-259">**Итоговая согласованность**
    [*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="029cd-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="029cd-260">**Филип Браун (Philip Brown). Стратегии интеграции ограниченных контекстов**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="029cd-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="029cd-261">**Крис Ричардсон (Chris Richardson). Разработка транзакционных микрослужб с помощью агрегатов, порождения событий и CQRS. Часть 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="029cd-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="029cd-262">**Крис Ричардсон (Chris Richardson). Шаблон порождения событий**
    [*https://microservices.io/patterns/data/event-sourcing.html*](https://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="029cd-262">**Chris Richardson. Event Sourcing pattern**
[*https://microservices.io/patterns/data/event-sourcing.html*](https://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="029cd-263">**Знакомство с порождением событий**
    [*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="029cd-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="029cd-264">**База данных хранилища событий**.</span><span class="sxs-lookup"><span data-stu-id="029cd-264">**Event Store database**.</span></span> <span data-ttu-id="029cd-265">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="029cd-265">Official site.</span></span>
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   <span data-ttu-id="029cd-266">**Патрик Номменсен (Patrick Nommensen). Управление данными на основе событий для микрослужб**
    \*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> \*</span><span class="sxs-lookup"><span data-stu-id="029cd-266">**Patrick Nommensen. Event-Driven Data Management for Microservices**
\*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> \*</span></span>

-   <span data-ttu-id="029cd-267">**Теорема CAP**
    [*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="029cd-267">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="029cd-268">**Что такое теорема CAP?**
    [*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="029cd-268">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="029cd-269">**Основные сведения о согласованности данных**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="029cd-269">**Data Consistency Primer**
[*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="029cd-270">**Рик Сейлинг (Rick Saling). Теорема CAP: почему в случае с облачными средами и Интернетом все иначе**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="029cd-270">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="029cd-271">**Эрик Брюер (Eric Brewer). Теорема CAP двенадцать лет спустя: как поменялись правила**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="029cd-271">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="029cd-272">**Участие во внешних транзакциях (DTC)** (MSMQ) [*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="029cd-272">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="029cd-273">**Служебная шина Azure. Обмен сообщениями через брокер: поиск повторяющихся данных**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="029cd-273">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="029cd-274">**Руководство по обеспечению надежности** (документация RabbitMQ) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="029cd-274">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="029cd-275">[Назад](rabbitmq-event-bus-development-test-environment.md)
[Вперед](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="029cd-275">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
