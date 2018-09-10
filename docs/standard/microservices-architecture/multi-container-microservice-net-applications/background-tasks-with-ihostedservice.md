---
title: Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 6ce9e40334e80e8bd17ce2f3d2569a1e3c39d09e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272921"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="2ff07-103">Реализация фоновых задач в микрослужбах с помощью IHostedService и класса BackgroundService</span><span class="sxs-lookup"><span data-stu-id="2ff07-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="2ff07-104">Рано или поздно вам может потребоваться реализовать фоновые задачи и запланированные задания в приложении на основе микрослужб или приложении любого другого типа.</span><span class="sxs-lookup"><span data-stu-id="2ff07-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="2ff07-105">Разница при использовании архитектуры микрослужб в том, что вы можете реализовать отдельный процесс или контейнер для размещения таких фоновых задач, чтобы затем масштабировать его по мере необходимости, или даже обеспечить выполнение единственного экземпляра этого процесса или контейнера микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="2ff07-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="2ff07-106">Если посмотреть шире, в .NET Core такие задачи называются размещенными службами, так как они представляют собой службы или логику, размещаемые в узле, приложении или микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="2ff07-106">From a generic point of view, in .NET Core we called these type of tasks Hosted Services, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="2ff07-107">Обратите внимание на то, что в этом случае под размещенной службой понимается просто класс с логикой фоновой задачи.</span><span class="sxs-lookup"><span data-stu-id="2ff07-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="2ff07-108">Начиная с версии .NET Core 2.0, платформа предоставляет новый интерфейс <xref:Microsoft.Extensions.Hosting.IHostedService>, который позволяет легко реализовывать размещенные службы.</span><span class="sxs-lookup"><span data-stu-id="2ff07-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="2ff07-109">Главная идея заключается в том, что вы можете регистрировать несколько фоновых задач (размещенных служб), которые выполняются в фоновом режиме в процессе работы веб-узла или обычного узла, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="2ff07-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image below.</span></span>

![](./media/image26.png)

<span data-ttu-id="2ff07-110">**Рис. 8-25**.</span><span class="sxs-lookup"><span data-stu-id="2ff07-110">**Figure 8-25.**</span></span> <span data-ttu-id="2ff07-111">Использование интерфейса IHostedService в классах WebHost и Host</span><span class="sxs-lookup"><span data-stu-id="2ff07-111">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="2ff07-112">Обратите внимание на различие между `WebHost` и `Host`.</span><span class="sxs-lookup"><span data-stu-id="2ff07-112">Note the difference made between `WebHost` and `Host`.</span></span> <span data-ttu-id="2ff07-113">`WebHost` (базовый класс, реализующий интерфейс `IWebHost`) в ASP.NET Core 2.0 — это артефакт инфраструктуры, с помощью которого процесс получает доступ к возможностям сервера HTTP, например при реализации веб-приложения MVC или службы веб-интерфейса API.</span><span class="sxs-lookup"><span data-stu-id="2ff07-113">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="2ff07-114">Он предоставляет все новые преимущества инфраструктуры в ASP.NET Core, позволяя использовать внедрение зависимостей, вставлять промежуточные слои в конвейер HTTP и, в частности, применять `IHostedServices` для фоновых задач.</span><span class="sxs-lookup"><span data-stu-id="2ff07-114">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the HTTP pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="2ff07-115">`Host` (базовый класс, реализующий интерфейс `IHost`) — это новшество в .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="2ff07-115">A `Host` (base class implementing `IHost`), however, is something new in .NET Core 2.1.</span></span> <span data-ttu-id="2ff07-116">По существу, класс `Host` обеспечивает практически такую же инфраструктуру, что и класс `WebHost` (внедрение зависимостей, размещенные службы и т. д.), но в этом случае узел должен представлять собой более простой процесс без связанных с MVC веб-интерфейсами API или сервером HTTP возможностей.</span><span class="sxs-lookup"><span data-stu-id="2ff07-116">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="2ff07-117">Таким образом, вы можете либо создать специальный хост-процесс с помощью интерфейса IHost для реализации только размещенных служб, например микрослужбу, предназначенную для размещения `IHostedServices`, либо расширить существующий в ASP.NET Core класс `WebHost`, например существующий веб-интерфейс API ASP.NET Core или приложение MVC.</span><span class="sxs-lookup"><span data-stu-id="2ff07-117">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span> 

