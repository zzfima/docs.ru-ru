---
title: "Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d60a4590682b79a9f8ac57afee09884b7edd1f98
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="0ad3b-104">Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService</span><span class="sxs-lookup"><span data-stu-id="0ad3b-104">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="0ad3b-105">Рано или поздно вам может потребоваться реализовать фоновые задачи и запланированные задания в приложении на основе микрослужб или приложении любого другого типа.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-105">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="0ad3b-106">Разница при использовании архитектуры микрослужб в том, что вы можете реализовать отдельный процесс или контейнер для размещения таких фоновых задач, чтобы затем масштабировать его по мере необходимости, или даже обеспечить выполнение единственного экземпляра этого процесса или контейнера микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-106">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="0ad3b-107">Если посмотреть шире, в .NET Core такие задачи называются размещенными службами, так как они представляют собой службы или логику, размещаемые в узле, приложении или микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-107">From a generic point of view, in .NET Core we called these type of tasks Hosted Services, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="0ad3b-108">Обратите внимание на то, что в этом случае под размещенной службой понимается просто класс с логикой фоновой задачи.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-108">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="0ad3b-109">Начиная с версии .NET Core 2.0, платформа предоставляет новый интерфейс <xref:Microsoft.Extensions.Hosting.IHostedService>, который позволяет легко реализовывать размещенные службы.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-109">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="0ad3b-110">Главная идея заключается в том, что вы можете регистрировать несколько фоновых задач (размещенных служб), которые выполняются в фоновом режиме в процессе работы веб-узла или обычного узла, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-110">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image below.</span></span>

![](./media/image26.png)

<span data-ttu-id="0ad3b-111">**Рис. 8-25**.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-111">**Figure 8-25.**</span></span> <span data-ttu-id="0ad3b-112">Использование интерфейса IHostedService в классах WebHost и Host</span><span class="sxs-lookup"><span data-stu-id="0ad3b-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="0ad3b-113">Обратите внимание на различие между `WebHost` и `Host`.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-113">Note the difference made between `WebHost` and `Host`.</span></span> <span data-ttu-id="0ad3b-114">`WebHost` (базовый класс, реализующий интерфейс `IWebHost`) в ASP.NET Core 2.0 — это артефакт инфраструктуры, с помощью которого процесс получает доступ к возможностям сервера HTTP, например при реализации веб-приложения MVC или службы веб-интерфейса API.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-114">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="0ad3b-115">Он предоставляет все новые преимущества инфраструктуры в ASP.NET Core, позволяя использовать внедрение зависимостей, вставлять промежуточные слои в конвейер HTTP и, в частности, применять `IHostedServices` для фоновых задач.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-115">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the HTTP pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="0ad3b-116">`Host` (базовый класс, реализующий интерфейс `IHost`) — это новшество в .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-116">A `Host` (base class implementing `IHost`), however, is something new in .NET Core 2.1.</span></span> <span data-ttu-id="0ad3b-117">По существу, класс `Host` обеспечивает практически такую же инфраструктуру, что и класс `WebHost` (внедрение зависимостей, размещенные службы и т. д.), но в этом случае узел должен представлять собой более простой процесс без связанных с MVC веб-интерфейсами API или сервером HTTP возможностей.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-117">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="0ad3b-118">Таким образом, вы можете либо создать специальный процесс узла с помощью интерфейса IHost для реализации только размещенных служб, например микрослужбу, предназначенную специально для размещения `IHostedServices`, либо вы можете расширить существующий класс `WebHost` в ASP.NET Core, например существующий веб-интерфейс API ASP.NET Core или приложение MVC.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-118">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatevely extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span> 

<span data-ttu-id="0ad3b-119">Каждый подход имеет свои преимущества и недостатки в зависимости от потребностей бизнеса и требований к масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-119">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="0ad3b-120">Основной принцип заключается в том, что если фоновые задачи не связаны с HTTP (IWebHost), в .NET Core 2.1 следует использовать интерфейс IHost, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-120">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use and IHost, when available in .NET Core 2.1.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="0ad3b-121">Регистрация размещенных служб в WebHost или Host</span><span class="sxs-lookup"><span data-stu-id="0ad3b-121">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="0ad3b-122">Давайте более подробно разберем интерфейс `IHostedService`, так как его использование в классах `WebHost` и `Host` во многом схоже.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-122">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span> 

