---
title: "Реализации микрослужбу уровня приложения, с помощью веб-API"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализации микрослужбу уровня приложения, с помощью веб-API"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: d505a2561ae9b8dee05e803fd639387b63b28b70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a><span data-ttu-id="ef74e-104">Реализации микрослужбу уровня приложения, с помощью веб-API</span><span class="sxs-lookup"><span data-stu-id="ef74e-104">Implementing the microservice application layer using the Web API</span></span>

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a><span data-ttu-id="ef74e-105">С помощью внедрения зависимости для вставки объектов инфраструктуры на уровне приложений</span><span class="sxs-lookup"><span data-stu-id="ef74e-105">Using Dependency Injection to inject infrastructure objects into your application layer</span></span>

<span data-ttu-id="ef74e-106">Как упоминалось ранее, уровень приложения может осуществляться в рамках артефакта, создании, таких как в проект веб-API или проект веб-приложения MVC.</span><span class="sxs-lookup"><span data-stu-id="ef74e-106">As mentioned previously, the application layer can be implemented as part of the artifact you are building, such as within a Web API project or an MVC web app project.</span></span> <span data-ttu-id="ef74e-107">В случае микрослужбу, созданного с помощью ASP.NET Core уровень приложения обычно будет библиотеки веб-API.</span><span class="sxs-lookup"><span data-stu-id="ef74e-107">In the case of a microservice built with ASP.NET Core, the application layer will usually be your Web API library.</span></span> <span data-ttu-id="ef74e-108">Если необходимо разделить предстоящие из ASP.NET Core (свою инфраструктуру, а также контроллеров) из пользовательского приложения слой кода, можно также поместить на уровне приложения в отдельной библиотеке классов, но это необязательно.</span><span class="sxs-lookup"><span data-stu-id="ef74e-108">If you want to separate what is coming from ASP.NET Core (its infrastructure plus your controllers) from your custom application layer code, you could also place your application layer in a separate class library, but that is optional.</span></span>

<span data-ttu-id="ef74e-109">Для экземпляра код уровня приложения для упорядочивания микрослужбу непосредственно реализуется как часть **Ordering.API** проект (проект веб-API ASP.NET Core), как показано на рисунке 9-19.</span><span class="sxs-lookup"><span data-stu-id="ef74e-109">For instance, the application layer code of the ordering microservice is directly implemented as part of the **Ordering.API** project (an ASP.NET Core Web API project), as shown in Figure 9-19.</span></span>

![](./media/image20.png)

<span data-ttu-id="ef74e-110">**На рисунке 9-19**.</span><span class="sxs-lookup"><span data-stu-id="ef74e-110">**Figure 9-19**.</span></span> <span data-ttu-id="ef74e-111">Уровень приложения в проекте веб-API Ordering.API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef74e-111">The application layer in the Ordering.API ASP.NET Core Web API project</span></span>