<span data-ttu-id="2ff07-118">Каждый подход имеет свои преимущества и недостатки в зависимости от потребностей бизнеса и требований к масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="2ff07-118">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="2ff07-119">Основной принцип заключается в том, что если фоновые задачи не связаны с HTTP (IWebHost), в .NET Core 2.1 следует использовать интерфейс IHost, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="2ff07-119">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use and IHost, when available in .NET Core 2.1.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="2ff07-120">Регистрация размещенных служб в WebHost или Host</span><span class="sxs-lookup"><span data-stu-id="2ff07-120">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="2ff07-121">Давайте более подробно разберем интерфейс `IHostedService`, так как его использование в классах `WebHost` и `Host` во многом схоже.</span><span class="sxs-lookup"><span data-stu-id="2ff07-121">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span> 

<span data-ttu-id="2ff07-122">Библиотека SignalR — один из примеров артефактов, использующих размещенные службы, однако ее можно применять и для более простых задач, таких как следующие:</span><span class="sxs-lookup"><span data-stu-id="2ff07-122">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

-   <span data-ttu-id="2ff07-123">фоновая задача опроса базы данных для поиска изменений;</span><span class="sxs-lookup"><span data-stu-id="2ff07-123">A background task polling a database looking for changes.</span></span>
-   <span data-ttu-id="2ff07-124">запланированная задача для периодического обновления кэша;</span><span class="sxs-lookup"><span data-stu-id="2ff07-124">A scheduled task updating some cache periodically.</span></span>
-   <span data-ttu-id="2ff07-125">реализация QueueBackgroundWorkItem, которая позволяет задаче выполняться в фоновом потоке;</span><span class="sxs-lookup"><span data-stu-id="2ff07-125">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
-   <span data-ttu-id="2ff07-126">обработка сообщений из очереди сообщений веб-приложения в фоновом режиме при использовании общих служб, таких как `ILogger`;</span><span class="sxs-lookup"><span data-stu-id="2ff07-126">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
-   <span data-ttu-id="2ff07-127">фоновая задача, запускаемая с помощью `Task.Run()`.</span><span class="sxs-lookup"><span data-stu-id="2ff07-127">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="2ff07-128">Выполнение любого из этих действий можно перенести в фоновую задачу на основе IHostedService.</span><span class="sxs-lookup"><span data-stu-id="2ff07-128">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="2ff07-129">Для добавления одного или нескольких экземпляров `IHostedServices` в `WebHost` или `Host` их следует зарегистрировать посредством стандартного внедрения зависимостей в классе ASP.NET Core `WebHost` (или в классе `Host` в .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="2ff07-129">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1).</span></span> <span data-ttu-id="2ff07-130">Фактически размещенные службы регистрируются в известном методе `ConfigureServices()` класса `Startup`, как в следующем коде типичного класса ASP.NET WebHost:</span><span class="sxs-lookup"><span data-stu-id="2ff07-130">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span> 

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

<span data-ttu-id="2ff07-131">В этом коде размещенная служба `GracePeriodManagerService` представляет собой реальный код микрослужбы размещения заказов в приложении eShopOnContainers, а другие две службы — это просто дополнительные примеры.</span><span class="sxs-lookup"><span data-stu-id="2ff07-131">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="2ff07-132">Выполнение фоновой задачи `IHostedService` согласуется с временем существования приложения (узла или микрослужбы).</span><span class="sxs-lookup"><span data-stu-id="2ff07-132">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="2ff07-133">Задачи регистрируются при запуске приложения, а при завершении его работы есть возможность произвести надлежащую обработку или очистку.</span><span class="sxs-lookup"><span data-stu-id="2ff07-133">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="2ff07-134">Фоновый поток можно запускать для выполнения любой задачи и без использования `IHostedService`.</span><span class="sxs-lookup"><span data-stu-id="2ff07-134">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="2ff07-135">Различие именно в том, что будет происходить при завершении работы приложения: поток будет просто завершаться без возможности надлежащей очистки.</span><span class="sxs-lookup"><span data-stu-id="2ff07-135">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>


## <a name="the-ihostedservice-interface"></a><span data-ttu-id="2ff07-136">Интерфейс IHostedService</span><span class="sxs-lookup"><span data-stu-id="2ff07-136">The IHostedService interface</span></span>