<span data-ttu-id="0ad3b-123">Библиотека SignalR — один из примеров артефактов, использующих размещенные службы, однако ее можно применять и для более простых задач, таких как следующие:</span><span class="sxs-lookup"><span data-stu-id="0ad3b-123">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

-   <span data-ttu-id="0ad3b-124">фоновая задача опроса базы данных для поиска изменений;</span><span class="sxs-lookup"><span data-stu-id="0ad3b-124">A background task polling a database looking for changes.</span></span>
-   <span data-ttu-id="0ad3b-125">запланированная задача для периодического обновления кэша;</span><span class="sxs-lookup"><span data-stu-id="0ad3b-125">A scheduled task updating some cache periodically.</span></span>
-   <span data-ttu-id="0ad3b-126">реализация QueueBackgroundWorkItem, которая позволяет задаче выполняться в фоновом потоке;</span><span class="sxs-lookup"><span data-stu-id="0ad3b-126">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
-   <span data-ttu-id="0ad3b-127">обработка сообщений из очереди сообщений веб-приложения в фоновом режиме при использовании общих служб, таких как `ILogger`;</span><span class="sxs-lookup"><span data-stu-id="0ad3b-127">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
-   <span data-ttu-id="0ad3b-128">фоновая задача, запускаемая с помощью `Task.Run()`.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-128">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="0ad3b-129">Выполнение любого из этих действий можно перенести в фоновую задачу на основе IHostedService.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-129">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="0ad3b-130">Для добавления одного или нескольких экземпляров `IHostedServices` в `WebHost` или `Host` их следует зарегистрировать посредством стандартного внедрения зависимостей в классе ASP.NET Core `WebHost` (или в классе `Host` в .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="0ad3b-130">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1).</span></span> <span data-ttu-id="0ad3b-131">Фактически размещенные службы регистрируются в известном методе `ConfigureServices()` класса `Startup`, как в следующем коде типичного класса ASP.NET WebHost:</span><span class="sxs-lookup"><span data-stu-id="0ad3b-131">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span> 

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{            
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="0ad3b-132">В этом коде размещенная служба `GracePeriodManagerService` представляет собой реальный код микрослужбы размещения заказов в приложении eShopOnContainers, а другие две службы — это просто дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-132">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="0ad3b-133">Выполнение фоновой задачи `IHostedService` согласуется с временем существования приложения (узла или микрослужбы).</span><span class="sxs-lookup"><span data-stu-id="0ad3b-133">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="0ad3b-134">Задачи регистрируются при запуске приложения, а при завершении его работы есть возможность произвести надлежащую обработку или очистку.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-134">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="0ad3b-135">Фоновый поток можно запускать для выполнения любой задачи и без использования `IHostedService`.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-135">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="0ad3b-136">Различие именно в том, что будет происходить при завершении работы приложения: поток будет просто завершаться без возможности надлежащей очистки.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-136">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>


## <a name="the-ihostedservice-interface"></a><span data-ttu-id="0ad3b-137">Интерфейс IHostedService</span><span class="sxs-lookup"><span data-stu-id="0ad3b-137">The IHostedService interface</span></span>

<span data-ttu-id="0ad3b-138">При регистрации интерфейса `IHostedService` платформа .NET Core вызывает методы `StartAsync()` и `StopAsync()` типа `IHostedService` во время запуска и остановки приложения соответственно.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-138">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="0ad3b-139">В частности, метод запуска вызывается после запуска сервера и активации `IApplicationLifetime.ApplicationStarted`.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-139">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="0ad3b-140">Определение интерфейса `IHostedService` в .NET Core выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-140">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```
<span data-ttu-id="0ad3b-141">Как было показано ранее, вы можете создать несколько реализаций IHostedService и зарегистрировать их в методе `ConfigureService()` в контейнере внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-141">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="0ad3b-142">Все эти размещенные службы будут запускаться и останавливаться вместе с приложением или микрослужбой.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-142">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="0ad3b-143">Разработчик отвечает за обработку завершения действия или работы служб при вызове метода `StopAsync()` узлом.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-143">As a developer, you are responsible for handling the stopping action or your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="0ad3b-144">Реализация IHostedService с помощью пользовательского класса размещенной службы, производного от базового класса BackgroundService</span><span class="sxs-lookup"><span data-stu-id="0ad3b-144">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="0ad3b-145">Можно пойти дальше и создать пользовательский класс размещенной службы с нуля, реализовав интерфейс `IHostedService`, как это требуется делать в .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-145">You could go ahead and create you custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span> 

<span data-ttu-id="0ad3b-146">Однако поскольку большинство фоновых задач имеют одинаковые потребности в отношении управления токенами отмены и других типичных операций, в .NET Core 2.1 будет доступен очень удобный абстрактный базовый класс BackgroundService, от которого можно будет производить наследование.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-146">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other tipical operations, .NET Core 2.1 will be providing a very convenient abstract base class you can derive from, named BackgroundService.</span></span>

<span data-ttu-id="0ad3b-147">Он будет выполнять основную часть работы, связанной с настройкой фоновой задачи.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-147">That class provides the main work needed to set up the background task.</span></span> <span data-ttu-id="0ad3b-148">Имейте в виду, что этот класс будет входить в состав библиотеки .NET Core 2.1, поэтому писать его не нужно.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-148">Note that this class will come in the .NET Core 2.1 library so you don’t need to write it.</span></span>

<span data-ttu-id="0ad3b-149">Однако на момент написания этой статьи платформа .NET Core 2.1 еще не была выпущена.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-149">However, as of the time of this writing, .NET Core 2.1 has not been released.</span></span> <span data-ttu-id="0ad3b-150">Поэтому в приложение eShopOnContainers, которое в настоящее время использует .NET Core 2.0, этот класс временно включен из репозитория .NET Core 2.1 с открытым кодом (требуется только лицензия на открытый код), так как он совместим с текущим интерфейсом IHostedService в .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-150">Therefore, in eShopOnContainers which is currently using .NET Core 2.0, we are just temporally incorporating that class from the .NET Core 2.1 open-source repo (no need of any proprietary license other than the open-source license) because it is compatible with the current IHostedService interface in .NET Core 2.0.</span></span> <span data-ttu-id="0ad3b-151">Когда платформа .NET Core 2.1 будет выпущена, нужно будет лишь указать соответствующий пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-151">When .NET Core 2.1 is released, you’ll just need to point to the right NuGet package.</span></span>

<span data-ttu-id="0ad3b-152">Следующий код — это абстрактный базовый класс BackgroundService, реализованный в .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="0ad3b-152">The next code is the abstract BackgroundService base class as implemented in .NET Core 2.1.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0. 
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts = 
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it, 
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }
    
    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="0ad3b-153">Благодаря такой унаследованной реализации при создании собственного класса размещенной службы, производного от приведенного выше абстрактного базового класса, необходимо просто реализовать в нем метод `ExecuteAsync()`. Пример представлен в следующем упрощенном коде из приложения eShopOnContainers, который опрашивает базу данных и при необходимости публикует события интеграции в шине событий.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-153">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{        
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
        {
            //Constructor’s parameters validations...       
        }

        protected override async Task ExecuteAsync(CancellationToken stoppingToken)
        {
            _logger.LogDebug($"GracePeriodManagerService is starting.");

            stoppingToken.Register(() => 
                    _logger.LogDebug($" GracePeriod background task is stopping."));

            while (!stoppingToken.IsCancellationRequested)
            {
                _logger.LogDebug($"GracePeriod task doing background work.");

                // This eShopOnContainers method is quering a database table 
                // and publishing events into the Event Bus (RabbitMS / ServiceBus)
                CheckConfirmedGracePeriodOrders();

                await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
            }
            
            _logger.LogDebug($"GracePeriod background task is stopping.");

        }

        protected override async Task StopAsync (CancellationToken stoppingToken)
        {
               // Run your graceful clean-up actions
        }
}
```

<span data-ttu-id="0ad3b-154">В этом конкретном случае выполняется метод приложения eShopOnContainers, который выполняет запрос к таблице базы данных для поиска заказов с определенным состоянием, а при применении изменений события интеграции публикуются через шину событий (она может быть основана на RabbitMQ или служебной шине Azure).</span><span class="sxs-lookup"><span data-stu-id="0ad3b-154">In this specific case for eShopOnContainers, it is executing an application method which is quering a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span> 

<span data-ttu-id="0ad3b-155">Естественно, вместо этого можно выполнять любую другую фоновую бизнес-задачу.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-155">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="0ad3b-156">По умолчанию для токена отмены задается время ожидания, равное 5 секундам, хотя это значение можно изменить при создании `WebHost` с помощью расширения `UseShutdownTimeout` интерфейса `IWebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-156">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="0ad3b-157">Это означает, что отмена службы ожидается в течение 5 секунд. В противном случае ее работа будет завершена внезапно.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-157">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="0ad3b-158">В следующем коде это время изменяется на 10 секунд:</span><span class="sxs-lookup"><span data-stu-id="0ad3b-158">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="0ad3b-159">Сводная диаграмма классов</span><span class="sxs-lookup"><span data-stu-id="0ad3b-159">Summary class diagram</span></span>