<span data-ttu-id="ef74e-112">ASP.NET Core включает в себя простую [встроенные контейнер IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (представленное интерфейс IServiceProvider), поддерживающем внедрение конструктора по умолчанию и ASP.NET можно использовать посредством DI определенных служб.</span><span class="sxs-lookup"><span data-stu-id="ef74e-112">ASP.NET Core includes a simple [built-in IoC container](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (represented by the IServiceProvider interface) that supports constructor injection by default, and ASP.NET makes certain services available through DI.</span></span> <span data-ttu-id="ef74e-113">ASP.NET Core используется термин *службы* для любых типов, регистрации, которые будут внесены через DI.</span><span class="sxs-lookup"><span data-stu-id="ef74e-113">ASP.NET Core uses the term *service* for any of the types you register that will be injected through DI.</span></span> <span data-ttu-id="ef74e-114">Необходимо настроить службы встроенного контейнера ConfigureServices метода в класс запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-114">You configure the built-in container's services in the ConfigureServices method in your application's Startup class.</span></span> <span data-ttu-id="ef74e-115">Зависимости будут реализованы в службы, которые требуется тип.</span><span class="sxs-lookup"><span data-stu-id="ef74e-115">Your dependencies are implemented in the services that a type needs.</span></span>

<span data-ttu-id="ef74e-116">Как правило требуется внедрения зависимостей, реализующих объектов инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="ef74e-116">Typically, you want to inject dependencies that implement infrastructure objects.</span></span> <span data-ttu-id="ef74e-117">Зависимость весьма типичен для вставки — это хранилище.</span><span class="sxs-lookup"><span data-stu-id="ef74e-117">A very typical dependency to inject is a repository.</span></span> <span data-ttu-id="ef74e-118">Однако может запустить другой инфраструктуры зависимости, то, возможно.</span><span class="sxs-lookup"><span data-stu-id="ef74e-118">But you could inject any other infrastructure dependency that you may have.</span></span> <span data-ttu-id="ef74e-119">Для простой реализации может напрямую внедрить объект шаблон единицы работы (объект EF DbContext), поскольку класс DBContext также является реализацией сохраняемости объектов вашей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="ef74e-119">For simpler implementations, you could directly inject your Unit of Work pattern object (the EF DbContext object), because the DBContext is also the implementation of your infrastructure persistence objects.</span></span>

<span data-ttu-id="ef74e-120">В следующем примере вы увидите, как .NET Core внедряет объектов требуется хранилище с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="ef74e-120">In the following example, you can see how .NET Core is injecting the required repository objects through the constructor.</span></span> <span data-ttu-id="ef74e-121">Класс представляет обработчик команд, в которой будут рассмотрены в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ef74e-121">The class is a command handler, which we will cover in the next section.</span></span>

```csharp
// Sample command handler
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IOrderRepository _orderRepository;

    // Constructor where Dependencies are injected
    public CreateOrderCommandHandler(IOrderRepository orderRepository)
    {
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // ... Additional code
        //
        // Create the Order AggregateRoot
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var address = new Address(message.Street, message.City, message.State,
            message.Country, message.ZipCode);
        var order = new Order(address, message.CardTypeId, message.CardNumber,
            message.CardSecurityNumber,
            message.CardHolderName,
            message.CardExpiration);

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        //Persist the Order through the Repository
        _orderRepository.Add(order);
        var result = await _orderRepository.UnitOfWork
            .SaveEntitiesAsync();
        return result > 0;
    }
}
```

<span data-ttu-id="ef74e-122">Этот класс использует подставляемого репозиториев для выполнения транзакции и сохранить изменения состояния.</span><span class="sxs-lookup"><span data-stu-id="ef74e-122">The class uses the injected repositories to execute the transaction and persist the state changes.</span></span> <span data-ttu-id="ef74e-123">Он не имеет значения, является ли этот класс является допустимым обработчиком команд, метод контроллера веб-API ASP.NET Core или [службы приложения DDD](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span><span class="sxs-lookup"><span data-stu-id="ef74e-123">It does not matter whether that class is a command handler, an ASP.NET Core Web API controller method, or a [DDD Application Service](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/).</span></span> <span data-ttu-id="ef74e-124">Он представляет собой простой класс, который использует репозиториев, домена сущностей и другие приложения координации аналогично обработчика команд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-124">It is ultimately a simple class that uses repositories, domain entities, and other application coordination in a fashion similar to a command handler.</span></span> <span data-ttu-id="ef74e-125">Работает внедрение зависимостей одинаково для всех упомянутых классов, как показано в примере с помощью DI на основании конструктор.</span><span class="sxs-lookup"><span data-stu-id="ef74e-125">Dependency Injection works the same way for all the mentioned classes, as in the example using DI based on the constructor.</span></span>

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a><span data-ttu-id="ef74e-126">Регистрация типов реализации зависимостей и интерфейсы или абстрактные классы</span><span class="sxs-lookup"><span data-stu-id="ef74e-126">Registering the dependency implementation types and interfaces or abstractions</span></span>

<span data-ttu-id="ef74e-127">Прежде чем использовать объекты, введенный через конструкторы, необходимо знать, где зарегистрировать интерфейсы и классы, создавать объекты, внедренные в ваши приложения классы через DI.</span><span class="sxs-lookup"><span data-stu-id="ef74e-127">Before you use the objects injected through constructors, you need to know where to register the interfaces and classes that produce the objects injected into your application classes through DI.</span></span> <span data-ttu-id="ef74e-128">(Подобно DI на основе конструктора, как показано выше.)</span><span class="sxs-lookup"><span data-stu-id="ef74e-128">(Like DI based on the constructor, as shown previously.)</span></span>

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a><span data-ttu-id="ef74e-129">С помощью встроенных контейнер IoC, предоставляемый ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ef74e-129">Using the built-in IoC container provided by ASP.NET Core</span></span>

<span data-ttu-id="ef74e-130">При использовании встроенных контейнер IoC, предоставляемый ASP.NET Core, можно зарегистрировать типы, которые нужно внедрить в методе ConfigureServices в файле Startup.cs файла, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="ef74e-130">When you use the built-in IoC container provided by ASP.NET Core, you register the types you want to inject in the ConfigureServices method in the Startup.cs file, as in the following code:</span></span>

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

<span data-ttu-id="ef74e-131">Чаще всего встречается при регистрации типов в контейнер IoC является регистрация парой типов — интерфейс и его связанные реализацию класса.</span><span class="sxs-lookup"><span data-stu-id="ef74e-131">The most common pattern when registering types in an IoC container is to register a pair of types—an interface and its related implementation class.</span></span> <span data-ttu-id="ef74e-132">Затем при запросе объекта контейнер IoC через любой конструктор запроса объекта определенного типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ef74e-132">Then when you request an object from the IoC container through any constructor, you request an object of a certain type of interface.</span></span> <span data-ttu-id="ef74e-133">Например в предыдущем примере последней строки состояния, если любой из конструкторах с зависимостями от IMyCustomRepository (интерфейс или абстракции) контейнер IoC добавит экземпляр реализации MyCustomSQLServerRepository класс.</span><span class="sxs-lookup"><span data-stu-id="ef74e-133">For instance, in the previous example, the last line states that when any of your constructors have a dependency on IMyCustomRepository (interface or abstraction), the IoC container will inject an instance of the MyCustomSQLServerRepository implementation class.</span></span>

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a><span data-ttu-id="ef74e-134">С помощью библиотеки Scrutor для типов автоматической регистрации</span><span class="sxs-lookup"><span data-stu-id="ef74e-134">Using the Scrutor library for automatic types registration</span></span>

<span data-ttu-id="ef74e-135">При использовании DI в .NET Core, можно иметь возможность проверять сборки и автоматически зарегистрировала свои типы по соглашению.</span><span class="sxs-lookup"><span data-stu-id="ef74e-135">When using DI in .NET Core, you might want to be able to scan an assembly and automatically register its types by convention.</span></span> <span data-ttu-id="ef74e-136">Этот компонент недоступен в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef74e-136">This feature is not currently available in ASP.NET Core.</span></span> <span data-ttu-id="ef74e-137">Тем не менее, можно использовать [Scrutor](https://github.com/khellang/Scrutor) библиотеки для этого.</span><span class="sxs-lookup"><span data-stu-id="ef74e-137">However, you can use the [Scrutor](https://github.com/khellang/Scrutor) library for that.</span></span> <span data-ttu-id="ef74e-138">Такой подход удобен при наличии десятков типов, которые должны быть зарегистрированы в контейнер IoC.</span><span class="sxs-lookup"><span data-stu-id="ef74e-138">This approach is convenient when you have dozens of types that need to be registered in your IoC container.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="ef74e-139">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ef74e-139">Additional resources</span></span>

-   <span data-ttu-id="ef74e-140">**Мэтью Кинг. Регистрация служб с Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span><span class="sxs-lookup"><span data-stu-id="ef74e-140">**Matthew King. Registering services with Scrutor**
[*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)</span></span>

<!-- -->

-   <span data-ttu-id="ef74e-141">**Кристиан Hellang. Scrutor.**</span><span class="sxs-lookup"><span data-stu-id="ef74e-141">**Kristian Hellang. Scrutor.**</span></span> <span data-ttu-id="ef74e-142">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="ef74e-142">GitHub repo.</span></span>
    [<span data-ttu-id="ef74e-143">*https://github.com/khellang/Scrutor*</span><span class="sxs-lookup"><span data-stu-id="ef74e-143">*https://github.com/khellang/Scrutor*</span></span>](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a><span data-ttu-id="ef74e-144">С помощью Autofac как контейнер IoC</span><span class="sxs-lookup"><span data-stu-id="ef74e-144">Using Autofac as an IoC container</span></span>

<span data-ttu-id="ef74e-145">Можно также использовать дополнительные контейнеры IoC и подключите их к конвейеру ASP.NET Core, как и порядка сортировки микрослужбу в eShopOnContainers, который использует [Autofac](https://autofac.org/).</span><span class="sxs-lookup"><span data-stu-id="ef74e-145">You can also use additional IoC containers and plug them into the ASP.NET Core pipeline, as in the ordering microservice in eShopOnContainers, which uses [Autofac](https://autofac.org/).</span></span> <span data-ttu-id="ef74e-146">При использовании Autofac обычно регистрации типов через модули, которые позволяют разделить типы регистрации между несколькими файлами в зависимости от расположения к типам, так же, как можно создать типы приложений, распределенные по нескольким библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="ef74e-146">When using Autofac you typically register the types via modules, which allow you to split the registration types between multiple files depending on where your types are, just as you could have the application types distributed across multiple class libraries.</span></span>

<span data-ttu-id="ef74e-147">Например, ниже приведен [модуль приложения Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) для [Ordering.API веб-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) проекта с типами, которые требуется вставить.</span><span class="sxs-lookup"><span data-stu-id="ef74e-147">For example, the following is the [Autofac application module](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) for the [Ordering.API Web API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) project with the types you will want to inject.</span></span>

```csharp
public class ApplicationModule
    :Autofac.Module
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

<span data-ttu-id="ef74e-148">Процесс регистрации и основные понятия очень аналогично тому, как можно зарегистрировать типы с помощью встроенных контейнера iOS ASP.NET Core, но синтаксис при использовании Autofac немного отличается.</span><span class="sxs-lookup"><span data-stu-id="ef74e-148">The registration process and concepts are very similar to the way you can register types with the built-in ASP.NET Core iOS container, but the syntax when using Autofac is a bit different.</span></span>

<span data-ttu-id="ef74e-149">В примере кода абстракции IOrderRepository регистрируется вместе с реализацией класса OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="ef74e-149">In the example code, the abstraction IOrderRepository is registered along with the implementation class OrderRepository.</span></span> <span data-ttu-id="ef74e-150">Это означает, что каждый раз, когда зависимостей через абстракции IOrderRepository или интерфейс объявляет конструктор, контейнер IoC добавит экземпляр класса OrderRepository.</span><span class="sxs-lookup"><span data-stu-id="ef74e-150">This means that whenever a constructor is declaring a dependency through the IOrderRepository abstraction or interface, the IoC container will inject an instance of the OrderRepository class.</span></span>

<span data-ttu-id="ef74e-151">Тип области экземпляр определяет, как экземпляр совместно запросов для той же службы или зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ef74e-151">The instance scope type determines how an instance is shared between requests for the same service or dependency.</span></span> <span data-ttu-id="ef74e-152">При обращении к зависимости контейнер IoC может вернуть следующее:</span><span class="sxs-lookup"><span data-stu-id="ef74e-152">When a request is made for a dependency, the IoC container can return the following:</span></span>

-   <span data-ttu-id="ef74e-153">Один экземпляр на время существования области (в контейнер ASP.NET Core IoC как называется *область*).</span><span class="sxs-lookup"><span data-stu-id="ef74e-153">A single instance per lifetime scope (referred to in the ASP.NET Core IoC container as *scoped*).</span></span>

-   <span data-ttu-id="ef74e-154">Новый экземпляр каждого зависимостей (в контейнер ASP.NET Core IoC как называется *временных*).</span><span class="sxs-lookup"><span data-stu-id="ef74e-154">A new instance per dependency (referred to in the ASP.NET Core IoC container as *transient*).</span></span>

-   <span data-ttu-id="ef74e-155">Один экземпляр, общими для всех объектов, используя контейнер IoC (Далее в контейнер ASP.NET Core IoC как *одноэлементный*).</span><span class="sxs-lookup"><span data-stu-id="ef74e-155">A single instance shared across all objects using the IoC container (referred to in the ASP.NET Core IoC container as *singleton*).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="ef74e-156">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ef74e-156">Additional resources</span></span>

-   <span data-ttu-id="ef74e-157">**Общие сведения о внедрение зависимостей в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span><span class="sxs-lookup"><span data-stu-id="ef74e-157">**Introduction to Dependency Injection in ASP.NET Core**
[*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)</span></span>

-   <span data-ttu-id="ef74e-158">**Autofac.**</span><span class="sxs-lookup"><span data-stu-id="ef74e-158">**Autofac.**</span></span> <span data-ttu-id="ef74e-159">Официальной документации.</span><span class="sxs-lookup"><span data-stu-id="ef74e-159">Official documentation.</span></span>
    [<span data-ttu-id="ef74e-160">*http://docs.autofac.org/en/Latest/*</span><span class="sxs-lookup"><span data-stu-id="ef74e-160">*http://docs.autofac.org/en/latest/*</span></span>](http://docs.autofac.org/en/latest/)

-   <span data-ttu-id="ef74e-161">**Сезар де ла Торре (Cesar de la Torre). Сравнение времени существования службы контейнер ASP.NET Core IoC с областями экземпляр контейнер Autofac IoC**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-161">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="implementing-the-command-and-command-handler-patterns"></a><span data-ttu-id="ef74e-162">Реализация шаблонов команда и обработчика команд</span><span class="sxs-lookup"><span data-stu-id="ef74e-162">Implementing the Command and Command Handler patterns</span></span>

<span data-ttu-id="ef74e-163">В примере DI через конструктор, показанном в предыдущем разделе контейнер IoC был вводится репозиториев через конструктор в классе.</span><span class="sxs-lookup"><span data-stu-id="ef74e-163">In the DI-through-constructor example shown in the previous section, the IoC container was injecting repositories through a constructor in a class.</span></span> <span data-ttu-id="ef74e-164">Но точно где были они внедрены?</span><span class="sxs-lookup"><span data-stu-id="ef74e-164">But exactly where were they injected?</span></span> <span data-ttu-id="ef74e-165">В простой веб-API (например, каталог микрослужбу в eShopOnContainers) запустить их на уровне контроллеров MVC в конструкторе контроллера.</span><span class="sxs-lookup"><span data-stu-id="ef74e-165">In a simple Web API (for example, the catalog microservice in eShopOnContainers), you inject them at the MVC controllers level, in a controller constructor.</span></span> <span data-ttu-id="ef74e-166">Однако в исходный код в этом разделе ( [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) класса из службы Ordering.API в eShopOnContainers), внедрение зависимостей выполняется с помощью конструктора определенной команды обработчик.</span><span class="sxs-lookup"><span data-stu-id="ef74e-166">However, in the initial code of this section (the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) class from the Ordering.API service in eShopOnContainers), the injection of dependencies is done through the constructor of a particular command handler.</span></span> <span data-ttu-id="ef74e-167">Сообщите нам объяснить является команда обработчик и зачем вам нужно использовать.</span><span class="sxs-lookup"><span data-stu-id="ef74e-167">Let us explain what a command handler is and why you would want to use it.</span></span>

<span data-ttu-id="ef74e-168">По своей природе команд связана с CQRS шаблон, который был введен ранее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="ef74e-168">The Command pattern is intrinsically related to the CQRS pattern that was introduced earlier in this guide.</span></span> <span data-ttu-id="ef74e-169">CQRS есть две стороны.</span><span class="sxs-lookup"><span data-stu-id="ef74e-169">CQRS has two sides.</span></span> <span data-ttu-id="ef74e-170">Первая область-запросы, с помощью упрощенного запросы с [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, который был описан ранее.</span><span class="sxs-lookup"><span data-stu-id="ef74e-170">The first area is queries, using simplified queries with the [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, which was explained previously.</span></span> <span data-ttu-id="ef74e-171">Вторая область-команд, которые являются отправной точкой для операций и входной канал из вне этой службы.</span><span class="sxs-lookup"><span data-stu-id="ef74e-171">The second area is commands, which are the starting point for transactions, and the input channel from outside the service.</span></span>

<span data-ttu-id="ef74e-172">Как показано на рисунке 9-20, шаблон основан на прием команд на стороне клиента, обработки их на основе модели правил домена и наконец сохранение состояния с транзакциями.</span><span class="sxs-lookup"><span data-stu-id="ef74e-172">As shown in Figure 9-20, the pattern is based on accepting commands from the client side, processing them based on the domain model rules, and finally persisting the states with transactions.</span></span>

![](./media/image21.png)

<span data-ttu-id="ef74e-173">**Рис. 9-20**.</span><span class="sxs-lookup"><span data-stu-id="ef74e-173">**Figure 9-20**.</span></span> <span data-ttu-id="ef74e-174">Высокоуровневое представление команд или «транзакций стороны» в шаблоне CQRS</span><span class="sxs-lookup"><span data-stu-id="ef74e-174">High-level view of the commands or “transactional side” in a CQRS pattern</span></span>

### <a name="the-command-class"></a><span data-ttu-id="ef74e-175">Класс команд</span><span class="sxs-lookup"><span data-stu-id="ef74e-175">The command class</span></span>

<span data-ttu-id="ef74e-176">Команда — это запрос, чтобы выполнить действие, которое изменяет состояние системы система.</span><span class="sxs-lookup"><span data-stu-id="ef74e-176">A command is a request for the system to perform an action that changes the state of the system.</span></span> <span data-ttu-id="ef74e-177">Команды императивный и будут обрабатываться только один раз.</span><span class="sxs-lookup"><span data-stu-id="ef74e-177">Commands are imperative, and should be processed just once.</span></span>

<span data-ttu-id="ef74e-178">Поскольку команды условиям, обычно именуются с помощью команды в императивном модальности (например, «создание» или «update»), и они могут включать агрегатного типа, например CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="ef74e-178">Since commands are imperatives, they are typically named with a verb in the imperative mood (for example, "create" or "update"), and they might include the aggregate type, such as CreateOrderCommand.</span></span> <span data-ttu-id="ef74e-179">В отличие от события команда не факт в прошлом; он представляет собой запрос и таким образом, может быть отклонено.</span><span class="sxs-lookup"><span data-stu-id="ef74e-179">Unlike an event, a command is not a fact from the past; it is only a request, and thus may be refused.</span></span>

<span data-ttu-id="ef74e-180">Команды могут быть получены из пользовательского интерфейса, в результате пользователь инициирует запрос или из диспетчера процессов при диспетчер процессов направляет статистическую функцию для выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="ef74e-180">Commands can originate from the UI as a result of a user initiating a request, or from a process manager when the process manager is directing an aggregate to perform an action.</span></span>

<span data-ttu-id="ef74e-181">Важной характеристикой команды — что он должен обрабатываться только один раз один получатель.</span><span class="sxs-lookup"><span data-stu-id="ef74e-181">An important characteristic of a command is that it should be processed just once by a single receiver.</span></span> <span data-ttu-id="ef74e-182">Это так, как команда — это единственное действие или транзакции, которую требуется выполнить в приложении.</span><span class="sxs-lookup"><span data-stu-id="ef74e-182">This is because a command is a single action or transaction you want to perform in the application.</span></span> <span data-ttu-id="ef74e-183">Например одной и той же команды создания заказа не должны обрабатываться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="ef74e-183">For example, the same order creation command should not be processed more than once.</span></span> <span data-ttu-id="ef74e-184">Это важное отличие между команды и события.</span><span class="sxs-lookup"><span data-stu-id="ef74e-184">This is an important difference between commands and events.</span></span> <span data-ttu-id="ef74e-185">События могут обрабатываться несколько раз, так как многие системы или микрослужбами могут быть заинтересованы в событии.</span><span class="sxs-lookup"><span data-stu-id="ef74e-185">Events may be processed multiple times, because many systems or microservices might be interested in the event.</span></span>

<span data-ttu-id="ef74e-186">Кроме того важно команду обработки только один раз в случае, если команда не является идемпотентными.</span><span class="sxs-lookup"><span data-stu-id="ef74e-186">In addition, it is important that a command be processed only once in case the command is not idempotent.</span></span> <span data-ttu-id="ef74e-187">Команда является идемпотентной, если он может выполняться несколько раз без изменения результатов, либо из-за характера команды, либо из-за того, система обрабатывает команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-187">A command is idempotent if it can be executed multiple times without changing the result, either because of the nature of the command, or because of the way the system handles the command.</span></span>

<span data-ttu-id="ef74e-188">Рекомендуется всегда команд и обновляет идемпотентными, когда это имеет смысл в области бизнес-правил для вашего домена и инварианты.</span><span class="sxs-lookup"><span data-stu-id="ef74e-188">It is a good practice to make your commands and updates idempotent when it makes sense under your domain’s business rules and invariants.</span></span> <span data-ttu-id="ef74e-189">Например использовать тот же пример, если для какой-либо причине (логику повторных попыток, взлому, т. д.) одной и той же команде CreateOrder достигает компьютер несколько раз, можно для идентификации и обеспечить не создания нескольких заказов.</span><span class="sxs-lookup"><span data-stu-id="ef74e-189">For instance, to use the same example, if for any reason (retry logic, hacking, etc.) the same CreateOrder command reaches your system multiple times, you should be able to identify it and ensure that you do not create multiple orders.</span></span> <span data-ttu-id="ef74e-190">Для этого необходимо присоединить какой-либо удостоверения в операциях и идентифицировать ли команда или обновления уже был обработан.</span><span class="sxs-lookup"><span data-stu-id="ef74e-190">To do so, you need to attach some kind of identity in the operations and identify whether the command or update was already processed.</span></span>

<span data-ttu-id="ef74e-191">Отправить команду к одному получателю; команда не будет опубликована.</span><span class="sxs-lookup"><span data-stu-id="ef74e-191">You send a command to a single receiver; you do not publish a command.</span></span> <span data-ttu-id="ef74e-192">Публикацию можно использовать для интеграции события с сообщением факт, что что-то произошло и может представлять интерес для приемников событий.</span><span class="sxs-lookup"><span data-stu-id="ef74e-192">Publishing is for integration events that state a fact—that something has happened and might be interesting for event receivers.</span></span> <span data-ttu-id="ef74e-193">В случае события у издателя есть никаких проблем, о которых получить приемники события и что они делают его.</span><span class="sxs-lookup"><span data-stu-id="ef74e-193">In the case of events, the publisher has no concerns about which receivers get the event or what they do it.</span></span> <span data-ttu-id="ef74e-194">Однако события интеграции другую статью, уже представленные в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="ef74e-194">But integration events are a different story already introduced in previous sections.</span></span>

<span data-ttu-id="ef74e-195">Команда реализуется с помощью класса, содержащего поля данных или коллекций, в которых все сведения, необходимые для выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-195">A command is implemented with a class that contains data fields or collections with all the information that is needed in order to execute that command.</span></span> <span data-ttu-id="ef74e-196">Команда — это особый тип объекта данных передачи объекта (DTO), который специально используется для запроса изменений или операции.</span><span class="sxs-lookup"><span data-stu-id="ef74e-196">A command is a special kind of Data Transfer Object (DTO), one that is specifically used to request changes or transactions.</span></span> <span data-ttu-id="ef74e-197">Саму команду основан на данные, необходимые для обработки команды и ничего более.</span><span class="sxs-lookup"><span data-stu-id="ef74e-197">The command itself is based on exactly the information that is needed for processing the command, and nothing more.</span></span>

<span data-ttu-id="ef74e-198">В примере показан упрощенный класс CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="ef74e-198">The following example shows the simplified CreateOrderCommand class.</span></span> <span data-ttu-id="ef74e-199">Это неизменяемый команды, используемой в упорядочивания микрослужбу в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="ef74e-199">This is an immutable command that is used in the ordering microservice in eShopOnContainers.</span></span>

```csharp
// DDD and CQRS patterns comment
// Note that it is recommended that yuo implement immutable commands
// In this case, immutability is achieved by having all the setters as private
// plus being able to update the data just once, when creating the object
// through the constructor.
// References on immutable commands:
// http://cqrs.nu/Faq
// https://docs.spine3.org/motivation/immutability.html
// http://blog.gauffin.org/2012/06/griffin-container-introducing-command-support/
// https://msdn.microsoft.com/en-us/library/bb383979.aspx
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

<span data-ttu-id="ef74e-200">По существу класс команд содержит все данные, необходимые для выполнения бизнес-транзакции с помощью объектов модели домена.</span><span class="sxs-lookup"><span data-stu-id="ef74e-200">Basically, the command class contains all the data you need for performing a business transaction by using the domain model objects.</span></span> <span data-ttu-id="ef74e-201">Таким образом команды, просто структур данных, содержащих данные только для чтения и нет поведения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-201">Thus, commands are simply data structures that contain read-only data, and no behavior.</span></span> <span data-ttu-id="ef74e-202">Указывает имя команды, его назначение.</span><span class="sxs-lookup"><span data-stu-id="ef74e-202">The command’s name indicates its purpose.</span></span> <span data-ttu-id="ef74e-203">Во многих языках, таких как C\#, команды отображаются в виде классов, но они не являются true классов в реальных объектно ориентированного смысла.</span><span class="sxs-lookup"><span data-stu-id="ef74e-203">In many languages like C\#, commands are represented as classes, but they are not true classes in the real object-oriented sense.</span></span>

<span data-ttu-id="ef74e-204">Как дополнительные характеристики команды являются неизменяемыми, так как они обрабатываются моделью домена ожидаемого режима использования.</span><span class="sxs-lookup"><span data-stu-id="ef74e-204">As an additional characteristic, commands are immutable, because the expected usage is that they are processed directly by the domain model.</span></span> <span data-ttu-id="ef74e-205">Они не должны измениться во время их предполагаемое время существования.</span><span class="sxs-lookup"><span data-stu-id="ef74e-205">They do not need to change during their projected lifetime.</span></span> <span data-ttu-id="ef74e-206">В языке C\# класса, неизменность достигается при этом не все задания или другие методы, изменяющие внутреннего состояния.</span><span class="sxs-lookup"><span data-stu-id="ef74e-206">In a C\# class, immutability can be achieved by not having any setters or other methods that change internal state.</span></span>

<span data-ttu-id="ef74e-207">Например класс команд для создания заказа аналогична, возможно, с точки зрения данных порядке, в котором вы хотите создать, но, возможно, не требуется те же атрибуты.</span><span class="sxs-lookup"><span data-stu-id="ef74e-207">For example, the command class for creating an order is probably similar in terms of data to the order you want to create, but you probably do not need the same attributes.</span></span> <span data-ttu-id="ef74e-208">Для экземпляра CreateOrderCommand имеет идентификатор заказа, так как порядок еще не создана.</span><span class="sxs-lookup"><span data-stu-id="ef74e-208">For instance, CreateOrderCommand does not have an order ID, because the order has not been created yet.</span></span>

<span data-ttu-id="ef74e-209">Многие классы команд могут быть простыми, требует лишь несколько полей о некоторое состояние, которое требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="ef74e-209">Many command classes can be simple, requiring only a few fields about some state that needs to be changed.</span></span> <span data-ttu-id="ef74e-210">Это было бы так при изменении состояния заказа из «выполнение» для только что «платная» или «отправить», используя команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="ef74e-210">That would be the case if you are just changing the status of an order from “in process” to “paid” or “shipped” by using a command similar to the following:</span></span>

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

<span data-ttu-id="ef74e-211">Некоторые разработчики их запроса объекты пользовательского интерфейса отдельно от их DTO команды, однако, является лишь предпочтения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-211">Some developers make their UI request objects separate from their command DTOs, but that is just a matter of preference.</span></span> <span data-ttu-id="ef74e-212">Она является трудоемкой разделение с не added объем работы и объекты имеют практически так же фигуры.</span><span class="sxs-lookup"><span data-stu-id="ef74e-212">It is a tedious separation with not much added value, and the objects are almost exactly the same shape.</span></span> <span data-ttu-id="ef74e-213">Например в eShopOnContainers, команды поступать непосредственно на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="ef74e-213">For instance, in eShopOnContainers, the commands come directly from the client side.</span></span>

### <a name="the-command-handler-class"></a><span data-ttu-id="ef74e-214">Класс обработчика команд</span><span class="sxs-lookup"><span data-stu-id="ef74e-214">The Command Handler class</span></span>

<span data-ttu-id="ef74e-215">Следует реализовать класс обработчика конкретной команды для каждой команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-215">You should implement a specific command handler class for each command.</span></span> <span data-ttu-id="ef74e-216">Это как шаблон работает, и это, где используется объект команды, объекты домена и объекты репозитория инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="ef74e-216">That is how the pattern works, and it is where you will use the command object, the domain objects, and the infrastructure repository objects.</span></span> <span data-ttu-id="ef74e-217">Обработчик команд на самом деле является сердцем платформы на уровне приложения с точки зрения CQRS и ддд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-217">The command handler is in fact the heart of the application layer in terms of CQRS and DDD.</span></span> <span data-ttu-id="ef74e-218">Однако вся логика домена должен находиться внутри домена классы — в пределах статистической корни (корневой сущности), дочерних сущностей или [доменных служб](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), но не в обработчике команды — это класс, из приложения слой.</span><span class="sxs-lookup"><span data-stu-id="ef74e-218">However, all the domain logic should be contained within the domain classes—within the aggregate roots (root entities), child entities, or [domain services](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), but not within the command handler, which is a class from the application layer.</span></span>

<span data-ttu-id="ef74e-219">Обработчик команд получает команды и получает результат из статистическое выражение, которое используется.</span><span class="sxs-lookup"><span data-stu-id="ef74e-219">A command handler receives a command and obtains a result from the aggregate that is used.</span></span> <span data-ttu-id="ef74e-220">Результат должен быть успешное выполнение команды или исключение.</span><span class="sxs-lookup"><span data-stu-id="ef74e-220">The result should be either successful execution of the command, or an exception.</span></span> <span data-ttu-id="ef74e-221">В случае возникновения исключения состояния системы следует без изменений.</span><span class="sxs-lookup"><span data-stu-id="ef74e-221">In the case of an exception, the system state should be unchanged.</span></span>

<span data-ttu-id="ef74e-222">Обычно обработчик команд выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ef74e-222">The command handler usually takes the following steps:</span></span>

-   <span data-ttu-id="ef74e-223">Получает объект команды, такие как DTO (из [посредником](https://en.wikipedia.org/wiki/Mediator_pattern) или другой объект инфраструктуры).</span><span class="sxs-lookup"><span data-stu-id="ef74e-223">It receives the command object, like a DTO (from the [mediator](https://en.wikipedia.org/wiki/Mediator_pattern) or other infrastructure object).</span></span>

-   <span data-ttu-id="ef74e-224">Она проверяет, что команда является допустимым (если не проверить с помощью посредника).</span><span class="sxs-lookup"><span data-stu-id="ef74e-224">It validates that the command is valid (if not validated by the mediator).</span></span>

-   <span data-ttu-id="ef74e-225">Он создает экземпляр статистические корневого, который является целевым объектом текущую команду.</span><span class="sxs-lookup"><span data-stu-id="ef74e-225">It instantiates the aggregate root instance that is the target of the current command.</span></span>

-   <span data-ttu-id="ef74e-226">Он выполняет метод на экземпляре статистические корневой получения необходимых данных из команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-226">It executes the method on the aggregate root instance, getting the required data from the command.</span></span>

-   <span data-ttu-id="ef74e-227">Она сохраняет новое состояние агрегатной функции в связанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="ef74e-227">It persists the new state of the aggregate to its related database.</span></span> <span data-ttu-id="ef74e-228">Эта последняя операция является фактические транзакции.</span><span class="sxs-lookup"><span data-stu-id="ef74e-228">This last operation is the actual transaction.</span></span>

<span data-ttu-id="ef74e-229">Как правило обработчик команд связана с одной статистической функции, обусловленных статистические корень (корневую сущность).</span><span class="sxs-lookup"><span data-stu-id="ef74e-229">Typically, a command handler deals with a single aggregate driven by its aggregate root (root entity).</span></span> <span data-ttu-id="ef74e-230">Если несколько статистических выражений должно повлиять на получение одной команды, можно использовать события домена распространяться состояния и действия по несколько статистических выражений</span><span class="sxs-lookup"><span data-stu-id="ef74e-230">If multiple aggregates should be impacted by the reception of a single command, you could use domain events to propagate states or actions across multiple aggregates</span></span>

<span data-ttu-id="ef74e-231">Здесь важно то, что при обработке команды всю логику домена должен быть внутри модели домена (статистические выражения), полностью инкапсулированный и готова для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="ef74e-231">The important point here is that when a command is being processed, all the domain logic should be inside the domain model (the aggregates), fully encapsulated and ready for unit testing.</span></span> <span data-ttu-id="ef74e-232">Обработчик команд действует только способ получить модель домена из базы данных, а последнее действие, чтобы определить уровень инфраструктуры (репозиториев) для сохранения изменений при смене модели.</span><span class="sxs-lookup"><span data-stu-id="ef74e-232">The command handler just acts as a way to get the domain model from the database, and as the final step, to tell the infrastructure layer (repositories) to persist the changes when the model is changed.</span></span> <span data-ttu-id="ef74e-233">Преимущество такого подхода является можно выполнить рефакторинг доменную логику модели изолированной, полностью инкапсулированный, широкие возможности, поведения домена без изменения кода в приложении или инфраструктуре слои, которые находятся на уровне направляющее (обработчики команд, веб-API репозиториев и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ef74e-233">The advantage of this approach is that you can refactor the domain logic in an isolated, fully encapsulated, rich, behavioral domain model without changing code in the application or infrastructure layers, which are the plumbing level (command handlers, Web API, repositories, etc.).</span></span>

<span data-ttu-id="ef74e-234">Когда обработчики команд get сложными, слишком большой объем логики, который может быть вонь от кода.</span><span class="sxs-lookup"><span data-stu-id="ef74e-234">When command handlers get complex, with too much logic, that can be a code smell.</span></span> <span data-ttu-id="ef74e-235">Ознакомление с ними, если Доменная логика, рефакторинг кода для перемещения этого поведения домена в методы объектов домена (статистические корневые и дочерние сущности).</span><span class="sxs-lookup"><span data-stu-id="ef74e-235">Review them, and if you find domain logic, refactor the code to move that domain behavior to the methods of the domain objects (the aggregate root and child entity).</span></span>

<span data-ttu-id="ef74e-236">В качестве примера класса обработчика команд код отображает тот же класс CreateOrderCommandHandler видно в начале данной главы.</span><span class="sxs-lookup"><span data-stu-id="ef74e-236">As an example of a command handler class, the following code shows the same CreateOrderCommandHandler class that you saw at the beginning of this chapter.</span></span> <span data-ttu-id="ef74e-237">В этом случае мы выделения дескриптора метода и операции с домена модели объектов или статистические выражения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-237">In this case we have highlighted the Handle method and the operations with the domain model objects/aggregates.</span></span>

```csharp
public class CreateOrderCommandHandler
    : IAsyncRequestHandler<CreateOrderCommand, bool>
{
    private readonly IBuyerRepository _buyerRepository;
    private readonly IOrderRepository _orderRepository;

    public CreateOrderCommandHandler(IBuyerRepository buyerRepository,
        IOrderRepository orderRepository)
    {
        if (buyerRepository == null)
        {
            throw new ArgumentNullException(nameof(buyerRepository));
        }
        if (orderRepository == null)
        {
            throw new ArgumentNullException(nameof(orderRepository));
        }

        _buyerRepository = buyerRepository;
        _orderRepository = orderRepository;
    }

    public async Task<bool> Handle(CreateOrderCommand message)
    {
        //
        // Additional code ...
        //
        // Create the Order aggregate root
        // Add child entities and value objects through the Order aggregate root
        // methods and constructor so validations, invariants, and business logic
        // make sure that consistency is preserved across the whole aggregate
        var order = new Order(buyer.Id, payment.Id,
            new Address(message.Street,
            message.City, message.State,
            message.Country, message.ZipCode));

        foreach (var item in message.OrderItems)
        {
            order.AddOrderItem(item.ProductId, item.ProductName, item.UnitPrice,
                item.Discount, item.PictureUrl, item.Units);
        }

        // Persist the Order through the aggregate's repository
        _orderRepository.Add(order);
        return await _orderRepository.UnitOfWork.SaveChangesAsync();
    }
}
```

<span data-ttu-id="ef74e-238">Это обработчик команды необходимо выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="ef74e-238">These are additional steps a command handler should take:</span></span>

-   <span data-ttu-id="ef74e-239">Используйте данные команды для работы с корня статистические методы и поведение.</span><span class="sxs-lookup"><span data-stu-id="ef74e-239">Use the command’s data to operate with the aggregate root’s methods and behavior.</span></span>

-   <span data-ttu-id="ef74e-240">Внутренне в объекты домена создавать события, домена, во время выполнения транзакции, но это прозрачное с команда обработчик точки зрения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-240">Internally within the domain objects, raise domain events while the transaction is executed, but that is transparent from a command handler point of view.</span></span>

-   <span data-ttu-id="ef74e-241">При успешном выполнении результат операции статистическое выражение и после завершения транзакции, вызывают обработчик команд события интеграции.</span><span class="sxs-lookup"><span data-stu-id="ef74e-241">If the aggregate’s operation result is successful and after the transaction is finished, raise integration events command handler.</span></span> <span data-ttu-id="ef74e-242">(Они могут также возникать классами инфраструктуры, например репозиториев.)</span><span class="sxs-lookup"><span data-stu-id="ef74e-242">(These might also be raised by infrastructure classes like repositories.)</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="ef74e-243">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ef74e-243">Additional resources</span></span>

-   <span data-ttu-id="ef74e-244">**Марк Симанн. Границы, приложения, не объектно-ориентированного**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, ориентированных на ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-244">**Mark Seemann. At the Boundaries, Applications are Not Object-Oriented**
[*http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)</span></span>

-   <span data-ttu-id="ef74e-245">**Команды и события**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span><span class="sxs-lookup"><span data-stu-id="ef74e-245">**Commands and events**
[*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)</span></span>

-   <span data-ttu-id="ef74e-246">**Что делает обработчик команд? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span><span class="sxs-lookup"><span data-stu-id="ef74e-246">**What does a command handler do?**
[*http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)</span></span>

-   <span data-ttu-id="ef74e-247">**Джимми Богард (Jimmy Bogard). Шаблоны команд домена — обработчики**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-247">**Jimmy Bogard. Domain Command Patterns – Handlers**
[*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)</span></span>

-   <span data-ttu-id="ef74e-248">**Джимми Богард (Jimmy Bogard). Шаблоны команд домена — проверка**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-248">**Jimmy Bogard. Domain Command Patterns – Validation**
[*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)</span></span>

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a><span data-ttu-id="ef74e-249">Процесс конвейере: активация является допустимым обработчиком команд</span><span class="sxs-lookup"><span data-stu-id="ef74e-249">The Command process pipeline: how to trigger a command handler</span></span>

<span data-ttu-id="ef74e-250">Следующий вопрос заключается в вызов обработчика команд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-250">The next question is how to invoke a command handler.</span></span> <span data-ttu-id="ef74e-251">Вручную может вызвать его из каждого связанные контроллера ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ef74e-251">You could manually call it from each related ASP.NET Core controller.</span></span> <span data-ttu-id="ef74e-252">Тем не менее что подходом было бы слишком связаны и не идеальное решение.</span><span class="sxs-lookup"><span data-stu-id="ef74e-252">However, that approach would be too coupled and is not ideal.</span></span>

<span data-ttu-id="ef74e-253">Другие два основных варианта, которые рекомендуется использовать параметры, являются:</span><span class="sxs-lookup"><span data-stu-id="ef74e-253">The other two main options, which are the recommended options, are:</span></span>

-   <span data-ttu-id="ef74e-254">Через шаблон артефакта посредника в памяти.</span><span class="sxs-lookup"><span data-stu-id="ef74e-254">Through an in-memory Mediator pattern artifact.</span></span>

-   <span data-ttu-id="ef74e-255">Асинхронное сообщение очереди сообщений, между контроллерами и обработчики.</span><span class="sxs-lookup"><span data-stu-id="ef74e-255">With an asynchronous message queue, in between controllers and handlers.</span></span>

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a><span data-ttu-id="ef74e-256">С помощью шаблона посредником (в памяти) в конвейере</span><span class="sxs-lookup"><span data-stu-id="ef74e-256">Using the Mediator pattern (in-memory) in the command pipeline</span></span>

<span data-ttu-id="ef74e-257">Как показано на рисунке 9-21, подход CQRS используется интеллектуальная посредника, аналогично шине в памяти, который способен перенаправить на основе типа команды или получения DTO обработчик команда right.</span><span class="sxs-lookup"><span data-stu-id="ef74e-257">As shown in Figure 9-21, in a CQRS approach you use an intelligent mediator, similar to an in-memory bus, which is smart enough to redirect to the right command handler based on the type of the command or DTO being received.</span></span> <span data-ttu-id="ef74e-258">Один черной стрелки между компонентами представляют зависимости между объектами (во многих случаях введенного через DI) с их связанных с ними взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="ef74e-258">The single black arrows between components represent the dependencies between objects (in many cases, injected through DI) with their related interactions.</span></span>

![](./media/image22.png)

<span data-ttu-id="ef74e-259">**На рисунке 9-21**.</span><span class="sxs-lookup"><span data-stu-id="ef74e-259">**Figure 9-21**.</span></span> <span data-ttu-id="ef74e-260">С помощью посредника шаблона процесса в одном микрослужбу CQRS</span><span class="sxs-lookup"><span data-stu-id="ef74e-260">Using the Mediator pattern in process in a single CQRS microservice</span></span>

<span data-ttu-id="ef74e-261">Причина, используя шаблон посредником имеет смысл в том, что в корпоративных приложениях обработки запросов может усложняться.</span><span class="sxs-lookup"><span data-stu-id="ef74e-261">The reason that using the Mediator pattern makes sense is that in enterprise applications, the processing requests can get complicated.</span></span> <span data-ttu-id="ef74e-262">Вы хотите иметь возможность добавить открытые количество решении общих задач ведения журнала, проверки, аудита и безопасности.</span><span class="sxs-lookup"><span data-stu-id="ef74e-262">You want to be able to add an open number of cross-cutting concerns like logging, validations, audit, and security.</span></span> <span data-ttu-id="ef74e-263">В таких случаях можно положиться на конвейере посредником (см. [шаблон посредником](https://en.wikipedia.org/wiki/Mediator_pattern)) для предоставления средства эти дополнительные поведения или проблемы пересечения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-263">In these cases, you can rely on a mediator pipeline (see [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern)) to provide a means for these extra behaviors or cross-cutting concerns.</span></span>

<span data-ttu-id="ef74e-264">Объект, инкапсулирующий «как» этого процесса является посредником: он координирует выполнение на основе состояния, вызывается метод обработчика команды или полезные данные, указываемые в обработчик.</span><span class="sxs-lookup"><span data-stu-id="ef74e-264">A mediator is an object that encapsulates the “how” of this process: it coordinates execution based on state, the way a command handler is invoked, or the payload you provide to the handler.</span></span> <span data-ttu-id="ef74e-265">С компонентом посредником можно применить проблемы пересечения централизованное и прозрачным способом, применяя декораторов (или [конвейер поведений](https://github.com/jbogard/MediatR/wiki/Behaviors) с момента посредником v3).</span><span class="sxs-lookup"><span data-stu-id="ef74e-265">With a mediator component you can apply cross-cutting concerns in a centralized and transparent way by applying decorators (or [pipeline behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) since Mediator v3).</span></span> <span data-ttu-id="ef74e-266">(Дополнительные сведения см. в разделе [шаблон Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)</span><span class="sxs-lookup"><span data-stu-id="ef74e-266">(For more information, see the [Decorator pattern](https://en.wikipedia.org/wiki/Decorator_pattern).)</span></span>

<span data-ttu-id="ef74e-267">Поведение и декораторы аналогичны [аспект ориентированного программирования (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)только для применения конвейер определенного процесса, управляемого компонентом посредником.</span><span class="sxs-lookup"><span data-stu-id="ef74e-267">Decorators and behaviors are similar to [Aspect Oriented Programming (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming), only applied to a specific process pipeline managed by the mediator component.</span></span> <span data-ttu-id="ef74e-268">Аспекты в AOP, реализующих проблемы пересечения применяются на основе *weavers аспект* введенного во время компиляции или на основании перехвата объекта вызова.</span><span class="sxs-lookup"><span data-stu-id="ef74e-268">Aspects in AOP that implement cross-cutting concerns are applied based on *aspect weavers* injected at compilation time or based on object call interception.</span></span> <span data-ttu-id="ef74e-269">Оба типичные подходы AOP иногда называются работать «как magic», так как он не легко увидеть, каким образом AOP выполняет свою работу.</span><span class="sxs-lookup"><span data-stu-id="ef74e-269">Both typical AOP approaches are sometimes said to work "like magic," because it is not easy to see how AOP does its work.</span></span> <span data-ttu-id="ef74e-270">При работе с серьезной проблемы или ошибки, AOP может быть трудно отлаживать.</span><span class="sxs-lookup"><span data-stu-id="ef74e-270">When dealing with serious issues or bugs, AOP can be difficult to debug.</span></span> <span data-ttu-id="ef74e-271">С другой стороны декораторы и поведение являются явные и применяется только в контексте посредника, поэтому отладка гораздо большей предсказуемостью и легко.</span><span class="sxs-lookup"><span data-stu-id="ef74e-271">On the other hand, these decorators/behaviors are explicit and applied only in the context of the mediator, so debugging is much more predictable and easy.</span></span>

<span data-ttu-id="ef74e-272">Например, в eShopOnContainers, упорядочение микрослужбу, мы реализовали декораторов два образца, [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) класса и [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) класса.</span><span class="sxs-lookup"><span data-stu-id="ef74e-272">For example, in the eShopOnContainers ordering microservice, we implemented two sample decorators, a [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class and a [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class.</span></span> <span data-ttu-id="ef74e-273">В следующем разделе описывается реализация декоратор.</span><span class="sxs-lookup"><span data-stu-id="ef74e-273">The decorator’s implementation is explained in the next section.</span></span> <span data-ttu-id="ef74e-274">Обратите внимание, что в будущих версиях eShopOnContainers перенесет [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) и переместить [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) вместо использования декораторов.</span><span class="sxs-lookup"><span data-stu-id="ef74e-274">Note that in a future version, eShopOnContainers will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a><span data-ttu-id="ef74e-275">С помощью очереди сообщений (вне процесса) в конвейере команд</span><span class="sxs-lookup"><span data-stu-id="ef74e-275">Using message queues (out-of-proc) in the command’s pipeline</span></span>

<span data-ttu-id="ef74e-276">Другой вариант — использование асинхронных сообщений на основе брокеров или очереди сообщений, как показано на рисунке 9-22.</span><span class="sxs-lookup"><span data-stu-id="ef74e-276">Another choice is to use asynchronous messages based on brokers or message queues, as shown in Figure 9-22.</span></span> <span data-ttu-id="ef74e-277">Этот параметр может быть совмещена с компонент посредником прямо перед обработчик команд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-277">That option could also be combined with the mediator component right before the command handler.</span></span>

![](./media/image23.png)

<span data-ttu-id="ef74e-278">**На рисунке 9-22**.</span><span class="sxs-lookup"><span data-stu-id="ef74e-278">**Figure 9-22**.</span></span> <span data-ttu-id="ef74e-279">С помощью очереди сообщений (вне процесса и связи между процессами) с помощью команд CQRS</span><span class="sxs-lookup"><span data-stu-id="ef74e-279">Using message queues (out of process and inter-process communication) with CQRS commands</span></span>

<span data-ttu-id="ef74e-280">С помощью сообщений очереди, чтобы принять дополнительные команды могут усложнить конвейера в команду, так как, возможно, понадобится разбиение конвейера на два процесса подключается через внешние сообщения очереди.</span><span class="sxs-lookup"><span data-stu-id="ef74e-280">Using message queues to accept the commands can further complicate your command’s pipeline, because you will probably need to split the pipeline into two processes connected through the external message queue.</span></span> <span data-ttu-id="ef74e-281">Тем не менее ее следует использовать, если необходимо повышение масштабируемости и производительности в зависимости от асинхронного обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ef74e-281">Still, it should be used if you need to have improved scalability and performance based on asynchronous messaging.</span></span> <span data-ttu-id="ef74e-282">Примите во внимание в случае рисунок 9 – 22, просто контроллер отправляет сообщение команды в очередь и возвращает.</span><span class="sxs-lookup"><span data-stu-id="ef74e-282">Consider that in the case of Figure 9-22, the controller just posts the command message into the queue and returns.</span></span> <span data-ttu-id="ef74e-283">Затем обработчик команды обработку сообщений в своем темпе.</span><span class="sxs-lookup"><span data-stu-id="ef74e-283">Then the command handlers process the messages at their own pace.</span></span> <span data-ttu-id="ef74e-284">То есть значительные преимущества очередей — очереди сообщений может выступать в качестве буфера в случаях при необходимости, например, биржевые сводки или любом другом сценарии, с большим объемом входящих данных hyper масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="ef74e-284">That is a great benefit of queues—the message queue can act as a buffer in cases when hyper scalability is needed, such as for stocks or any other scenario with a high volume of ingress data.</span></span>

<span data-ttu-id="ef74e-285">Однако из-за характера асинхронной очереди сообщений, необходимо понять, как взаимодействовать с клиентским приложением об успешном или неуспешном процесса команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-285">However, because of the asynchronous nature of message queues, you need to figure out how to communicate with the client application about the success or failure of the command’s process.</span></span> <span data-ttu-id="ef74e-286">Как правило никогда не следует использовать команды «Отправить и забыть».</span><span class="sxs-lookup"><span data-stu-id="ef74e-286">As a rule, you should never use “fire and forget” commands.</span></span> <span data-ttu-id="ef74e-287">Каждый бизнес-приложение должно быть известно, если команда была обработана успешно, или по крайней мере проверки и принято.</span><span class="sxs-lookup"><span data-stu-id="ef74e-287">Every business application needs to know if a command was processed successfully, or at least validated and accepted.</span></span>

<span data-ttu-id="ef74e-288">Таким образом не сможет отвечать клиенту после проверки команда сообщения, отправленного в очередь асинхронных усложняет систему по сравнению с процесс команды в процессе, который возвращает результат операции после запуска транзакции.</span><span class="sxs-lookup"><span data-stu-id="ef74e-288">Thus, being able to respond to the client after validating a command message that was submitted to an asynchronous queue adds complexity to your system, as compared to an in-process command process that returns the operation’s result after running the transaction.</span></span> <span data-ttu-id="ef74e-289">С использованием очередей, может потребоваться вернуть результат процесс команды с помощью других сообщений результат операции, которые требуют дополнительных компонентов и пользовательские связи в системе.</span><span class="sxs-lookup"><span data-stu-id="ef74e-289">Using queues, you might need to return the result of the command process through other operation result messages, which will require additional components and custom communication in your system.</span></span>

<span data-ttu-id="ef74e-290">Кроме того, команды async, односторонний команды, в которых во многих случаях может не потребоваться, как описано в следующих интересные обмена данными между Алексей Burtsev и Янг Грег в [обсуждения](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span><span class="sxs-lookup"><span data-stu-id="ef74e-290">Additionally, async commands are one-way commands, which in many cases might not be needed, as is explained in the following interesting exchange between Burtsev Alexey and Greg Young in an [online conversation](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):</span></span>

<span data-ttu-id="ef74e-291">\[Алексей Burtsev\] найти множество кода которых используется обработка асинхронных команд или одним из способов команды, обмен сообщениями без какой-либо причине, чтобы сделать это (они не реализуют некоторые длительной операции, они не выполняются внешних асинхронного кода, они даже не пересекали приложения граница будет использовать канал сообщений).</span><span class="sxs-lookup"><span data-stu-id="ef74e-291">\[Burtsev Alexey\] I find lots of code where people use async command handling or one way command messaging without any reason to do so (they are not doing some long operation, they are not executing external async code, they do not even cross application boundary to be using message bus).</span></span> <span data-ttu-id="ef74e-292">Почему они вызвать это излишнее усложнение?</span><span class="sxs-lookup"><span data-stu-id="ef74e-292">Why do they introduce this unnecessary complexity?</span></span> <span data-ttu-id="ef74e-293">И в действительности не видели пример кода CQRS с на данный момент блокирует обработчики команд на то, что он будет работать корректно, в большинстве случаев.</span><span class="sxs-lookup"><span data-stu-id="ef74e-293">And actually, I haven't seen a CQRS code example with blocking command handlers so far, though it will work just fine in most cases.</span></span>

<span data-ttu-id="ef74e-294">\[Грег Янг\] \[... \] асинхронную команду не существует; это фактически другое событие.</span><span class="sxs-lookup"><span data-stu-id="ef74e-294">\[Greg Young\] \[...\] an asynchronous command doesn't exist; it's actually another event.</span></span> <span data-ttu-id="ef74e-295">Если необходимо принять, что вы отправлять мне и инициировать событие, если не принимаю, он больше не вы говорите каким-либо.</span><span class="sxs-lookup"><span data-stu-id="ef74e-295">If I must accept what you send me and raise an event if I disagree, it's no longer you telling me to do something.</span></span> <span data-ttu-id="ef74e-296">Это действительно вы сообщает, что-то было сделано.</span><span class="sxs-lookup"><span data-stu-id="ef74e-296">It's you telling me something has been done.</span></span> <span data-ttu-id="ef74e-297">На первый взгляд незначительные различия на первый, но она влияет на множество.</span><span class="sxs-lookup"><span data-stu-id="ef74e-297">This seems like a slight difference at first, but it has many implications.</span></span>

<span data-ttu-id="ef74e-298">Асинхронные команды значительно увеличивается сложность системы, так как нет простого способа сведения о сбоях.</span><span class="sxs-lookup"><span data-stu-id="ef74e-298">Asynchronous commands greatly increase the complexity of a system, because there is no simple way to indicate failures.</span></span> <span data-ttu-id="ef74e-299">Таким образом асинхронных команд не рекомендуются отличный от при масштабировании требования или в особых случаях при взаимодействии внутренней микрослужбами посредством обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ef74e-299">Therefore, asynchronous commands are not recommended other than when scaling requirements are needed or in special cases when communicating the internal microservices through messaging.</span></span> <span data-ttu-id="ef74e-300">В таких случаях необходимо создать отдельные отчеты и восстановления системы сбоев.</span><span class="sxs-lookup"><span data-stu-id="ef74e-300">In those cases, you must design a separate reporting and recovery system for failures.</span></span>

<span data-ttu-id="ef74e-301">В первоначальную версию eShopOnContainers мы решили использовать обработку синхронных команд, запущен из HTTP-запросы и набором шаблон посредником.</span><span class="sxs-lookup"><span data-stu-id="ef74e-301">In the initial version of eShopOnContainers, we decided to use synchronous command processing, started from HTTP requests and driven by the Mediator pattern.</span></span> <span data-ttu-id="ef74e-302">Легко позволяет вернуться успешность процесса, как и в [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) реализации.</span><span class="sxs-lookup"><span data-stu-id="ef74e-302">That easily allows you to return the success or failure of the process, as in the [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) implementation.</span></span>

<span data-ttu-id="ef74e-303">В любом случае это должна быть принятия решений, в зависимости от приложения или элемента микрослужбу бизнес-требований.</span><span class="sxs-lookup"><span data-stu-id="ef74e-303">In any case, this should be a decision based on your application’s or microservice’s business requirements.</span></span>

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a><span data-ttu-id="ef74e-304">Реализация конвейера процесса команда посредником шаблоном (MediatR)</span><span class="sxs-lookup"><span data-stu-id="ef74e-304">Implementing the command process pipeline with a mediator pattern (MediatR)</span></span>

<span data-ttu-id="ef74e-305">Как образец реализации в этом руководстве предлагаются с помощью конвейера в процессе на основе шаблона посредника для приема команда диска и маршрутизации, в памяти, обработчиками команд вправо.</span><span class="sxs-lookup"><span data-stu-id="ef74e-305">As a sample implementation, this guide proposes using the in-process pipeline based on the Mediator pattern to drive command ingestion and routing them, in memory, to the right command handlers.</span></span> <span data-ttu-id="ef74e-306">Руководство предлагает применение декораторов или [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) для разделения проблемы пересечения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-306">The guide also proposes applying decorators or [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) in order to separate cross-cutting concerns.</span></span>

<span data-ttu-id="ef74e-307">Для реализации в .NET Core нет несколько открытая библиотеки доступны, реализующих шаблон посредником.</span><span class="sxs-lookup"><span data-stu-id="ef74e-307">For implementation in .NET Core, there are multiple open-source libraries available that implement the Mediator pattern.</span></span> <span data-ttu-id="ef74e-308">В этом руководстве используется библиотека [MediatR](https://github.com/jbogard/MediatR) библиотеки открытым исходным кодом (созданное Джимми Богард), но может использовать другой подход.</span><span class="sxs-lookup"><span data-stu-id="ef74e-308">The library used in this guide is the [MediatR](https://github.com/jbogard/MediatR) open-source library (created by Jimmy Bogard), but you could use another approach.</span></span> <span data-ttu-id="ef74e-309">MediatR — это библиотека небольших и простых, которая позволяет обрабатывать сообщения в памяти как команды, при применении декораторов или поведения.</span><span class="sxs-lookup"><span data-stu-id="ef74e-309">MediatR is a small and simple library that allows you to process in-memory messages like a command, while applying decorators or behaviors.</span></span>

<span data-ttu-id="ef74e-310">С помощью шаблона посредником помогает уменьшить взаимозависимости и изолировать проблемы запрашиваемую работу при автоматическом соединении обработчик, который выполняет эту работу — в этом случае для обработчиков команд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-310">Using the Mediator pattern helps you to reduce coupling and to isolate the concerns of the requested work, while automatically connecting to the handler that performs that work—in this case, to command handlers.</span></span>

<span data-ttu-id="ef74e-311">Другой веская причина для использования шаблона посредником объяснялось, Джимми Богард при просмотре в этом руководстве:</span><span class="sxs-lookup"><span data-stu-id="ef74e-311">Another good reason to use the Mediator pattern was explained by Jimmy Bogard when reviewing this guide:</span></span>

<span data-ttu-id="ef74e-312">Я думаю, возможно, следует упомянуть здесь тестирование — он предоставляет окно согласованной работы с низким приоритетом в поведение системы.</span><span class="sxs-lookup"><span data-stu-id="ef74e-312">I think it might be worth mentioning testing here – it provides a nice consistent window into the behavior of your system.</span></span> <span data-ttu-id="ef74e-313">В запрос, выход ответа. Мы обнаружили этого аспекта весьма ценным в здании согласованно работает тестов.</span><span class="sxs-lookup"><span data-stu-id="ef74e-313">Request-in, response-out. We’ve found that aspect quite valuable in building consistently behaving tests.</span></span>

<span data-ttu-id="ef74e-314">Во-первых сообщите нам взгляните на код контроллера когда фактически используется объект посредником.</span><span class="sxs-lookup"><span data-stu-id="ef74e-314">First, let us take a look to the controller code where you actually would use the mediator object.</span></span> <span data-ttu-id="ef74e-315">Если вы не используете объект посредником, необходимо ввести все зависимости для контроллера, такие как объект средства ведения журнала и другие.</span><span class="sxs-lookup"><span data-stu-id="ef74e-315">If you were not using the mediator object, you would need to inject all the dependencies for that controller, things like a logger object and others.</span></span> <span data-ttu-id="ef74e-316">Таким образом конструктор будет довольно сложными.</span><span class="sxs-lookup"><span data-stu-id="ef74e-316">Therefore, the constructor would be quite complicated.</span></span> <span data-ttu-id="ef74e-317">С другой стороны Если вы используете объект посредником, конструктор контроллера может быть гораздо проще всего несколько зависимостей вместо много зависимостей, которые потребовалось бы, если у вас есть по одному на операцию пересечения, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ef74e-317">On the other hand, if you use the mediator object, the constructor of your controller can be a lot simpler, with just a few dependencies instead of many dependencies that you would have if you had one per cross-cutting operation, as in the following example:</span></span>

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

<span data-ttu-id="ef74e-318">Вы увидите, что посредника предоставляет чистого и экономичных конструктором контроллера веб-API.</span><span class="sxs-lookup"><span data-stu-id="ef74e-318">You can see that the mediator provides a clean and lean Web API controller constructor.</span></span> <span data-ttu-id="ef74e-319">Кроме того в методы контроллера, код для отправки команды к объекту посредником, почти одну строку:</span><span class="sxs-lookup"><span data-stu-id="ef74e-319">In addition, within the controller methods, the code to send a command to the mediator object is almost one line:</span></span>

```csharp
[Route("new")]
[HttpPost]
public async Task<IActionResult> CreateOrder([FromBody]CreateOrderCommand
    createOrderCommand)
{
    var commandResult = await _mediator.SendAsync(createOrderCommand);
    return commandResult ? (IActionResult)Ok() : (IActionResult)BadRequest();
}
```

<span data-ttu-id="ef74e-320">Чтобы MediatR следует учитывать классов обработчика команды необходимо зарегистрировать посредником классов и классов обработчика команд в контейнер IoC.</span><span class="sxs-lookup"><span data-stu-id="ef74e-320">In order for MediatR to be aware of your command handler classes, you need to register the mediator classes and the command handler classes in your IoC container.</span></span> <span data-ttu-id="ef74e-321">По умолчанию MediatR Autofac используется как контейнер IoC, но можно также использовать встроенные контейнер ASP.NET Core IoC или любым другим контейнером, поддерживаемый MediatR.</span><span class="sxs-lookup"><span data-stu-id="ef74e-321">By default, MediatR uses Autofac as the IoC container, but you can also use the built-in ASP.NET Core IoC container or any other container supported by MediatR.</span></span>

<span data-ttu-id="ef74e-322">Следующий код показано, как зарегистрировать типы посредником и команд при использовании Autofac модулей.</span><span class="sxs-lookup"><span data-stu-id="ef74e-322">The following code shows how to register Mediator’s types and commands when using Autofac modules.</span></span>

```csharp
public class MediatorModule : Autofac.Module
{
    protected override void Load(ContainerBuilder builder)
    {
        builder.RegisterAssemblyTypes(typeof(IMediator).GetTypeInfo().Assembly)
            .AsImplementedInterfaces();
        builder.RegisterAssemblyTypes(typeof(CreateOrderCommand)
            .GetTypeInfo().Assembly)
            .As(o => o.GetInterfaces()
            .Where(i => i.IsClosedTypeOf(typeof(IAsyncRequestHandler<,>)))
            .Select(i => new KeyedService("IAsyncRequestHandler", i)));
        builder.RegisterGenericDecorator(typeof(LogDecorator<,>),
            typeof(IAsyncRequestHandler<,>), "IAsyncRequestHandler");

        // Other types registration
    }
}
```

<span data-ttu-id="ef74e-323">Поскольку каждый обработчик команд реализует интерфейс с универсальным IAsyncRequestHandler&lt;T&gt; и затем просматривает RegisteredAssemblyTypes объекта обработчик возможность связать каждую команду его обработчик команд, так как, отношение выражается в классе CommandHandler, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ef74e-323">Because each command handler implements the interface with generic IAsyncRequestHandler&lt;T&gt; and then inspects the RegisteredAssemblyTypes object, the handler is able to relate each command with its command handler, because that relationship is stated in the CommandHandler class, as in the following example:</span></span>

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

<span data-ttu-id="ef74e-324">Это код, который сопоставляет команды с обработчиков команд.</span><span class="sxs-lookup"><span data-stu-id="ef74e-324">This is the code that correlates commands with command handlers.</span></span> <span data-ttu-id="ef74e-325">Обработчик является простой класс, но он наследует RequestHandler&lt;T&gt;, и MediatR обеспечивает ее вызова возвращает правильный полезных данных.</span><span class="sxs-lookup"><span data-stu-id="ef74e-325">The handler is just a simple class, but it inherits from RequestHandler&lt;T&gt;, and MediatR makes sure it gets invoked with the correct payload.</span></span>

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a><span data-ttu-id="ef74e-326">Применение перекрестными проблемы при обработке команды с шаблонами посредника и Decorator</span><span class="sxs-lookup"><span data-stu-id="ef74e-326">Applying cross-cutting concerns when processing commands with the Mediator and Decorator patterns</span></span>

<span data-ttu-id="ef74e-327">Есть еще одно: возможность применить при решении общих задач в конвейере посредником.</span><span class="sxs-lookup"><span data-stu-id="ef74e-327">There is one more thing: being able to apply cross-cutting concerns to the mediator pipeline.</span></span> <span data-ttu-id="ef74e-328">Можно также просмотреть в конце код модуля регистрации Autofac как регистрирующий декоратор введите, в частности, пользовательский класс LogDecorator.</span><span class="sxs-lookup"><span data-stu-id="ef74e-328">You can also see at the end of the Autofac registration module code how it is registering a decorator type, specifically, a custom LogDecorator class.</span></span>

<span data-ttu-id="ef74e-329">Обратите внимание, что будущая версия eShopOnContainers она будет перемещена [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) и переместить [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) вместо использования декораторов.</span><span class="sxs-lookup"><span data-stu-id="ef74e-329">Again, note that a future version of eShopOnContainers it will migrate to [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) and move to [behaviors](https://github.com/jbogard/MediatR/wiki/Behaviors) instead of using decorators.</span></span>

<span data-ttu-id="ef74e-330">Что [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) класса могут быть реализованы как следующий код, который записывает сведения о выполняемой обработчик команд и был успешно или нет.</span><span class="sxs-lookup"><span data-stu-id="ef74e-330">That [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) class can be implemented as the following code, which logs information about the command handler being executed and whether it was successful or not.</span></span>

```csharp
public class LogDecorator<TRequest, TResponse>
    : IAsyncRequestHandler<TRequest, TResponse>
    where TRequest : IAsyncRequest<TResponse>
{
    private readonly IAsyncRequestHandler<TRequest, TResponse> _inner;
    private readonly ILogger<LogDecorator<TRequest, TResponse>> _logger;

    public LogDecorator(
        IAsyncRequestHandler<TRequest, TResponse> inner,
        ILogger<LogDecorator<TRequest, TResponse>> logger)
    {
        _inner = inner;
        _logger = logger;
    }

    public async Task<TResponse> Handle(TRequest message)
    {
        _logger.LogInformation($"Executing command {_inner.GetType().FullName}");
        var response = await _inner.Handle(message);
        _logger.LogInformation($"Succeeded executed command{_inner.GetType().FullName}");
        return response;
    }
}
```

<span data-ttu-id="ef74e-331">Просто путем реализации этого класса decorator и дополняя конвейера с ним всех команд, обработанных с помощью MediatR входа сведения о выполнении.</span><span class="sxs-lookup"><span data-stu-id="ef74e-331">Just by implementing this decorator class and by decorating the pipeline with it, all the commands processed through MediatR will be logging information about the execution.</span></span>

<span data-ttu-id="ef74e-332">EShopOnContainers упорядочение микрослужбу также применяется декоратор второй основных проверок [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) класс, который зависит от [FluentValidation](https://github.com/JeremySkinner/FluentValidation) библиотеки, как показано в Следующий код:</span><span class="sxs-lookup"><span data-stu-id="ef74e-332">The eShopOnContainers ordering microservice also applies a second decorator for basic validations, the [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) class that relies on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, as shown in the following code:</span></span>

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

<span data-ttu-id="ef74e-333">Затем на основе [FluentValidation](https://github.com/JeremySkinner/FluentValidation) библиотеки, мы создали проверки для данных, передаваемых с CreateOrderCommand, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="ef74e-333">Then, based on the [FluentValidation](https://github.com/JeremySkinner/FluentValidation) library, we created validation for the data passed with CreateOrderCommand, as in the following code:</span></span>

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
        RuleFor(command => command.CardExpiration).NotEmpty().Must(BeValidExpirationDate).
            WithMessage("Please specify a valid card expiration date");
        RuleFor(command => command.CardSecurityNumber).NotEmpty().Length(3);
        RuleFor(command => command.CardTypeId).NotEmpty();
        RuleFor(command => command.OrderItems).
            Must(ContainOrderItems).WithMessage("No order items found");
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

<span data-ttu-id="ef74e-334">Можно создать дополнительные проверки.</span><span class="sxs-lookup"><span data-stu-id="ef74e-334">You could create additional validations.</span></span> <span data-ttu-id="ef74e-335">Это очень простой и элегантный способ реализации проверки вашей команды.</span><span class="sxs-lookup"><span data-stu-id="ef74e-335">This is a very clean and elegant way to implement your command validations.</span></span>

<span data-ttu-id="ef74e-336">Аналогичным образом можно реализовать другие декораторов Дополнительные аспекты или решении общих задач, которые необходимо применить к командам, при их обработке.</span><span class="sxs-lookup"><span data-stu-id="ef74e-336">In a similar way, you could implement other decorators for additional aspects or cross-cutting concerns that you want to apply to commands when handling them.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="ef74e-337">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ef74e-337">Additional resources</span></span>

##### <a name="the-mediator-pattern"></a><span data-ttu-id="ef74e-338">Шаблон посредника</span><span class="sxs-lookup"><span data-stu-id="ef74e-338">The mediator pattern</span></span>

-   <span data-ttu-id="ef74e-339">**Шаблон посредником**
    [*https://en.wikipedia.org/wiki/Mediator\_шаблон*](https://en.wikipedia.org/wiki/Mediator_pattern)</span><span class="sxs-lookup"><span data-stu-id="ef74e-339">**Mediator pattern**
[*https://en.wikipedia.org/wiki/Mediator\_pattern*](https://en.wikipedia.org/wiki/Mediator_pattern)</span></span>

##### <a name="the-decorator-pattern"></a><span data-ttu-id="ef74e-340">Шаблон decorator</span><span class="sxs-lookup"><span data-stu-id="ef74e-340">The decorator pattern</span></span>

-   <span data-ttu-id="ef74e-341">**Шаблон декоратора**
    [*https://en.wikipedia.org/wiki/Decorator\_шаблон*](https://en.wikipedia.org/wiki/Decorator_pattern)</span><span class="sxs-lookup"><span data-stu-id="ef74e-341">**Decorator pattern**
[*https://en.wikipedia.org/wiki/Decorator\_pattern*](https://en.wikipedia.org/wiki/Decorator_pattern)</span></span>

##### <a name="mediatr-jimmy-bogard"></a><span data-ttu-id="ef74e-342">MediatR (Джимми Богард)</span><span class="sxs-lookup"><span data-stu-id="ef74e-342">MediatR (Jimmy Bogard)</span></span>

-   <span data-ttu-id="ef74e-343">**MediatR.**</span><span class="sxs-lookup"><span data-stu-id="ef74e-343">**MediatR.**</span></span> <span data-ttu-id="ef74e-344">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="ef74e-344">GitHub repo.</span></span>
    [<span data-ttu-id="ef74e-345">*https://github.com/jbogard/MediatR*</span><span class="sxs-lookup"><span data-stu-id="ef74e-345">*https://github.com/jbogard/MediatR*</span></span>](https://github.com/jbogard/MediatR)

-   <span data-ttu-id="ef74e-346">**CQRS с MediatR и AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-346">**CQRS with MediatR and AutoMapper**
[*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)</span></span>

-   <span data-ttu-id="ef74e-347">**Разместить контроллеры на диеты: в блогах и команд. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-347">**Put your controllers on a diet: POSTs and commands.**
[*https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)</span></span>

-   <span data-ttu-id="ef74e-348">**Решение проблемы пересечения с конвейером посредником**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-348">**Tackling cross-cutting concerns with a mediator pipeline**
[*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)</span></span>

-   <span data-ttu-id="ef74e-349">**CQRS и REST: найденного совпадения**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-349">**CQRS and REST: the perfect match**
[*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)</span></span>

-   <span data-ttu-id="ef74e-350">**Примеры конвейера MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-350">**MediatR Pipeline Examples**
[*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)</span></span>

-   <span data-ttu-id="ef74e-351">**Основы для вертикального ползунка тестирования MediatR и ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*</span><span class="sxs-lookup"><span data-stu-id="ef74e-351">**Vertical Slice Test Fixtures for MediatR and ASP.NET Core**
*<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/> *</span></span>

-   <span data-ttu-id="ef74e-352">**MediatR расширений для внедрения зависимостей Корпорация Майкрософт выпустила**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span><span class="sxs-lookup"><span data-stu-id="ef74e-352">**MediatR Extensions for Microsoft Dependency Injection Released**
[*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)</span></span>

##### <a name="fluent-validation"></a><span data-ttu-id="ef74e-353">Fluent проверки</span><span class="sxs-lookup"><span data-stu-id="ef74e-353">Fluent validation</span></span>

-   <span data-ttu-id="ef74e-354">**Скиннер Jeremy. FluentValidation.**</span><span class="sxs-lookup"><span data-stu-id="ef74e-354">**Jeremy Skinner. FluentValidation.**</span></span> <span data-ttu-id="ef74e-355">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="ef74e-355">GitHub repo.</span></span>
    [<span data-ttu-id="ef74e-356">*https://github.com/JeremySkinner/FluentValidation*</span><span class="sxs-lookup"><span data-stu-id="ef74e-356">*https://github.com/JeremySkinner/FluentValidation*</span></span>](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
<span data-ttu-id="ef74e-357">[Предыдущие] (microservice-application-layer-web-api-design.md) [Далее] (.. /Implement-Resilient-Applications/index.MD)</span><span class="sxs-lookup"><span data-stu-id="ef74e-357">[Previous] (microservice-application-layer-web-api-design.md) [Next] (../implement-resilient-applications/index.md)</span></span>