<span data-ttu-id="2ff07-137">При регистрации интерфейса `IHostedService` платформа .NET Core вызывает методы `StartAsync()` и `StopAsync()` типа `IHostedService` во время запуска и остановки приложения соответственно.</span><span class="sxs-lookup"><span data-stu-id="2ff07-137">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="2ff07-138">В частности, метод запуска вызывается после запуска сервера и активации `IApplicationLifetime.ApplicationStarted`.</span><span class="sxs-lookup"><span data-stu-id="2ff07-138">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="2ff07-139">Определение интерфейса `IHostedService` в .NET Core выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2ff07-139">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

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
<span data-ttu-id="2ff07-140">Как было показано ранее, вы можете создать несколько реализаций IHostedService и зарегистрировать их в методе `ConfigureService()` в контейнере внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2ff07-140">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="2ff07-141">Все эти размещенные службы будут запускаться и останавливаться вместе с приложением или микрослужбой.</span><span class="sxs-lookup"><span data-stu-id="2ff07-141">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="2ff07-142">Разработчик отвечает за обработку завершения действия или работы служб при вызове метода `StopAsync()` узлом.</span><span class="sxs-lookup"><span data-stu-id="2ff07-142">As a developer, you are responsible for handling the stopping action or your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="2ff07-143">Реализация IHostedService с помощью пользовательского класса размещенной службы, производного от базового класса BackgroundService</span><span class="sxs-lookup"><span data-stu-id="2ff07-143">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="2ff07-144">Можно пойти дальше и создать пользовательский класс размещенной службы с нуля, реализовав интерфейс `IHostedService`, как это требуется делать в .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2ff07-144">You could go ahead and create you custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span> 

<span data-ttu-id="2ff07-145">Но большинство фоновых задач имеют схожие потребности в отношении управления токенами отмены и других типичных операций, поэтому .NET Core 2.1 предоставит для них очень удобный абстрактный базовый класс BackgroundService, от которого можно создавать производные классы.</span><span class="sxs-lookup"><span data-stu-id="2ff07-145">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, .NET Core 2.1 will be providing a very convenient abstract base class you can derive from, named BackgroundService.</span></span>

<span data-ttu-id="2ff07-146">Он будет выполнять основную часть работы, связанной с настройкой фоновой задачи.</span><span class="sxs-lookup"><span data-stu-id="2ff07-146">That class provides the main work needed to set up the background task.</span></span> <span data-ttu-id="2ff07-147">Имейте в виду, что этот класс будет входить в состав библиотеки .NET Core 2.1, поэтому писать его не нужно.</span><span class="sxs-lookup"><span data-stu-id="2ff07-147">Note that this class will come in the .NET Core 2.1 library so you don’t need to write it.</span></span>

<span data-ttu-id="2ff07-148">Однако на момент написания этой статьи платформа .NET Core 2.1 еще не была выпущена.</span><span class="sxs-lookup"><span data-stu-id="2ff07-148">However, as of the time of this writing, .NET Core 2.1 has not been released.</span></span> <span data-ttu-id="2ff07-149">Поэтому в приложение eShopOnContainers, которое в настоящее время использует .NET Core 2.0, этот класс временно включен из репозитория .NET Core 2.1 с открытым кодом (требуется только лицензия на открытый код), так как он совместим с текущим интерфейсом IHostedService в .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2ff07-149">Therefore, in eShopOnContainers which is currently using .NET Core 2.0, we are just temporally incorporating that class from the .NET Core 2.1 open-source repo (no need of any proprietary license other than the open-source license) because it is compatible with the current IHostedService interface in .NET Core 2.0.</span></span> <span data-ttu-id="2ff07-150">Когда платформа .NET Core 2.1 будет выпущена, нужно будет лишь указать соответствующий пакет NuGet.</span><span class="sxs-lookup"><span data-stu-id="2ff07-150">When .NET Core 2.1 is released, you’ll just need to point to the right NuGet package.</span></span>

<span data-ttu-id="2ff07-151">Следующий код — это абстрактный базовый класс BackgroundService, реализованный в .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="2ff07-151">The next code is the abstract BackgroundService base class as implemented in .NET Core 2.1.</span></span>

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

<span data-ttu-id="2ff07-152">Благодаря такой унаследованной реализации при создании собственного класса размещенной службы, производного от приведенного выше абстрактного базового класса, необходимо просто реализовать в нем метод `ExecuteAsync()`. Пример представлен в следующем упрощенном коде из приложения eShopOnContainers, который опрашивает базу данных и при необходимости публикует события интеграции в шине событий.</span><span class="sxs-lookup"><span data-stu-id="2ff07-152">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

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

                // This eShopOnContainers method is querying a database table 
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

<span data-ttu-id="2ff07-153">В этом конкретном примере eShopOnContainers выполняет метод приложения, который отправляет запрос к таблице базы данных для поиска заказов с определенным состоянием, а при применении изменений публикует события интеграции через шину событий (она может быть основана на RabbitMQ или Служебной шине Azure).</span><span class="sxs-lookup"><span data-stu-id="2ff07-153">In this specific case for eShopOnContainers, it is executing an application method which is querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span> 