<span data-ttu-id="0ad3b-160">На приведенном ниже рисунке 8-26 представлена наглядная сводка классов и интерфейсов, которые задействованы в реализации IHostedService.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-160">The following image 8-26 shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>
 
![](./media/image27.png)

<span data-ttu-id="0ad3b-161">**Рис. 8-26**.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-161">**Figure 8-26.**</span></span> <span data-ttu-id="0ad3b-162">Диаграмма классов и интерфейсов, связанных с IHostedService</span><span class="sxs-lookup"><span data-stu-id="0ad3b-162">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="0ad3b-163">Основные положения и моменты, связанные с развертыванием</span><span class="sxs-lookup"><span data-stu-id="0ad3b-163">Deployment considerations and takeaways</span></span>

<span data-ttu-id="0ad3b-164">Важно отметить, что способ развертывания узла `WebHost` в ASP.NET Core или `Host` в .NET Core может влиять на конечное решение.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-164">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="0ad3b-165">Например, если вы развертываете `WebHost` в службах IIS или обычной службе приложений Azure, работа узла может быть завершена из-за перезапуска пула приложений.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-165">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="0ad3b-166">Однако если вы развертываете узел как контейнер в оркестраторе, таком как Kubernetes или Service Fabric, вы можете контролировать гарантированное число активных экземпляров узла.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-166">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="0ad3b-167">Кроме того, в облачной среде можно рассмотреть другие подходы, особенно предназначенные для таких сценариев, как Функции Azure.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-167">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> 

