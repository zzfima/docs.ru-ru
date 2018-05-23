---
title: Реализация прикладного уровня микрослужб с помощью веб-интерфейсов API
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация прикладного уровня микрослужб с помощью веб-интерфейсов API
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 7c785814c4726dd805ad7b0dccb6a3584118cc65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="72332-103">Реализация прикладного уровня микрослужб с помощью веб-интерфейсов API</span><span class="sxs-lookup"><span data-stu-id="72332-103">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="72332-104">Внедрение объектов инфраструктуры в прикладной уровень с помощью внедрения зависимостей</span><span class="sxs-lookup"><span data-stu-id="72332-104">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="72332-105">Как упоминалось ранее, прикладной уровень может быть реализован в рамках создаваемого артефакта, например проекта веб-интерфейса API или проекта веб-приложения MVC.</span><span class="sxs-lookup"><span data-stu-id="72332-105">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="72332-106">При создании микрослужбы с помощью ASP.NET Core прикладным уровнем обычно является библиотека веб-интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="72332-106">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="72332-107">Чтобы отделить ту часть, которая берется из ASP.NET Core (инфраструктуру и контроллеры), от пользовательского кода прикладного уровня, можно поместить прикладной уровень в отдельную библиотеку классов, хотя это необязательно.</span><span class="sxs-lookup"><span data-stu-id="72332-107">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="72332-108">Например, код прикладного уровня для микрослужбы размещения заказов реализуется непосредственно в рамках проекта **Ordering.API** (проекта веб-интерфейса API ASP.NET Core), как показано на рисунке 9-23.</span><span class="sxs-lookup"><span data-stu-id="72332-108">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-23.</span></span>

![](./media/image20.png)

<span data-ttu-id="72332-109">**Рис. 9-23**.</span><span class="sxs-lookup"><span data-stu-id="72332-109">**Figure 9-23**.</span></span> <span data-ttu-id="72332-110">Прикладной уровень в проекте веб-интерфейса API ASP.NET Core Ordering.API</span><span class="sxs-lookup"><span data-stu-id="72332-110">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="72332-111">ASP.NET Core содержит простой [встроенный контейнер IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (представленный интерфейсом IServiceProvider), поддерживающий внедрение через конструктор по умолчанию, а ASP.NET предоставляет посредством внедрения зависимостей определенные службы.</span><span class="sxs-lookup"><span data-stu-id="72332-111">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="72332-112">В ASP.NET Core под термином *служба* понимаются любые зарегистрированные типы, которые будут внедряться посредством внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="72332-112">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="72332-113">Настроить службы встроенного контейнера можно в методе ConfigureServices в классе Startup вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="72332-113">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="72332-114">Зависимости реализуются в службах, которые требуются типу.</span><span class="sxs-lookup"><span data-stu-id="72332-114">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="72332-115">Как правило, необходимо внедрить зависимости, реализующие объекты инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72332-115">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="72332-116">Типичной внедряемой зависимостью является репозиторий.</span><span class="sxs-lookup"><span data-stu-id="72332-116">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="72332-117">Однако можно внедрять и любые другие имеющиеся зависимости инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72332-117">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="72332-118">Чтобы упростить реализацию, можно напрямую внедрить объект на основе шаблона "Единица работы" (объект EF DbContext), так как DBContext также является реализацией сохраняемых объектов инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72332-118">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="72332-119">В приведенном ниже примере показано, как платформа .NET Core внедряет необходимые объекты репозитория посредством конструктора.</span><span class="sxs-lookup"><span data-stu-id="72332-119">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="72332-120">Класс представляет собой обработчик команд, о котором мы поговорим в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="72332-120">The class is a command handler, which we will cover in the next section.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator, 
                                     IOrderRepository orderRepository, 
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ?? 
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? 
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? 
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic 
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, 
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId, 
                              message.CardNumber, message.CardSecurityNumber, 
                              message.CardHolderName, message.CardExpiration);
            
        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