<span data-ttu-id="2ff07-154">Естественно, вместо этого можно выполнять любую другую фоновую бизнес-задачу.</span><span class="sxs-lookup"><span data-stu-id="2ff07-154">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="2ff07-155">По умолчанию для токена отмены задается время ожидания, равное 5 секундам, хотя это значение можно изменить при создании `WebHost` с помощью расширения `UseShutdownTimeout` интерфейса `IWebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="2ff07-155">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="2ff07-156">Это означает, что отмена службы ожидается в течение 5 секунд. В противном случае ее работа будет завершена внезапно.</span><span class="sxs-lookup"><span data-stu-id="2ff07-156">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="2ff07-157">В следующем коде это время изменяется на 10 секунд:</span><span class="sxs-lookup"><span data-stu-id="2ff07-157">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="2ff07-158">Сводная диаграмма классов</span><span class="sxs-lookup"><span data-stu-id="2ff07-158">Summary class diagram</span></span>

<span data-ttu-id="2ff07-159">На приведенном ниже рисунке 8-26 представлена наглядная сводка классов и интерфейсов, которые задействованы в реализации IHostedService.</span><span class="sxs-lookup"><span data-stu-id="2ff07-159">The following image 8-26 shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>
 
![](./media/image27.png)

<span data-ttu-id="2ff07-160">**Рис. 8-26**.</span><span class="sxs-lookup"><span data-stu-id="2ff07-160">**Figure 8-26.**</span></span> <span data-ttu-id="2ff07-161">Диаграмма классов и интерфейсов, связанных с IHostedService</span><span class="sxs-lookup"><span data-stu-id="2ff07-161">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="2ff07-162">Основные положения и моменты, связанные с развертыванием</span><span class="sxs-lookup"><span data-stu-id="2ff07-162">Deployment considerations and takeaways</span></span>

<span data-ttu-id="2ff07-163">Важно отметить, что способ развертывания узла `WebHost` в ASP.NET Core или `Host` в .NET Core может влиять на конечное решение.</span><span class="sxs-lookup"><span data-stu-id="2ff07-163">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="2ff07-164">Например, если вы развертываете `WebHost` в службах IIS или обычной службе приложений Azure, работа узла может быть завершена из-за перезапуска пула приложений.</span><span class="sxs-lookup"><span data-stu-id="2ff07-164">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="2ff07-165">Однако если вы развертываете узел как контейнер в оркестраторе, таком как Kubernetes или Service Fabric, вы можете контролировать гарантированное число активных экземпляров узла.</span><span class="sxs-lookup"><span data-stu-id="2ff07-165">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="2ff07-166">Кроме того, в облачной среде можно рассмотреть другие подходы, особенно предназначенные для таких сценариев, как Функции Azure.</span><span class="sxs-lookup"><span data-stu-id="2ff07-166">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> 

<span data-ttu-id="2ff07-167">Даже при развертывании `WebHost` в пуле приложений применим ряд сценариев, таких как повторное заполнение или сброс кэша в памяти для приложения.</span><span class="sxs-lookup"><span data-stu-id="2ff07-167">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="2ff07-168">Интерфейс `IHostedService` предоставляет удобный способ запуска фоновых задач в веб-приложении ASP.NET Core (в .NET Core 2.0) или в любом процессе или узле (при использовании `IHost` начиная с .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="2ff07-168">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="2ff07-169">Его главное преимущество — это возможность надлежащей отмены с целью очистки кода фоновых задач при завершении работы самого узла.</span><span class="sxs-lookup"><span data-stu-id="2ff07-169">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="2ff07-170">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2ff07-170">Additional resources</span></span>

-   <span data-ttu-id="2ff07-171">**Создание запланированной задачи в ASP.NET Core или Standard 2.0**</span><span class="sxs-lookup"><span data-stu-id="2ff07-171">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> 

    [*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   <span data-ttu-id="2ff07-172">**Реализация интерфейса IHostedService в ASP.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="2ff07-172">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> 

    [*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   <span data-ttu-id="2ff07-173">**Образцы размещения в ASP.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="2ff07-173">**ASP.NET Core 2.1 Hosting samples**</span></span> 

    [*https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample*](https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample)

>[!div class="step-by-step"]
<span data-ttu-id="2ff07-174">[Назад](test-aspnet-core-services-web-apps.md)
[Вперед](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="2ff07-174">[Previous](test-aspnet-core-services-web-apps.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