<span data-ttu-id="0ad3b-168">Даже при развертывании `WebHost` в пуле приложений применим ряд сценариев, таких как повторное заполнение или сброс кэша в памяти для приложения.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-168">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="0ad3b-169">Интерфейс `IHostedService` предоставляет удобный способ запуска фоновых задач в веб-приложении ASP.NET Core (в .NET Core 2.0) или в любом процессе или узле (при использовании `IHost` начиная с .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="0ad3b-169">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="0ad3b-170">Его главное преимущество — это возможность надлежащей отмены с целью очистки кода фоновых задач при завершении работы самого узла.</span><span class="sxs-lookup"><span data-stu-id="0ad3b-170">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="0ad3b-171">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="0ad3b-171">Additional resources</span></span>

-   <span data-ttu-id="0ad3b-172">**Создание запланированной задачи в ASP.NET Core или Standard 2.0**</span><span class="sxs-lookup"><span data-stu-id="0ad3b-172">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> 

    [<span data-ttu-id="0ad3b-173">*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*</span><span class="sxs-lookup"><span data-stu-id="0ad3b-173">*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*</span></span>](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   <span data-ttu-id="0ad3b-174">**Реализация интерфейса IHostedService в ASP.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="0ad3b-174">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> 

    [<span data-ttu-id="0ad3b-175">*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*</span><span class="sxs-lookup"><span data-stu-id="0ad3b-175">*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*</span></span>](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   <span data-ttu-id="0ad3b-176">**Образцы размещения в ASP.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="0ad3b-176">**ASP.NET Core 2.1 Hosting samples**</span></span> 

    [<span data-ttu-id="0ad3b-177">*https://github.com/aspnet/Hosting/tree/dev/samples/GenericHostSample*</span><span class="sxs-lookup"><span data-stu-id="0ad3b-177">*https://github.com/aspnet/Hosting/tree/dev/samples/GenericHostSample*</span></span>](https://github.com/aspnet/Hosting/tree/dev/samples/GenericHostSample)



>[!div class="step-by-step"]
<span data-ttu-id="0ad3b-178">[Назад] (test-aspnet-core-services-web-apps.md) [Далее] (../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="0ad3b-178">[Previous] (test-aspnet-core-services-web-apps.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