<span data-ttu-id="72332-121">Этот класс использует внедренные репозитории для выполнения транзакции и сохранения изменений состояния.</span><span class="sxs-lookup"><span data-stu-id="72332-121">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="72332-122">Не имеет значения, является ли класс обработчиком команд, методом контроллера веб-интерфейса API ASP.NET Core или [службой приложения DDD](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="72332-122">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="72332-123">В любом случае он представляет собой простой класс, который использует репозитории, сущности домена и другие средства координации приложения подобно тому, как это делает обработчик команд.</span><span class="sxs-lookup"><span data-stu-id="72332-123">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="72332-124">Внедрение зависимостей работает одинаково для всех перечисленных выше классов, как в этом примере, в котором внедрение зависимостей основано на конструкторе.</span><span class="sxs-lookup"><span data-stu-id="72332-124">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="72332-125">Регистрация типов и интерфейсов или абстракций для реализации зависимостей</span><span class="sxs-lookup"><span data-stu-id="72332-125">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="72332-126">Прежде чем использовать объекты, внедренные посредством конструкторов, необходимо знать, где следует зарегистрировать интерфейсы и классы, которые предоставляют объекты, внедренные в приложение с помощью внедрения зависимостей</span><span class="sxs-lookup"><span data-stu-id="72332-126">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="72332-127">(например, в случае внедрения зависимостей на основе конструктора, показанного выше).</span><span class="sxs-lookup"><span data-stu-id="72332-127">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="72332-128">Использование встроенного конструктора IoC, предоставляемого платформой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72332-128">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="72332-129">При использовании встроенного контейнера IoC, предоставляемого платформой ASP.NET Core, типы, которые нужно внедрить, регистрируются в методе ConfigureServices в файле Startup.cs, как в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="72332-129">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

```csharp
// Registration of types into ASP.NET Core built-in container
public void ConfigureServices(IServiceCollection services)
{
    // Register out-of-the-box framework services.
    services.AddDbContext<CatalogContext>(c =>
    {
        c.UseSqlServer(Configuration["ConnectionString"]);
    },
    ServiceLifetime.Scoped
    );
    services.AddMvc();
    // Register custom application dependencies.
    services.AddScoped<IMyCustomRepository, MyCustomSQLRepository>();
}
```

<span data-ttu-id="72332-130">Чаще всего типы регистрируются в контейнере IoC парами, состоящими из интерфейса и связанного с ним класса реализации.</span><span class="sxs-lookup"><span data-stu-id="72332-130">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="72332-131">Затем при запросе объекта из контейнера IoC посредством любого конструктора вы запрашиваете объект определенного типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="72332-131">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="72332-132">Например, в предыдущем примере в последней строке указано, что когда любой из конструкторов имеет зависимость от IMyCustomRepository (интерфейса или абстракции), контейнер IoC внедряет экземпляр класса реализации MyCustomSQLServerRepository.</span><span class="sxs-lookup"><span data-stu-id="72332-132">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="72332-133">Автоматическая регистрация типов с помощью библиотеки Scrutor</span><span class="sxs-lookup"><span data-stu-id="72332-133">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="72332-134">При использовании внедрения зависимостей в .NET Core может потребоваться проверить сборку и автоматически зарегистрировать ее типы в соответствии с соглашением.</span><span class="sxs-lookup"><span data-stu-id="72332-134">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="72332-135">Эта возможность в настоящее время недоступна в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="72332-135">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="72332-136">Однако для этого можно использовать библиотеку [Scrutor](https://github.com/khellang/Scrutor).</span><span class="sxs-lookup"><span data-stu-id="72332-136">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="72332-137">Такой подход удобен в случае, если имеются десятки типов, которые необходимо зарегистрировать в контейнере IoC.</span><span class="sxs-lookup"><span data-stu-id="72332-137">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="72332-138">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72332-138">Additional resources</span></span>

-   <span data-ttu-id="72332-139">**Мэтью Кинг (Matthew King). Регистрация служб в Scrutor**
    [*https://mking.net/blog/registering-services-with-scrutor*](https://mking.net/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="72332-139">**Matthew King. Registering services with Scrutor**
[*https://mking.net/blog/registering-services-with-scrutor*](https://mking.net/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="72332-140">**Кристиан Хелланг (Kristian Hellang). Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="72332-140">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="72332-141">Репозиторий GitHub.</span><span class="sxs-lookup"><span data-stu-id="72332-141">GitHub repo.</span></span>
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="72332-142">Использование Autofac в качестве IoC</span><span class="sxs-lookup"><span data-stu-id="72332-142">Using Autofac as an IoC container</span></span>

<span data-ttu-id="72332-143">Вы также можете использовать дополнительные контейнеры IoC и подключить их к конвейеру ASP.NET Core, как в случае с микрослужбой размещения заказов в eShopOnContainers, которая использует [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="72332-143">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="72332-144">При использовании Autofac типы, как правило, регистрируются посредством модулей, что позволяет разделить типы регистрации на несколько файлов в зависимости от местонахождения типов, так же как типы приложения распределяются по нескольким библиотекам классов.</span><span class="sxs-lookup"><span data-stu-id="72332-144">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="72332-145">Например, ниже приведен [модуль приложения Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) для проекта [веб-интерфейса API Ordering.API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) с типами, которые потребуется внедрить.</span><span class="sxs-lookup"><span data-stu-id="72332-145">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

```csharp
public class ApplicationModule : Autofac.Module
{
    public string QueriesConnectionString { get; }
    public ApplicationModule(string qconstr)
    {
        QueriesConnectionString = qconstr;
    }

    protected override void Load(ContainerBuilder builder)
    {
        builder.Register(c => new OrderQueries(QueriesConnectionString))
            .As<IOrderQueries>()
            .InstancePerLifetimeScope();
        builder.RegisterType<BuyerRepository>()
            .As<IBuyerRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<OrderRepository>()
            .As<IOrderRepository>()
            .InstancePerLifetimeScope();
        builder.RegisterType<RequestManager>()
            .As<IRequestManager>()
            .InstancePerLifetimeScope();
   }
}
```

<span data-ttu-id="72332-146">Принципы и процесс регистрации очень похожи на регистрацию типов с помощью встроенного контейнера IoC ASP.NET Core, но синтаксис при использовании Autofac немного иной.</span><span class="sxs-lookup"><span data-stu-id="72332-146">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core IoC container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="72332-147">В примере кода абстракция IOrderRepository регистрируется вместе с классом реализации OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="72332-147">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="72332-148">Это означает, что каждый раз, когда в конструкторе объявляется зависимость посредством абстракции или интерфейса IOrderRepository, контейнер IoC внедряет экземпляр класса OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="72332-148">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="72332-149">Тип области экземпляра определяет то, как экземпляр используется совместно при запросах к одной и той же службе или зависимости.</span><span class="sxs-lookup"><span data-stu-id="72332-149">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="72332-150">При запросе зависимости контейнер IoC может вернуть следующее:</span><span class="sxs-lookup"><span data-stu-id="72332-150">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="72332-151">один экземпляр для каждой области времени существования (в контейнере IoC ASP.NET Core такой экземпляр называется экземпляром *с заданной областью*);</span><span class="sxs-lookup"><span data-stu-id="72332-151">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="72332-152">новый экземпляр для каждой зависимости (в контейнере IoC ASP.NET Core такой экземпляр называется *временным*);</span><span class="sxs-lookup"><span data-stu-id="72332-152">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="72332-153">один общий экземпляр для всех объектов, использующих контейнер IoC (в контейнере IoC ASP.NET Core такой экземпляр называется *единичным*).</span><span class="sxs-lookup"><span data-stu-id="72332-153">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="72332-154">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72332-154">Additional resources</span></span>

-   <span data-ttu-id="72332-155">**Общие сведения о внедрении зависимостей в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="72332-155">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="72332-156">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="72332-156">**Autofac.**</span></span> <span data-ttu-id="72332-157">Официальная документация.</span><span class="sxs-lookup"><span data-stu-id="72332-157">Official documentation.</span></span>
    [*http://docs.autofac.org/en/latest/*](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="72332-158">**Сравнение времени существования службы контейнеров IoC ASP.NET Core с областями действия экземпляра контейнера IoC Autofac. Сезар де ла Торре (Cesar de la Torre).**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="72332-158">**Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes - Cesar de la Torre.**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="72332-159">Реализация шаблонов команд и обработчиков команд</span><span class="sxs-lookup"><span data-stu-id="72332-159">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="72332-160">В примере внедрения зависимостей через конструктор в предыдущем разделе контейнер IoC внедрял репозитории через конструктор в классе.</span><span class="sxs-lookup"><span data-stu-id="72332-160">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="72332-161">Но куда именно они внедрялись?</span><span class="sxs-lookup"><span data-stu-id="72332-161">But exactly where were they injected?</span></span> <span data-ttu-id="72332-162">В простом веб-интерфейсе API (например, микрослужбе каталога в eShopOnContainers) они внедряются на уровне контроллеров MVC в конструкторе контроллера.</span><span class="sxs-lookup"><span data-stu-id="72332-162">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="72332-163">Однако в коде, приведенном в начале этого раздела (класс [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) из службы Ordering.API в eShopOnContainers), внедрение зависимостей производится через конструктор определенного обработчика команд.</span><span class="sxs-lookup"><span data-stu-id="72332-163">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="72332-164">Давайте рассмотрим, что такое обработчик команд и зачем его использовать.</span><span class="sxs-lookup"><span data-stu-id="72332-164">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="72332-165">Шаблон команды, по сути, связан с шаблоном CQRS, который был представлен ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="72332-165">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="72332-166">CQRS имеет два аспекта.</span><span class="sxs-lookup"><span data-stu-id="72332-166">CQRS has two sides.</span></span> <span data-ttu-id="72332-167">Первый аспект — это запросы, причем используются упрощенные запросы на основе микро-ORM [Dapper](https://github.com/StackExchange/dapper-dot-net), который был рассмотрен ранее.</span><span class="sxs-lookup"><span data-stu-id="72332-167">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="72332-168">Второй аспект — это команды, которые являются отправной точкой для транзакций, и канал входных данных извне службы.</span><span class="sxs-lookup"><span data-stu-id="72332-168">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="72332-169">Как показано на рисунке 9-24, шаблон основан на принятии команд со стороны клиента, их обработке на основе правил модели предметной области и, наконец, сохранении состояний с помощью транзакций.</span><span class="sxs-lookup"><span data-stu-id="72332-169">As shown in Figure 9-24, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="72332-170">**Рис. 9-24**.</span><span class="sxs-lookup"><span data-stu-id="72332-170">**Figure 9-24**.</span></span> <span data-ttu-id="72332-171">Общее представление команд или "уровня транзакций" в шаблоне CQRS</span><span class="sxs-lookup"><span data-stu-id="72332-171">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="72332-172">Класс команд</span><span class="sxs-lookup"><span data-stu-id="72332-172">The command class</span></span>

<span data-ttu-id="72332-173">Команда — это запрос к системе на выполнение действия, которое изменяет состояние системы.</span><span class="sxs-lookup"><span data-stu-id="72332-173">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="72332-174">Команды являются императивными и должны обрабатываться только один раз.</span><span class="sxs-lookup"><span data-stu-id="72332-174">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="72332-175">Так как команды являются императивами, в их именах обычно есть глагол в повелительном наклонении (например, create или update) и может присутствовать тип агрегата, например CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="72332-175">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="72332-176">В отличие от события, команда не связана с фактом в прошлом. Это всего лишь запрос, который может быть отклонен.</span><span class="sxs-lookup"><span data-stu-id="72332-176">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="72332-177">Команды могут поступать из пользовательского интерфейса в результате инициации запроса пользователем или из диспетчера процессов, когда он предписывает агрегату выполнить действие.</span><span class="sxs-lookup"><span data-stu-id="72332-177">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="72332-178">Важной особенностью команды является то, что она должна обрабатываться только один раз одним получателем.</span><span class="sxs-lookup"><span data-stu-id="72332-178">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="72332-179">Связано это с тем, что команда представляет собой одно действие или транзакцию, которую нужно выполнить в приложении.</span><span class="sxs-lookup"><span data-stu-id="72332-179">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="72332-180">Например, одну и ту же команду создания заказа не следует обрабатывать несколько раз.</span><span class="sxs-lookup"><span data-stu-id="72332-180">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="72332-181">Это важное различие между командами и событиями.</span><span class="sxs-lookup"><span data-stu-id="72332-181">This is an important difference between commands and events.</span></span> <span data-ttu-id="72332-182">События могут обрабатываться несколько раз, так как одно событие может представлять интерес для множества систем или микрослужб.</span><span class="sxs-lookup"><span data-stu-id="72332-182">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="72332-183">Кроме того, важно, чтобы команда обрабатывалась только одни раз, если она не является идемпотентной.</span><span class="sxs-lookup"><span data-stu-id="72332-183">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="72332-184">Команда является идемпотентной, если она может выполняться несколько раз с одинаковым результатом либо из-за самого ее характера, либо из-за способа обработки команды системой.</span><span class="sxs-lookup"><span data-stu-id="72332-184">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="72332-185">Команды имеет смысл делать идемпотентными, если этого требуют бизнес-правила и инварианты предметной области.</span><span class="sxs-lookup"><span data-stu-id="72332-185">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="72332-186">Продолжая приведенный выше пример, если по какой-либо причине (логика повтора, взлом и т. д.) одна и та же команда CreateOrder поступает в систему несколько раз, необходимо иметь возможность определить такую ситуацию и предотвратить создание нескольких заказов.</span><span class="sxs-lookup"><span data-stu-id="72332-186">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="72332-187">Для этого в операции необходимо включить какой-либо идентификатор, чтобы определять, были ли команда или обновление уже обработаны.</span><span class="sxs-lookup"><span data-stu-id="72332-187">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="72332-188">Команда отправляется одному получателю. Она не публикуется.</span><span class="sxs-lookup"><span data-stu-id="72332-188">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="72332-189">Публикуются события интеграции, сообщающие некий факт — что произошло что-то, что может представлять интерес для приемников событий.</span><span class="sxs-lookup"><span data-stu-id="72332-189">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="72332-190">Издателя событий не интересует, какие приемники получат событие и что они будут с ним делать.</span><span class="sxs-lookup"><span data-stu-id="72332-190">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="72332-191">Однако с событиями интеграции дело обстоит иначе, о чем уже говорилось в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="72332-191">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="72332-192">Команда реализуется с помощью класса, который содержит поля данных или коллекции со всеми сведениями, необходимыми для выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="72332-192">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="72332-193">Команда — это объект передачи данных (DTO) особого типа, предназначенный специально для запроса изменений или транзакций.</span><span class="sxs-lookup"><span data-stu-id="72332-193">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="72332-194">Сама по себе команда основана только на тех сведениях, которые необходимы для ее обработки, и ни на чем больше.</span><span class="sxs-lookup"><span data-stu-id="72332-194">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="72332-195">В приведенном ниже примере показан упрощенный класс CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="72332-195">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="72332-196">Это неизменяемая команда, которая используется в микрослужбе размещения заказов в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="72332-196">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

```csharp
// DDD and CQRS patterns comment
// Note that we recommend that you implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/library/bb383979.aspx
[DataContract]
public class CreateOrderCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    private readonly List<OrderItemDTO> _orderItems;
    [DataMember]
    public string City { get; private set; }
    [DataMember]
    public string Street { get; private set; }
    [DataMember]
    public string State { get; private set; }
    [DataMember]
    public string Country { get; private set; }
    [DataMember]
    public string ZipCode { get; private set; }
    [DataMember]
    public string CardNumber { get; private set; }
    [DataMember]
    public string CardHolderName { get; private set; }
    [DataMember]
    public DateTime CardExpiration { get; private set; }
    [DataMember]
    public string CardSecurityNumber { get; private set; }
    [DataMember]
    public int CardTypeId { get; private set; }
    [DataMember]
    public IEnumerable<OrderItemDTO> OrderItems => _orderItems;

    public CreateOrderCommand()
    {
        _orderItems = new List<OrderItemDTO>();
    }

    public CreateOrderCommand(List<OrderItemDTO> orderItems, string city,
        string street,
        string state, string country, string zipcode,
        string cardNumber, string cardHolderName, DateTime cardExpiration,
        string cardSecurityNumber, int cardTypeId) : this()
    {
        _orderItems = orderItems;
        City = city;
        Street = street;
        State = state;
        Country = country;
        ZipCode = zipcode;
        CardNumber = cardNumber;
        CardHolderName = cardHolderName;
        CardSecurityNumber = cardSecurityNumber;
        CardTypeId = cardTypeId;
        CardExpiration = cardExpiration;
    }

    public class OrderItemDTO
    {
        public int ProductId { get; set; }
        public string ProductName { get; set; }
        public decimal UnitPrice { get; set; }
        public decimal Discount { get; set; }
        public int Units { get; set; }
        public string PictureUrl { get; set; }
    }
}
```

<span data-ttu-id="72332-197">По существу, класс команды содержит все данные, необходимые для выполнения бизнес-транзакции с помощью объектов модели предметной области.</span><span class="sxs-lookup"><span data-stu-id="72332-197">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="72332-198">Таким образом, команды — это попросту структуры данных, которые содержат доступные только для чтения данные, но не алгоритмы.</span><span class="sxs-lookup"><span data-stu-id="72332-198">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="72332-199">Имя команды указывает на ее назначение.</span><span class="sxs-lookup"><span data-stu-id="72332-199">The command’s name indicates its purpose.</span></span> <span data-ttu-id="72332-200">Во многих языках, например в C\#, команды представлены классами, но они не являются настоящими классами в объектно-ориентированном смысле.</span><span class="sxs-lookup"><span data-stu-id="72332-200">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="72332-201">Дополнительной характеристикой команд является неизменяемость, так как предполагается, что они обрабатываются непосредственно моделью предметной области.</span><span class="sxs-lookup"><span data-stu-id="72332-201">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="72332-202">Они не должны изменяться в течение предполагаемого времени существования.</span><span class="sxs-lookup"><span data-stu-id="72332-202">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="72332-203">В классе C\# неизменяемость может обеспечиваться благодаря отсутствию методов задания или других методов, которые изменяют внутреннее состояние.</span><span class="sxs-lookup"><span data-stu-id="72332-203">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="72332-204">Например, в плане данных класс команды для создания заказа может быть аналогичен создаваемому заказу, однако, вероятно, требуемые атрибуты могут различаться.</span><span class="sxs-lookup"><span data-stu-id="72332-204">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="72332-205">Например, команда CreateOrderCommand не включает в себя идентификатор заказа, так как заказ еще не создан.</span><span class="sxs-lookup"><span data-stu-id="72332-205">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="72332-206">Многие классы команд могут быть простыми и требуют лишь несколько полей, связанных с изменяемым состоянием.</span><span class="sxs-lookup"><span data-stu-id="72332-206">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="72332-207">Например, это верно в случае изменения состояния заказа с "обрабатывается" на "оплачен" или "отправлен" с помощью команды наподобие следующей:</span><span class="sxs-lookup"><span data-stu-id="72332-207">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

```csharp
[DataContract]
public class UpdateOrderStatusCommand
    :IAsyncRequest<bool>
{
    [DataMember]
    public string Status { get; private set; }

    [DataMember]
    public string OrderId { get; private set; }

    [DataMember]
    public string BuyerIdentityGuid { get; private set; }
}
```

<span data-ttu-id="72332-208">Некоторые разработчики разделяют объекты запросов пользовательского интерфейса и объекты DTO команд, но это всего лишь вопрос предпочтений.</span><span class="sxs-lookup"><span data-stu-id="72332-208">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="72332-209">Такое разделение требует значительных усилий, а преимущества невелики, причем объекты очень схожи по сути.</span><span class="sxs-lookup"><span data-stu-id="72332-209">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="72332-210">Например, в eShopOnContainers некоторые команды поступают непосредственно со стороны клиента.</span><span class="sxs-lookup"><span data-stu-id="72332-210">For instance, in eShopOnContainers, some commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="72332-211">Класс обработчика команд</span><span class="sxs-lookup"><span data-stu-id="72332-211">The Command Handler class</span></span>

<span data-ttu-id="72332-212">Для каждой команды следует реализовать класс обработчика команд.</span><span class="sxs-lookup"><span data-stu-id="72332-212">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="72332-213">Этого требует шаблон, и именно в этом классе будут использоваться объект команды, объекты предметной области и объекты репозиториев инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72332-213">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="72332-214">Обработчик команд — это, по сути, центральный элемент прикладного уровня в рамках CQRS и DDD.</span><span class="sxs-lookup"><span data-stu-id="72332-214">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="72332-215">Однако вся логика предметной области должна содержаться в классах предметной области — корневых объектах агрегатов (корневых сущностях), дочерних сущностях или [службах предметной области](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), но не в обработчике команд, который представляет собой класс прикладного уровня.</span><span class="sxs-lookup"><span data-stu-id="72332-215">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="72332-216">Обработчик команд принимает команду и получает результат из используемого агрегата.</span><span class="sxs-lookup"><span data-stu-id="72332-216">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="72332-217">Результатом должно быть успешное выполнение команды или исключение.</span><span class="sxs-lookup"><span data-stu-id="72332-217">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="72332-218">В случае исключения состояние системы не должно меняться.</span><span class="sxs-lookup"><span data-stu-id="72332-218">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="72332-219">Обработчик команд обычно выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72332-219">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="72332-220">получает объект команды, например DTO (от [медиатора](https://en.wikipedia.org/wiki/Mediator_pattern) или другого объекта инфраструктуры);</span><span class="sxs-lookup"><span data-stu-id="72332-220">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="72332-221">проверяет допустимость команды (если она не была проверена медиатором);</span><span class="sxs-lookup"><span data-stu-id="72332-221">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="72332-222">создает экземпляр корневой сущности агрегата, являющийся целевым для текущей команды;</span><span class="sxs-lookup"><span data-stu-id="72332-222">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="72332-223">выполняет метод экземпляра корневой сущности агрегата, получая необходимые данные из команды;</span><span class="sxs-lookup"><span data-stu-id="72332-223">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="72332-224">сохраняет новое состояние агрегата в связанной с ним базе данных.</span><span class="sxs-lookup"><span data-stu-id="72332-224">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="72332-225">Эта последняя операция и является транзакцией.</span><span class="sxs-lookup"><span data-stu-id="72332-225">This last operation is the actual transaction.</span></span>

<span data-ttu-id="72332-226">Как правило, обработчик команд работает с одним агрегатом, определяемым корневым объектом агрегата (корневой сущностью).</span><span class="sxs-lookup"><span data-stu-id="72332-226">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="72332-227">Если принимаемая команда должна влиять на несколько агрегатов, можно использовать события предметной области для распространения состояний или действий в нескольких агрегатах.</span><span class="sxs-lookup"><span data-stu-id="72332-227">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates.</span></span>

<span data-ttu-id="72332-228">Важным моментом является то, что при обработке команды вся логика предметной области должна находиться внутри модели предметной области (агрегатов), причем она должна быть полностью инкапсулирована и готова для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="72332-228">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="72332-229">Обработчик команд служит лишь для того, чтобы получить модель предметной области из базы данных и (на последнем этапе) сообщить уровню инфраструктуры (репозиториям) о необходимости сохранить изменения в случае изменения модели.</span><span class="sxs-lookup"><span data-stu-id="72332-229">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="72332-230">Преимуществом такого подхода является возможность рефакторинга логики предметной области в рамках изолированной, полностью инкапсулированной поведенческой модели предметной области без изменения кода на прикладном уровне или уровне инфраструктуры, то есть на связующем уровне (обработчики команд, веб-интерфейс API, репозитории и т. д.).</span><span class="sxs-lookup"><span data-stu-id="72332-230">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="72332-231">Если обработчики команд становятся слишком сложными, содержащими слишком много логики, это может быть признаком плохого кода.</span><span class="sxs-lookup"><span data-stu-id="72332-231">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="72332-232">Проверьте их и, если найдете логику предметной области, выполните рефакторинг кода, чтобы переместить эту логику в методы объектов предметной области (корневая сущность агрегата и дочерняя сущность).</span><span class="sxs-lookup"><span data-stu-id="72332-232">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="72332-233">В приведенном ниже коде в качестве примера класса обработчика команд показан тот же класс CreateOrderCommandHandler, который вы уже видели в начале этой главы.</span><span class="sxs-lookup"><span data-stu-id="72332-233">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="72332-234">В этом случае мы хотим привлечь внимание к методу Handle и операциям с объектами и агрегатами модели предметной области.</span><span class="sxs-lookup"><span data-stu-id="72332-234">In this case, we want to highlight the Handle method and the operations with the domain model objects/aggregates.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator, 
                                     IOrderRepository orderRepository, 
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ?? 
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? 
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? 
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic 
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State, 
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId, 
                              message.CardNumber, message.CardSecurityNumber, 
                              message.CardHolderName, message.CardExpiration);
            
        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

<span data-ttu-id="72332-235">Обработчик команд должен выполнять следующие дополнительные действия:</span><span class="sxs-lookup"><span data-stu-id="72332-235">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="72332-236">использовать данные команды для взаимодействия с методами и поведением корневой сущности агрегата;</span><span class="sxs-lookup"><span data-stu-id="72332-236">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="72332-237">вызывать события предметной области внутри объектов предметной области во время выполнения транзакции прозрачным с точки зрения обработчика команд образом;</span><span class="sxs-lookup"><span data-stu-id="72332-237">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="72332-238">в случае успешного результата операции агрегата вызывать обработчик команд событий интеграции после завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="72332-238">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="72332-239">(Эти события могут также вызываться классами инфраструктуры, такими как репозитории.)</span><span class="sxs-lookup"><span data-stu-id="72332-239">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="72332-240">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72332-240">Additional resources</span></span>

-   <span data-ttu-id="72332-241">**Марк Симанн (Mark Seemann). Граничный слой приложения не является объектно-ориентированным**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="72332-241">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="72332-242">**Команды и события**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="72332-242">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="72332-243">**Что делает обработчик команд?**
    [*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="72332-243">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="72332-244">**Джимми Богард (Jimmy Bogard). Шаблоны команд домена — обработчики**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="72332-244">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="72332-245">**Джимми Богард (Jimmy Bogard). Шаблоны команд домена — проверка**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="72332-245">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="72332-246">Конвейер обработки команд: активация обработчика команд</span><span class="sxs-lookup"><span data-stu-id="72332-246">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="72332-247">Следующий вопрос заключается в том, как вызывается обработчик команд.</span><span class="sxs-lookup"><span data-stu-id="72332-247">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="72332-248">Его можно вызывать из каждого связанного контроллера ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="72332-248">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="72332-249">Однако такой подход требует слишком большого количества связей и не идеален.</span><span class="sxs-lookup"><span data-stu-id="72332-249">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="72332-250">Другие два варианта, которые рекомендуются, представлены ниже:</span><span class="sxs-lookup"><span data-stu-id="72332-250">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="72332-251">посредством артефакта шаблона медиатора в памяти;</span><span class="sxs-lookup"><span data-stu-id="72332-251">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="72332-252">с помощью асинхронной очереди сообщений между контроллерами и обработчиками.</span><span class="sxs-lookup"><span data-stu-id="72332-252">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="72332-253">Использование шаблона медиатора (в памяти) в конвейере команд</span><span class="sxs-lookup"><span data-stu-id="72332-253">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="72332-254">Как показано на рисунке 9-25, в рамках подхода на основе CQRS используется интеллектуальный медиатор, похожий на шину в памяти, который может осуществлять перенаправление в нужный обработчик команд в соответствии с типом полученной команды или объекта DTO.</span><span class="sxs-lookup"><span data-stu-id="72332-254">As shown in Figure 9-25, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="72332-255">Одиночные черные стрелки между компонентами представляют зависимости между объектами (которые часто внедряются посредством внедрения зависимостей) и соответствующие взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="72332-255">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="72332-256">**Рис. 9-25**.</span><span class="sxs-lookup"><span data-stu-id="72332-256">**Figure 9-25**.</span></span> <span data-ttu-id="72332-257">Использование шаблона медиатора в процессе обработки в отдельной микрослужбе CQRS</span><span class="sxs-lookup"><span data-stu-id="72332-257">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="72332-258">Основанием для применения шаблона медиатора является то, что в корпоративных приложениях обработка запросов может становиться сложной.</span><span class="sxs-lookup"><span data-stu-id="72332-258">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="72332-259">Вам может требоваться добавить сквозную функциональность, например ведения журнала, проверки, аудит и безопасность.</span><span class="sxs-lookup"><span data-stu-id="72332-259">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="72332-260">В таком случае вы можете применить конвейер медиатора (см. статью [Шаблон медиатора](https://en.wikipedia.org/wiki/Mediator_pattern)) в качестве средства для реализации дополнительной сквозной функциональности или поведения.</span><span class="sxs-lookup"><span data-stu-id="72332-260">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="72332-261">Медиатор — это объект, который инкапсулирует методы выполнения этого процесса: он координирует выполнение на основе состояния, способы вызова обработчика команд и полезные данные, предоставляемые ему.</span><span class="sxs-lookup"><span data-stu-id="72332-261">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="72332-262">С помощью медиатора вы можете применять сквозную функциональность централизованным и прозрачным образом, применяя декораторы (или [расширения функциональности конвейера](https://github.com/jbogard/MediatR/wiki/Behaviors) начиная с [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)).</span><span class="sxs-lookup"><span data-stu-id="72332-262">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0)).</span></span> <span data-ttu-id="72332-263">Дополнительную информацию см. в статье [Шаблон декоратора](https://en.wikipedia.org/wiki/Decorator_pattern).</span><span class="sxs-lookup"><span data-stu-id="72332-263">For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).</span></span>

<span data-ttu-id="72332-264">Декораторы и расширения функциональности похожи на [аспектно-ориентированное программирование (АОП)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), но применяются к определенному конвейеру обработки, управляемому медиатором.</span><span class="sxs-lookup"><span data-stu-id="72332-264">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="72332-265">Аспекты в АОП, которые реализуют сквозную функциональность, применяются на основе *средств внедрения аспектов*, внедряемых во время компиляции или с помощью перехвата вызовов объектов.</span><span class="sxs-lookup"><span data-stu-id="72332-265">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="72332-266">Иногда говорят, что оба подхода АОП работают "волшебным образом", так как их применение трудно проследить.</span><span class="sxs-lookup"><span data-stu-id="72332-266">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="72332-267">В случае серьезных проблем или ошибок отладка в АОП может вызывать трудности.</span><span class="sxs-lookup"><span data-stu-id="72332-267">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="72332-268">С другой стороны, эти декораторы и расширения функциональности являются явными и применяются только в контексте медиатора, поэтому отладка является гораздо более предсказуемой и легкой.</span><span class="sxs-lookup"><span data-stu-id="72332-268">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="72332-269">Например, в микрослужбе размещения заказов eShopOnContainers реализованы два образца расширений функциональности: класс [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) и класс [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs).</span><span class="sxs-lookup"><span data-stu-id="72332-269">For example, in the eShopOnContainers ordering microservice, we implemented two sample behaviors, a [LogBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class and a [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class.</span></span> <span data-ttu-id="72332-270">Реализация расширений функциональности рассмотрена в следующем разделе. В нем показано, как в eShopOnContainers реализованы [расширения функциональности](https://github.com/jbogard/MediatR/wiki/Behaviors) [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0).</span><span class="sxs-lookup"><span data-stu-id="72332-270">The implementation of the behaviors is explained in the next section by showing how eShopOnContainers implements [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors).</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="72332-271">Использование очередей сообщений (внепроцессных) в конвейере команд</span><span class="sxs-lookup"><span data-stu-id="72332-271">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="72332-272">Еще один вариант — это использование асинхронных сообщений на основе брокеров или очередей сообщений, как показано на рисунке 9-26.</span><span class="sxs-lookup"><span data-stu-id="72332-272">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-26.</span></span> <span data-ttu-id="72332-273">Его можно использовать в сочетании с компонентом медиатора непосредственно перед обработчиком команд.</span><span class="sxs-lookup"><span data-stu-id="72332-273">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="72332-274">**Рис. 9-26**.</span><span class="sxs-lookup"><span data-stu-id="72332-274">**Figure 9-26**.</span></span> <span data-ttu-id="72332-275">Использование очередей сообщений (внепроцессное и внутрипроцессное взаимодействие) с командами CQRS</span><span class="sxs-lookup"><span data-stu-id="72332-275">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="72332-276">Использование очередей сообщений для принятия команд может еще более усложнить конвейер команд, так как вам может потребоваться разделить его на два процесса, связанных посредством внешней очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="72332-276">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="72332-277">Однако его следует использовать, если вам нужно повысить масштабируемость и производительность с помощью асинхронных сообщений.</span><span class="sxs-lookup"><span data-stu-id="72332-277">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="72332-278">Представьте, что в ситуации, продемонстрированной на рисунке 9-26, контроллер просто отправляет сообщение команды в очередь и возвращает управление.</span><span class="sxs-lookup"><span data-stu-id="72332-278">Consider that in the case of Figure 9-26, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="72332-279">В этом случае обработчики команд обрабатывают сообщения в удобном для себя темпе.</span><span class="sxs-lookup"><span data-stu-id="72332-279">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="72332-280">Это важное преимущество очередей: очередь сообщений может служить буфером в случае, когда требуется высочайшая масштабируемость, например в сценариях с большим объемом входящих данных.</span><span class="sxs-lookup"><span data-stu-id="72332-280">That is a great benefit of queues: the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="72332-281">Однако из-за асинхронного характера очередей сообщений необходимо продумать способ, который позволит сообщать клиентскому приложению об успешном или неудачном выполнении процесса команды.</span><span class="sxs-lookup"><span data-stu-id="72332-281">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="72332-282">Как правило, не следует использовать команды, выполняющиеся в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="72332-282">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="72332-283">Каждому бизнес-приложению требуется знать, была ли команда обработана успешно или по крайней мере была ли она проверена и принята.</span><span class="sxs-lookup"><span data-stu-id="72332-283">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="72332-284">Таки образом, возможность предоставления ответа клиенту после проверки сообщения команды, отправленного в асинхронную очередь, повышает сложность системы по сравнению с внутрипроцессной обработкой команды, при которой результат операции возвращается после выполнения транзакции.</span><span class="sxs-lookup"><span data-stu-id="72332-284">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="72332-285">При использовании очередей может требоваться возвращать результат обработки команды посредством других сообщений о результате операции, для чего в системе необходимы дополнительные компоненты и пользовательские сообщения.</span><span class="sxs-lookup"><span data-stu-id="72332-285">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="72332-286">Кроме того, асинхронные команды являются односторонними, что во многих случаях не требуется. Об этом говорят Алексей Бурцев (Burtsev Alexey) и Грег Янг (Greg Young) в этой интересной [беседе в Интернете](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="72332-286">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="72332-287">\[Алексей Бурцев\] Мне часто встречается код, в котором асинхронная обработка команд или односторонние сообщения команд используются без всякой причины (в нем не выполняются длительные операции или внешний асинхронный код; в нем даже не пересекаются границы приложения для использования шины сообщений).</span><span class="sxs-lookup"><span data-stu-id="72332-287">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="72332-288">Зачем это излишнее усложнение?</span><span class="sxs-lookup"><span data-stu-id="72332-288">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="72332-289">В действительности мне еще не встречался пример кода CQRS с блокирующими обработчиками команд, хотя в большинстве случаев они вполне применимы.</span><span class="sxs-lookup"><span data-stu-id="72332-289">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="72332-290">\[Грег Янг\] \[...\] асинхронных команд не существует; они по сути являются событиями.</span><span class="sxs-lookup"><span data-stu-id="72332-290">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="72332-291">Если я могу принять то, что вы мне отправили, и породить событие в случае несогласия, значит, вы уже не указываете, что мне нужно что-то сделать.</span><span class="sxs-lookup"><span data-stu-id="72332-291">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="72332-292">Вы сообщаете мне, что что-то было сделано.</span><span class="sxs-lookup"><span data-stu-id="72332-292">It's you telling me something has been done.</span></span> <span data-ttu-id="72332-293">Сначала разница кажется небольшой, но она имеет множество последствий.</span><span class="sxs-lookup"><span data-stu-id="72332-293">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="72332-294">Асинхронные команды значительно повышают сложность системы, так как нет простого способа сообщать о сбоях.</span><span class="sxs-lookup"><span data-stu-id="72332-294">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="72332-295">Поэтому асинхронные команды рекомендуются только при высоких требованиях к масштабируемости или в особых случаях, когда взаимодействие с внутренними микрослужбами осуществляется посредством сообщений.</span><span class="sxs-lookup"><span data-stu-id="72332-295">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="72332-296">В этих ситуациях необходимо спроектировать отдельную систему для информирования о сбоях и восстановления.</span><span class="sxs-lookup"><span data-stu-id="72332-296">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="72332-297">В первоначальной версии eShopOnContainers было решено использовать синхронную обработку команд, начиная с HTTP-запросов, на основе шаблона медиатора.</span><span class="sxs-lookup"><span data-stu-id="72332-297">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="72332-298">Это позволяет легко возвращать результат процесса (успех или неудача), как в реализации [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs).</span><span class="sxs-lookup"><span data-stu-id="72332-298">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="72332-299">В любом случае решение должно приниматься на основе бизнес-требований к приложению или микрослужбе.</span><span class="sxs-lookup"><span data-stu-id="72332-299">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="72332-300">Реализация конвейера обработки команд с помощью шаблона медиатора (MediatR)</span><span class="sxs-lookup"><span data-stu-id="72332-300">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="72332-301">В качестве примера реализации в этом руководстве используется внутрипроцессный конвейер на основе шаблона медиатора, обеспечивающий прием команд и их маршрутизацию в памяти в соответствующие обработчики команд.</span><span class="sxs-lookup"><span data-stu-id="72332-301">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and route commands, in memory, to the right command handlers.</span></span> <span data-ttu-id="72332-302">В руководстве также предлагается применять [расширения функциональности](https://github.com/jbogard/MediatR/wiki/Behaviors) для разделения сквозной функциональности.</span><span class="sxs-lookup"><span data-stu-id="72332-302">The guide also proposes applying [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="72332-303">Для реализации в .NET Core доступно множество библиотек с открытым кодом, которые реализуют шаблон медиатора.</span><span class="sxs-lookup"><span data-stu-id="72332-303">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="72332-304">В этом руководстве применяется библиотека [MediatR](https://github.com/jbogard/MediatR) с открытым кодом (созданная Джимми Богардом (Jimmy Bogard)), но можно выбрать и другой подход.</span><span class="sxs-lookup"><span data-stu-id="72332-304">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="72332-305">MediatR — это небольшая простая библиотека, которая позволяет обрабатывать сообщения в памяти как команды, применяя декораторы или расширения функциональности.</span><span class="sxs-lookup"><span data-stu-id="72332-305">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="72332-306">Использование шаблона медиатора помогает уменьшить количество связей и изолировать функциональность, связанную с запрашиваемой работой. При этом вы можете автоматически подключаться к обработчику, который выполняет эту работу — в данном случае к обработчику команд.</span><span class="sxs-lookup"><span data-stu-id="72332-306">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="72332-307">Еще одна причина для использования шаблона медиатора была раскрыта Джимми Богардом при рецензировании этого руководства:</span><span class="sxs-lookup"><span data-stu-id="72332-307">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="72332-308">"Я думаю, здесь стоит упомянуть тестирование — вы получаете ясное и согласованное представление о поведении системы".</span><span class="sxs-lookup"><span data-stu-id="72332-308">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="72332-309">Запрос поступает, ответ выдается — этот принцип оказался очень полезным при разработке согласованно работающих тестов.</span><span class="sxs-lookup"><span data-stu-id="72332-309">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="72332-310">Сначала рассмотрим пример контроллера WebAPI, в котором будет использоваться объект медиатора.</span><span class="sxs-lookup"><span data-stu-id="72332-310">First, let’s look at a sample WebAPI controller where you actually would use the mediator object.</span></span> <span data-ttu-id="72332-311">Если бы объект медиатора не применялся, потребовалось бы внедрить все зависимости для контроллера, такие как средство ведения журнала и другие.</span><span class="sxs-lookup"><span data-stu-id="72332-311">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="72332-312">Поэтому конструктор был бы весьма сложным.</span><span class="sxs-lookup"><span data-stu-id="72332-312">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="72332-313">Если же вы используете объект медиатора, конструктор контроллера может быть гораздо проще. Он может иметь всего лишь несколько зависимостей вместо множества, как в случае, когда для каждой сквозной операции имеется отдельная зависимость. Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72332-313">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class MyMicroserviceController : Controller
{
    public MyMicroserviceController(IMediator mediator, 
                                    IMyMicroserviceQueries microserviceQueries)
    // ...
```

<span data-ttu-id="72332-314">Как можно видеть, медиатор обеспечивает простой контроллер веб-интерфейса API, в котором нет ничего лишнего.</span><span class="sxs-lookup"><span data-stu-id="72332-314">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="72332-315">Кроме того, в методах контроллера код для отправки команды объекту медиатора ограничивается практически одной строкой:</span><span class="sxs-lookup"><span data-stu-id="72332-315">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

```csharp
[Route("new")]
[HttpPost] 
public async Task<IActionResult> ExecuteBusinessOperation([FromBody]RunOpCommand 
                                                               runOperationCommand) 
{
    var commandResult = await _mediator.SendAsync(runOperationCommand); 

    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

### <a name="implementing-idempotent-commands"></a><span data-ttu-id="72332-316">Реализация идемпотентных команд</span><span class="sxs-lookup"><span data-stu-id="72332-316">Implementing idempotent Commands</span></span>

<span data-ttu-id="72332-317">Более сложным примером по сравнению с приведенным выше в приложении eShopOnContainers является отправка объекта CreateOrderCommand из микрослужбы размещения заказов.</span><span class="sxs-lookup"><span data-stu-id="72332-317">In eShopOnContainers, a more advanced example than the above is submitting a CreateOrderCommand object from the Ordering microservice.</span></span> <span data-ttu-id="72332-318">Однако поскольку бизнес-процесс размещения заказов является немного более сложным и в данном случае он фактически начинается в микрослужбе Basket, действие отправки объекта CreateOrderCommand выполняется из обработчика событий интеграции с именем [UserCheckoutAcceptedIntegrationEvent.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs), а не из простого контроллера WebAPI, вызываемого из клиентского приложения, как в предыдущем более простом примере.</span><span class="sxs-lookup"><span data-stu-id="72332-318">But since the Ordering business process is a bit more complex and, in our case, it actually starts in the Basket microservice, this action of submitting the CreateOrderCommand object is performed from an integration-event handler named [UserCheckoutAcceptedIntegrationEvent.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) instead of a simple WebAPI controller called from the client App as in the previous simpler example.</span></span> 

<span data-ttu-id="72332-319">Тем не менее действие отправки команды в MediatR по многом схоже, как показано в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="72332-319">Nevertheless, the action of submitting the Command to MediatR is pretty similar, as shown in the following code.</span></span>

```csharp
var createOrderCommand = new CreateOrderCommand(eventMsg.Basket.Items,     
                                                eventMsg.UserId, eventMsg.City, 
                                                eventMsg.Street, eventMsg.State,
                                                eventMsg.Country, eventMsg.ZipCode,
                                                eventMsg.CardNumber, 
                                                eventMsg.CardHolderName, 
                                                eventMsg.CardExpiration,
                                                eventMsg.CardSecurityNumber,  
                                                eventMsg.CardTypeId);

var requestCreateOrder = new IdentifiedCommand<CreateOrderCommand,bool>(createOrderCommand, 
                                                                        eventMsg.RequestId);
result = await _mediator.Send(requestCreateOrder);
```

<span data-ttu-id="72332-320">Этот случай также немного сложнее, так как мы реализуем идемпотентные команды.</span><span class="sxs-lookup"><span data-stu-id="72332-320">However, this case is also a little bit more advanced because we’re also implementing idempotent commands.</span></span> <span data-ttu-id="72332-321">Процесс CreateOrderCommand должен быть идемпотентным, чтобы в случае повторной передачи по сети одного и того же сообщения по какой-либо причине, например из-за выполнения повторных попыток, заказ обрабатывался бы только один раз.</span><span class="sxs-lookup"><span data-stu-id="72332-321">The CreateOrderCommand process should be idempotent, so if the same message comes duplicated through the network, because of any reason, like retries, the same business order will be processed just once.</span></span>

<span data-ttu-id="72332-322">Для этого бизнес-команда (в данном случае CreateOrderCommand) упаковывается и внедряется в универсальный класс IdentifiedCommand, отслеживаемый по идентификатору каждого поступающего по сети сообщения, которое должно быть идемпотентным.</span><span class="sxs-lookup"><span data-stu-id="72332-322">This is implemented by wrapping the business command (in this case CreateOrderCommand) and embeding it into a generic IdentifiedCommand which is tracked by an ID of every message coming through the network that has to be idempotent.</span></span>

<span data-ttu-id="72332-323">В приведенном ниже коде видно, что IdentifiedCommand — это просто объект DTO с идентификатором и объектом упакованной бизнес-команды.</span><span class="sxs-lookup"><span data-stu-id="72332-323">In the code below, you can see that the IdentifiedCommand is nothing more than a DTO with and ID plus the wrapped business command object.</span></span>

```csharp
public class IdentifiedCommand<T, R> : IRequest<R>
    where T : IRequest<R>
{
    public T Command { get; }
    public Guid Id { get; }
    public IdentifiedCommand(T command, Guid id)
    {
        Command = command;
        Id = id;
    }
}
```

<span data-ttu-id="72332-324">Затем обработчик CommandHandler для IdentifiedCommand с именем [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) проверяет, имеется ли уже идентификатор, полученный в сообщении, в таблице.</span><span class="sxs-lookup"><span data-stu-id="72332-324">Then the CommandHandler for the IdentifiedCommand named [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs) will basically check if the ID coming as part of the message already exists in a table.</span></span> <span data-ttu-id="72332-325">Если он имеется, команда не будет обработана повторно, то есть она является идемпотентной.</span><span class="sxs-lookup"><span data-stu-id="72332-325">If it already exists, that command won’t be processed again, so it behaves as an idempotent command.</span></span> <span data-ttu-id="72332-326">Этот код инфраструктуры выполняется в результате вызова метода `_requestManager.ExistAsync`, приведенного ниже.</span><span class="sxs-lookup"><span data-stu-id="72332-326">That infrastructure code is performed by the `_requestManager.ExistAsync` method call below.</span></span>

```csharp
// IdentifiedCommandHandler.cs
public class IdentifiedCommandHandler<T, R> : 
                                   IAsyncRequestHandler<IdentifiedCommand<T, R>, R>
                                   where T : IRequest<R>
{
    private readonly IMediator _mediator;
    private readonly IRequestManager _requestManager;

    public IdentifiedCommandHandler(IMediator mediator, 
                                    IRequestManager requestManager)
    {
        _mediator = mediator;
        _requestManager = requestManager;
    }

    protected virtual R CreateResultForDuplicateRequest()
    {
        return default(R);
    }

    public async Task<R> Handle(IdentifiedCommand<T, R> message)
    {
        var alreadyExists = await _requestManager.ExistAsync(message.Id);
        if (alreadyExists)
        {
            return CreateResultForDuplicateRequest();
        }
        else
        {
            await _requestManager.CreateRequestForCommandAsync<T>(message.Id);

            // Send the embeded business command to mediator 
            // so it runs its related CommandHandler 
            var result = await _mediator.Send(message.Command);
                
            return result;
        }
    }
}
```

<span data-ttu-id="72332-327">Объект IdentifiedCommand выступает в роли конверта для бизнес-команды, поэтому когда бизнес-команда должна быть обработана в случае, если идентификатор не повторяется, этот объект берет внутреннюю бизнес-команду и повторно передает ее в медиатор. Это продемонстрировано в последней части приведенного выше кода, в которой выполняется метод `_mediator.Send(message.Command)` из [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span><span class="sxs-lookup"><span data-stu-id="72332-327">Since the IdentifiedCommand acts like a business command’s envelope, when the business command needs to be processed because it is not a repeated Id, then it takes that inner business command and re-submits it to Mediator, as in the last part of the code shown above when running `_mediator.Send(message.Command)`, from the [IdentifiedCommandHandler.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Commands/IdentifiedCommandHandler.cs).</span></span>

<span data-ttu-id="72332-328">При этом выполняется связывание с обработчиком бизнес-команд и его запуск. В данном случае это обработчик CreateOrderCommandHandler, который выполняет транзакции в базе данных Ordering, как показано в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="72332-328">When doing that, it will link and run the business command handler, in this case, the CreateOrderCommandHandler which is running transactions against the Ordering database, as shown in the following code.</span></span>

```csharp
// CreateOrderCommandHandler.cs
public class CreateOrderCommandHandler
                                   : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;
    private readonly IIdentityService _identityService;
    private readonly IMediator _mediator;

    // Using DI to inject infrastructure persistence Repositories
    public CreateOrderCommandHandler(IMediator mediator, 
                                     IOrderRepository orderRepository, 
                                     IIdentityService identityService)
    {
        _orderRepository = orderRepository ?? 
                          throw new ArgumentNullException(nameof(orderRepository));
        _identityService = identityService ?? 
                          throw new ArgumentNullException(nameof(identityService));
        _mediator = mediator ?? 
                                 throw new ArgumentNullException(nameof(mediator));
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        // Add/Update the Buyer AggregateRoot
        var address = new Address(message.Street, message.City, message.State,
                                  message.Country, message.ZipCode);
        var order = new Order(message.UserId, address, message.CardTypeId,  
                              message.CardNumber, message.CardSecurityNumber, 
                              message.CardHolderName, message.CardExpiration);
            
        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                               item.Discount, item.PictureUrl, item.Units);
        }

        _orderRepository.Add(order);

        return await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
    }
}
```

### <a name="registering-the-types-used-by-mediatr"></a><span data-ttu-id="72332-329">Регистрация типов, используемых библиотекой MediatR</span><span class="sxs-lookup"><span data-stu-id="72332-329">Registering the types used by MediatR</span></span>

<span data-ttu-id="72332-330">Чтобы сообщить библиотеке MediatR об используемых классах обработчиков команд, необходимо зарегистрировать классы медиаторов и обработчиков команд в контейнере IoC.</span><span class="sxs-lookup"><span data-stu-id="72332-330">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="72332-331">По умолчанию библиотека MediatR использует Autofac в качестве контейнера IoC, но вы также можете использовать встроенный контейнер IoC в ASP.NET Core или любой другой контейнер, поддерживаемый MediatR.</span><span class="sxs-lookup"><span data-stu-id="72332-331">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="72332-332">В приведенном ниже коде показано, как зарегистрировать типы и команды Mediator при использовании модулей Autofac.</span><span class="sxs-lookup"><span data-stu-id="72332-332">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...
    }
}
```

<span data-ttu-id="72332-333">Именно в нем творится вся магия MediatR.</span><span class="sxs-lookup"><span data-stu-id="72332-333">This is where “the magic happens” with MediatR.</span></span> 

<span data-ttu-id="72332-334">Так как каждый обработчик команд реализует универсальный интерфейс IAsyncRequestHandler&lt;T&gt;, при регистрации сборок код регистрирует в RegisteredAssemblyTypes все типы, созданные как обработчики RequestHandler. При этом он связывает обработчики CommandHandler с командами посредством отношения, определенного в классе CommandHandler, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72332-334">Because each command handler implements the generic IAsyncRequestHandler&lt;T&gt; interface, when registering the assemblies, the code registers with RegisteredAssemblyTypes all the types maked as RequestHandlers while relating the CommandHandlers with their Commands, thanks to the relationship stated at the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="72332-335">Этот код сопоставляет команды с обработчиками команд.</span><span class="sxs-lookup"><span data-stu-id="72332-335">That is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="72332-336">Обработчик представляет собой простой класс, но он наследуется от RequestHandler&lt;T&gt;, и библиотека MediatR обеспечивает его вызов с надлежащими полезными данными.</span><span class="sxs-lookup"><span data-stu-id="72332-336">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it is invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-behaviors-in-meadiatr"></a><span data-ttu-id="72332-337">Применение сквозной функциональности при обработке команд с помощью расширений функциональности в MeadiatR</span><span class="sxs-lookup"><span data-stu-id="72332-337">Applying cross-cutting concerns when processing commands with the Behaviors in MeadiatR</span></span>

<span data-ttu-id="72332-338">Есть еще одна возможность: применение сквозной функциональности к конвейеру медиатора.</span><span class="sxs-lookup"><span data-stu-id="72332-338">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="72332-339">В конце кода модуля регистрации Autofac можно заметить, что он регистрирует тип расширения функциональности, а именно: пользовательский класс LoggingBehavior и класс ValidatorBehavior.</span><span class="sxs-lookup"><span data-stu-id="72332-339">You can also see at the end of the Autofac registration module code how it registers a behavior type, specifically, a custom LoggingBehavior class and a ValidatorBehavior class.</span></span> <span data-ttu-id="72332-340">Вы также можете добавить другие пользовательские расширения функциональности.</span><span class="sxs-lookup"><span data-stu-id="72332-340">But you could add other custom behaviours, too.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();

        // Register all the Command classes (they implement IAsyncRequestHandler)
        // in assembly holding the Commands
        builder.RegisterAssemblyTypes(
                              typeof(CreateOrderCommand).GetTypeInfo().Assembly).
                                   AsClosedTypesOf(typeof(IAsyncRequestHandler<,>));
        // Other types registration
        //...        
        builder.RegisterGeneric(typeof(LoggingBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
        builder.RegisterGeneric(typeof(ValidatorBehavior<,>)).
                                                   As(typeof(IPipelineBehavior<,>));
    }
}
```

<span data-ttu-id="72332-341">Класс [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) может быть реализован в виде приведенного ниже кода, который записывает в журнал сведения о выполняемом обработчике команд и результате его выполнения (успех или неудача).</span><span class="sxs-lookup"><span data-stu-id="72332-341">That [LoggingBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/LoggingBehavior.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

```csharp
public class LoggingBehavior<TRequest, TResponse> 
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly ILogger<LoggingBehavior<TRequest, TResponse>> _logger;
    public LoggingBehavior(ILogger<LoggingBehavior<TRequest, TResponse>> logger) =>
                                                                  _logger = logger;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        _logger.LogInformation($"Handling {typeof(TRequest).Name}");
        var response = await next();
        _logger.LogInformation($"Handled {typeof(TResponse).Name}");
        return response;
    }
}
```

<span data-ttu-id="72332-342">Если реализовать этот класс декоратора и применить его к конвейеру, в журнал будут записываться сведения о выполнении всех команд, обрабатываемых посредством MediatR.</span><span class="sxs-lookup"><span data-stu-id="72332-342">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="72332-343">В микрослужбе размещения заказов eShopOnContainers применяется еще одно расширение функциональности для проведения базовых проверок. Это класс [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs), основанный на библиотеке [FluentValidation](https://github.com/JeremySkinner/FluentValidation) и показанный в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="72332-343">The eShopOnContainers ordering microservice also applies a second behavior for basic validations, the [ValidatorBehavior](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.API/Application/Behaviors/ValidatorBehavior.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

```csharp
public class ValidatorDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly IValidator<TRequest>[] _validators;

    public ValidatorDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        IValidator<TRequest>[] validators)
    {
        _inner = inner;
        _validators = validators;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        var failures = _validators
            .Select(v => v.Validate(message))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();
            if (failures.Any())
            {
                throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                new ValidationException("Validation exception", failures));
            }
            var response = await _inner.Handle(message);
        return response;
    }
}
```

<span data-ttu-id="72332-344">Затем на основе [FluentValidation](https://github.com/JeremySkinner/FluentValidation) была реализована проверка данных, передаваемых с помощью команды CreateOrderCommand, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="72332-344">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

```csharp
public class ValidatorBehavior<TRequest, TResponse> 
         : IPipelineBehavior<TRequest, TResponse>
{
    private readonly IValidator<TRequest>[] _validators;
    public ValidatorBehavior(IValidator<TRequest>[] validators) =>
                                                         _validators = validators;

    public async Task<TResponse> Handle(TRequest request,
                                        RequestHandlerDelegate<TResponse> next)
    {
        var failures = _validators
            .Select(v => v.Validate(request))
            .SelectMany(result => result.Errors)
            .Where(error => error != null)
            .ToList();

        if (failures.Any())
        {
            throw new OrderingDomainException(
                $"Command Validation Errors for type {typeof(TRequest).Name}",
                        new ValidationException("Validation exception", failures));
        }

        var response = await next();
        return response;
    }
}
```

<span data-ttu-id="72332-345">Затем на основе FluentValidation была реализована проверка данных, передаваемых с помощью команды CreateOrderCommand, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="72332-345">Then, based on the FluentValidation library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

```csharp
public class CreateOrderCommandValidator : AbstractValidator<CreateOrderCommand>
{
    public CreateOrderCommandValidator()
    {
        RuleFor(command => command.City).NotEmpty();
        RuleFor(command => command.Street).NotEmpty();
        RuleFor(command => command.State).NotEmpty();
        RuleFor(command => command.Country).NotEmpty();
        RuleFor(command => command.ZipCode).NotEmpty();
        RuleFor(command => command.CardNumber).NotEmpty().Length(12, 19); 
        RuleFor(command => command.CardHolderName).NotEmpty();
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).WithMessage("Please specify a valid card expiration date"); 
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3); 
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).Must(ContainOrderItems).WithMessage("No order items found"); 
    }

    private bool BeValidExpirationDate(DateTime dateTime)
    {
        return dateTime >= DateTime.UtcNow;
    }

    private bool ContainOrderItems(IEnumerable<OrderItemDTO> orderItems)
    {
        return orderItems.Any();
    }
}

```

<span data-ttu-id="72332-346">Можно создать дополнительные проверки.</span><span class="sxs-lookup"><span data-stu-id="72332-346">You could create additional validations.</span></span> <span data-ttu-id="72332-347">Это очень простой и изящный способ реализации проверок команд.</span><span class="sxs-lookup"><span data-stu-id="72332-347">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="72332-348">Аналогичным образом можно реализовать дополнительные расширения функциональности для других аспектов или сквозной функциональности, которые требуется применять к командам во время их обработки.</span><span class="sxs-lookup"><span data-stu-id="72332-348">In a similar way, you could implement other behaviors for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="72332-349">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72332-349">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="72332-350">Шаблон медиатора</span><span class="sxs-lookup"><span data-stu-id="72332-350">The mediator pattern</span></span>

-   <span data-ttu-id="72332-351">**Шаблон медиатора**
    [*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="72332-351">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="72332-352">Шаблон декоратора</span><span class="sxs-lookup"><span data-stu-id="72332-352">The decorator pattern</span></span>

-   <span data-ttu-id="72332-353">**Шаблон декоратора**
    [*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="72332-353">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="72332-354">MediatR (Джимми Богард (Jimmy Bogard))</span><span class="sxs-lookup"><span data-stu-id="72332-354">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="72332-355">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="72332-355">**MediatR.**</span></span> <span data-ttu-id="72332-356">Репозиторий GitHub.</span><span class="sxs-lookup"><span data-stu-id="72332-356">GitHub repo.</span></span>
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="72332-357">**CQRS с MediatR и AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="72332-357">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="72332-358">**Сажаем контроллеры на диету: запросы POST и команды.**
    [*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="72332-358">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="72332-359">**Обеспечение сквозной функциональности с помощью конвейера медиатора**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="72332-359">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="72332-360">**CQRS и REST: идеальная пара**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="72332-360">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="72332-361">**Примеры конвейера MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="72332-361">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="72332-362">**Средства тестирования вертикальных срезов для MediatR и ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span><span class="sxs-lookup"><span data-stu-id="72332-362">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="72332-363">**Объявление о выпуске расширений MediatR для внедрения зависимостей Майкрософт**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="72332-363">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="72332-364">Плавная проверка</span><span class="sxs-lookup"><span data-stu-id="72332-364">Fluent validation</span></span>

-   <span data-ttu-id="72332-365">**Джереми Скиннер (Jeremy Skinner). FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="72332-365">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="72332-366">Репозиторий GitHub.</span><span class="sxs-lookup"><span data-stu-id="72332-366">GitHub repo.</span></span>
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="72332-367">[Назад] (microservice-application-layer-web-api-design.md) [Далее] (../implement-resilient-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="72332-367">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
