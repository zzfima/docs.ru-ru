---
title: "Реализация уровня инфраструктуры сохраняемости с Entity Framework Core"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация уровня инфраструктуры сохраняемости с Entity Framework Core"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 508d60d73eb7c0f0cc2cc909613cc4f8712b4aba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a><span data-ttu-id="3f878-104">Реализация уровня инфраструктуры сохраняемости с Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="3f878-104">Implementing the infrastructure persistence layer with Entity Framework Core</span></span>

<span data-ttu-id="3f878-105">При использовании реляционных баз данных, например SQL Server, Oracle или PostgreSQL, рекомендуемый подход заключается в реализации на уровне хранения на основе на Entity Framework (EF).</span><span class="sxs-lookup"><span data-stu-id="3f878-105">When you use relational databases such as SQL Server, Oracle, or PostgreSQL, a recommended approach is to implement the persistence layer based on Entity Framework (EF).</span></span> <span data-ttu-id="3f878-106">EF поддерживает LINQ и предоставляет строго типизированных объектов для модели, а также упрощенное сохраняемости в базу данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-106">EF supports LINQ and provides strongly typed objects for your model, as well as simplified persistence into your database.</span></span>

<span data-ttu-id="3f878-107">Платформа Entity Framework имеет длинную историю в составе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3f878-107">Entity Framework has a long history as part of the .NET Framework.</span></span> <span data-ttu-id="3f878-108">При использовании .NET Core, следует также использовать Entity Framework Core, который выполняется на Windows или Linux в так же, как .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3f878-108">When you use .NET Core, you should also use Entity Framework Core, which runs on Windows or Linux in the same way as .NET Core.</span></span> <span data-ttu-id="3f878-109">EF лежит полностью переписан платформы Entity Framework реализована с помощью намного меньше памяти и важные улучшения в производительности.</span><span class="sxs-lookup"><span data-stu-id="3f878-109">EF Core is a complete rewrite of Entity Framework, implemented with a much smaller footprint and important improvements in performance.</span></span>

## <a name="introduction-to-entity-framework-core"></a><span data-ttu-id="3f878-110">Общие сведения об Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="3f878-110">Introduction to Entity Framework Core</span></span>

<span data-ttu-id="3f878-111">Core Entity Framework (EF) является упрощенным, расширяемым, и технология доступа к версии кросс платформенных популярных данных Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3f878-111">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="3f878-112">Она появилась в .NET Core в середине 2016.</span><span class="sxs-lookup"><span data-stu-id="3f878-112">It was introduced with .NET Core in mid-2016.</span></span>

<span data-ttu-id="3f878-113">Поскольку введение в основные EF недоступные в документации Microsoft, здесь просто содержатся ссылки на эти сведения.</span><span class="sxs-lookup"><span data-stu-id="3f878-113">Since an introduction to EF Core is already available in Microsoft documentation, here we simply provide links to that information.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3f878-114">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="3f878-114">Additional resources</span></span>

-   <span data-ttu-id="3f878-115">**Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span><span class="sxs-lookup"><span data-stu-id="3f878-115">**Entity Framework Core**
[*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)</span></span>

-   <span data-ttu-id="3f878-116">**Приступая к работе с ASP.NET Core и Entity Framework с помощью Visual Studio**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span><span class="sxs-lookup"><span data-stu-id="3f878-116">**Getting started with ASP.NET Core and Entity Framework Core using Visual Studio**
[*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)</span></span>

-   <span data-ttu-id="3f878-117">**Класс DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span><span class="sxs-lookup"><span data-stu-id="3f878-117">**DbContext Class**
[*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)</span></span>

-   <span data-ttu-id="3f878-118">**Сравнение основных EF & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span><span class="sxs-lookup"><span data-stu-id="3f878-118">**Compare EF Core & EF6.x**
[*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)</span></span>

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a><span data-ttu-id="3f878-119">С точки зрения DDD инфраструктуры Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="3f878-119">Infrastructure in Entity Framework Core from a DDD perspective</span></span>

<span data-ttu-id="3f878-120">С точки зрения DDD являются важной характеристикой EF является возможность использования сущности POCO домена, в терминологии EF как POCO также называется *сначала код сущности*.</span><span class="sxs-lookup"><span data-stu-id="3f878-120">From a DDD point of view, an important capability of EF is the ability to use POCO domain entities, also known in EF terminology as POCO *code-first entities*.</span></span> <span data-ttu-id="3f878-121">При использовании домена сущности POCO, ваши классы модели домена сохраняемость, следуя [сохраняемости](http://deviq.com/persistence-ignorance/) и [пропуск инфраструктуры](https://ayende.com/blog/3137/infrastructure-ignorance) принципы.</span><span class="sxs-lookup"><span data-stu-id="3f878-121">If you use POCO domain entities, your domain model classes are persistence-ignorant, following the [Persistence Ignorance](http://deviq.com/persistence-ignorance/) and the [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) principles.</span></span>

<span data-ttu-id="3f878-122">В шаблонах DDD следует инкапсулируют поведение домена и правил в класс сущностей, благодаря чему можно контролировать инварианты, проверки и правила, при доступе к любой коллекции.</span><span class="sxs-lookup"><span data-stu-id="3f878-122">Per DDD patterns, you should encapsulate domain behavior and rules within the entity class itself, so it can control invariants, validations, and rules when accessing any collection.</span></span> <span data-ttu-id="3f878-123">Таким образом это не рекомендуется в ддд, чтобы разрешить общий доступ к коллекции дочерних сущностей или объектов значение.</span><span class="sxs-lookup"><span data-stu-id="3f878-123">Therefore, it is not a good practice in DDD to allow public access to collections of child entities or value objects.</span></span> <span data-ttu-id="3f878-124">Вместо этого необходимо предоставлять методы, определяющие, как и когда поля и коллекциях свойств могут обновляться, и какое поведение, а также действия должно выполняться, когда это происходит.</span><span class="sxs-lookup"><span data-stu-id="3f878-124">Instead, you want to expose methods that control how and when your fields and property collections can be updated, and what behavior and actions should occur when that happens.</span></span>

<span data-ttu-id="3f878-125">В EF Core 1.1 для удовлетворения этих требований DDD могут иметь простых полей в сущностях вместо свойств с помощью открытые и закрытые методы задания.</span><span class="sxs-lookup"><span data-stu-id="3f878-125">In EF Core 1.1, to satisfy those DDD requirements you can have plain fields in your entities instead of properties with public and private setters.</span></span> <span data-ttu-id="3f878-126">Если не хотите, чтобы поле сущности для будет доступен, достаточно просто создать атрибут или поле, а не свойства.</span><span class="sxs-lookup"><span data-stu-id="3f878-126">If you do not want an entity field to be externally accessible, you can just create the attribute or field instead of a property.</span></span> <span data-ttu-id="3f878-127">Нет необходимости использовать частного задания, если вы предпочитаете такой подход очистки.</span><span class="sxs-lookup"><span data-stu-id="3f878-127">There is no need to use private setters if you prefer this cleaner approach.</span></span>

<span data-ttu-id="3f878-128">Аналогичным образом, теперь вы можете открыть доступ только для чтения к коллекциям с помощью открытые свойства, типизированное как IEnumerable&lt;T&gt;, который резервируется членом закрытое поле для коллекции (такие как список&lt;&gt;) в вашей сущность, использующая EF для сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="3f878-128">In a similar way, you can now have read-only access to collections by using a public property typed as IEnumerable&lt;T&gt;, which is backed by a private field member for the collection (like a List&lt;&gt;) in your entity that relies on EF for persistence.</span></span> <span data-ttu-id="3f878-129">Предыдущие версии платформы Entity Framework требуют наличия свойства коллекции для поддержки ICollection&lt;T&gt;, которой означает, что любому разработчику, использующему родительского класса сущности может добавлять или удалять элементы из коллекции его свойства.</span><span class="sxs-lookup"><span data-stu-id="3f878-129">Previous versions of Entity Framework required collection properties to support ICollection&lt;T&gt;, which meant that any developer using the parent entity class could add or remove items from its property collections.</span></span> <span data-ttu-id="3f878-130">Чтобы можно было бы от рекомендуемых шаблонов в ддд.</span><span class="sxs-lookup"><span data-stu-id="3f878-130">That possibility would be against the recommended patterns in DDD.</span></span>

<span data-ttu-id="3f878-131">Можно использовать частной коллекции при предоставлении доступа к объект IEnumerable, только для чтения, как показано в следующем примере кода:</span><span class="sxs-lookup"><span data-stu-id="3f878-131">You can use a private collection while exposing a read-only IEnumerable object, as shown in the following code example:</span></span>

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...
    private readonly List<OrderItem> _orderItems;

    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        // Initializations ...
    }

    public void AddOrderItem(int productId, string productName,
        decimal unitPrice, decimal discount,
        string pictureUrl, int units = 1)
    {
        // Validation logic...
        var orderItem = new OrderItem(productId, productName, unitPrice, discount,
            pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

<span data-ttu-id="3f878-132">Обратите внимание, что свойство OrderItems только доступно только для чтения с помощью списка&lt;&gt;. AsReadOnly().</span><span class="sxs-lookup"><span data-stu-id="3f878-132">Note that the OrderItems property can only be accessed as read-only using List&lt;&gt;.AsReadOnly().</span></span> <span data-ttu-id="3f878-133">Этот метод создает оболочку закрытого списка только для чтения, чтобы он защищен от внешних обновлений.</span><span class="sxs-lookup"><span data-stu-id="3f878-133">This method creates a read-only wrapper around the private list so that it is protected against external updates.</span></span> <span data-ttu-id="3f878-134">Это значительно дешевле, чем с помощью метода ToList, так как не включает копирование всех элементов в коллекции; Вместо этого он выполняет только для одной операции выделения кучи для экземпляра оболочки.</span><span class="sxs-lookup"><span data-stu-id="3f878-134">It is much cheaper than using the ToList method, because it does not have to copy all the items in a new collection; instead, it performs just one heap alloc operation for the wrapper instance.</span></span>

<span data-ttu-id="3f878-135">EF Core предоставляет способ для сопоставления модели домена физическую базу данных без что засоряет модели домена.</span><span class="sxs-lookup"><span data-stu-id="3f878-135">EF Core provides a way to map the domain model to the physical database without contaminating the domain model.</span></span> <span data-ttu-id="3f878-136">Это чисто .NET POCO код, так как сопоставление это реализовано в уровне сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="3f878-136">It is pure .NET POCO code, because the mapping action is implemented in the persistence layer.</span></span> <span data-ttu-id="3f878-137">В данному действию сопоставления необходимо настроить сопоставления полей для базы данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-137">In that mapping action, you need to configure the fields-to-database mapping.</span></span> <span data-ttu-id="3f878-138">В следующем примере метод OnModelCreating выделенный код сообщает EF ядер и доступ к свойству OrderItems через его поля.</span><span class="sxs-lookup"><span data-stu-id="3f878-138">In the following example of an OnModelCreating method, the highlighted code tells EF Core to access the OrderItems property through its field.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // ...
    modelBuilder.Entity<Order>(ConfigureOrder);
    // Other entities ...
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    // Other configuration ...
    var navigation = orderConfiguration.Metadata.
    FindNavigation(nameof(Order.OrderItems));
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);
    // Other configuration ...
}
```

<span data-ttu-id="3f878-139">При использовании полей вместо свойств сущности OrderItem сохраняется, как если бы оно находилось список&lt;OrderItem&gt; свойство.</span><span class="sxs-lookup"><span data-stu-id="3f878-139">When you use fields instead of properties, the OrderItem entity is persisted just as if it had a List&lt;OrderItem&gt; property.</span></span> <span data-ttu-id="3f878-140">Однако он предоставляет один метод доступа (метод AddOrderItem) для добавления новых элементов в порядке.</span><span class="sxs-lookup"><span data-stu-id="3f878-140">However, it exposes a single accessor (the AddOrderItem method) for adding new items to the order.</span></span> <span data-ttu-id="3f878-141">В результате поведение и данных связаны друг с другом и будет несогласованной в код приложения, использующего модель домена.</span><span class="sxs-lookup"><span data-stu-id="3f878-141">As a result, behavior and data are tied together and will be consistent throughout any application code that uses the domain model.</span></span>

## <a name="implementing-custom-repositories-with-entity-framework-core"></a><span data-ttu-id="3f878-142">Реализация пользовательских репозиториев с Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="3f878-142">Implementing custom repositories with Entity Framework Core</span></span>

<span data-ttu-id="3f878-143">На уровне реализации репозитория является просто классом с кодом сохраняемости данных, координируемое единица работы (DBContext ядра EF) при выполнении обновления, как показано в следующем классе:</span><span class="sxs-lookup"><span data-stu-id="3f878-143">At the implementation level, a repository is simply a class with data persistence code coordinated by a unit of work (DBContext in EF Core) when performing updates, as shown in the following class:</span></span>

```csharp
// using statements...
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class BuyerRepository : IBuyerRepository
    {
        private readonly OrderingContext _context;

        public IUnitOfWork UnitOfWork
        {
            get
            {
                return _context;
            }
        }
    }

    public BuyerRepository(OrderingContext context)
    {
        if (context == null)
        {
            throw new ArgumentNullException(
                nameof(context));
        }
        _context = context;
    }

    public Buyer Add(Buyer buyer)
    {
        return _context.Buyers.Add(buyer).Entity;
    }

    public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
    {
        var buyer = await _context.Buyers.Include(b => b.Payments)
            .Where(b => b.FullName == BuyerIdentityGuid)
            .SingleOrDefaultAsync();
        return buyer;
    }
}
```

<span data-ttu-id="3f878-144">Обратите внимание, что интерфейс IBuyerRepository поступают из уровня модели домена.</span><span class="sxs-lookup"><span data-stu-id="3f878-144">Note that the IBuyerRepository interface comes from the domain model layer.</span></span> <span data-ttu-id="3f878-145">Однако реализация репозитория выполняется в сохраняемости и уровень инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3f878-145">However, the repository implementation is done at the persistence and infrastructure layer.</span></span>

<span data-ttu-id="3f878-146">EF DbContext поступает через конструктор через внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="3f878-146">The EF DbContext comes through the constructor through Dependency Injection.</span></span> <span data-ttu-id="3f878-147">Используется совместно несколькими репозиториями внутри одной области запроса HTTP, благодаря существования по умолчанию (ServiceLifetime.Scoped) в контейнер IoC (их можно также явно задать со службами. AddDbContext&lt;&gt;).</span><span class="sxs-lookup"><span data-stu-id="3f878-147">It is shared between multiple repositories within the same HTTP request scope, thanks to its default lifetime (ServiceLifetime.Scoped) in the IoC container (which can also be explicitly set with services.AddDbContext&lt;&gt;).</span></span>

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a><span data-ttu-id="3f878-148">Методы, реализуемые в репозитории (обновления или транзакций и запросы)</span><span class="sxs-lookup"><span data-stu-id="3f878-148">Methods to implement in a repository (updates or transactions versus queries)</span></span>

<span data-ttu-id="3f878-149">В каждом классе репозитория следует разместить методы сохраняемости, обновляющих состояние сущности его связанные агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="3f878-149">Within each repository class, you should put the persistence methods that update the state of entities contained by its related aggregate.</span></span> <span data-ttu-id="3f878-150">Помните, что имеется однозначное соответствие между статистическое выражение и его связанные репозитория.</span><span class="sxs-lookup"><span data-stu-id="3f878-150">Remember there is one-to-one relationship between an aggregate and its related repository.</span></span> <span data-ttu-id="3f878-151">Принять во внимание, что объект сущности статистические корневой могут внедрять дочерних сущностей в его графе EF.</span><span class="sxs-lookup"><span data-stu-id="3f878-151">Take into account that an aggregate root entity object might have embedded child entities within its EF graph.</span></span> <span data-ttu-id="3f878-152">Например покупатель может быть несколько способов оплаты связанных дочерних сущностей.</span><span class="sxs-lookup"><span data-stu-id="3f878-152">For example, a buyer might have multiple payment methods as related child entities.</span></span>

<span data-ttu-id="3f878-153">Поскольку подход для упорядочивания микрослужбу в eShopOnContainers также основана на CQS/CQRS, большинство запросов не реализованы в пользовательские репозитории.</span><span class="sxs-lookup"><span data-stu-id="3f878-153">Since the approach for the ordering microservice in eShopOnContainers is also based on CQS/CQRS, most of the queries are not implemented in custom repositories.</span></span> <span data-ttu-id="3f878-154">Разработчики имеют возможность создавать запросы и соединения, необходимые для уровня представления без ограничений, установленных для статистических выражений, пользовательские репозитории каждого статистического выражения и DDD в целом.</span><span class="sxs-lookup"><span data-stu-id="3f878-154">Developers have the freedom to create the queries and joins they need for the presentation layer without the restrictions imposed by aggregates, custom repositories per aggregate, and DDD in general.</span></span> <span data-ttu-id="3f878-155">Большинство пользовательских репозиториев, предлагаемые в данном руководстве имеют несколько обновлений или методы транзакций, но только методы запросов, необходимых для получения данных для обновления.</span><span class="sxs-lookup"><span data-stu-id="3f878-155">Most of the custom repositories suggested by this guide have several update or transactional methods but just the query methods needed to get data to be updated.</span></span> <span data-ttu-id="3f878-156">Например репозитории BuyerRepository реализует метод FindAsync, так как приложению нужно знать, существует ли определенный покупатель перед созданием нового покупатель порядка.</span><span class="sxs-lookup"><span data-stu-id="3f878-156">For example, the BuyerRepository repository implements a FindAsync method, because the application needs to know whether a particular buyer exists before creating a new buyer related to the order.</span></span>

<span data-ttu-id="3f878-157">Однако методы реальные запросов для получения данных для отправки презентации слоя или клиентского приложения реализации, как упоминалось в CQRS запросы, основанные на гибкие запросы, с помощью Dapper.</span><span class="sxs-lookup"><span data-stu-id="3f878-157">However, the real query methods to get data to send to the presentation layer or client apps are implemented, as mentioned, in the CQRS queries based on flexible queries using Dapper.</span></span>

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a><span data-ttu-id="3f878-158">С помощью пользовательского репозитория или непосредственно с помощью EF DbContext</span><span class="sxs-lookup"><span data-stu-id="3f878-158">Using a custom repository versus using EF DbContext directly</span></span>

<span data-ttu-id="3f878-159">Класс Entity Framework DbContext основана на шаблонах единицей работы и репозитория, а также можно использовать напрямую из кода приложения, такие как с помощью контроллера ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="3f878-159">The Entity Framework DbContext class is based on the Unit of Work and Repository patterns, and can be used directly from your code, such as from an ASP.NET Core MVC controller.</span></span> <span data-ttu-id="3f878-160">То есть способ вы можете создать простой код, как микрослужбу каталога CRUD в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3f878-160">That is the way you can create the simplest code, as in the CRUD catalog microservice in eShopOnContainers.</span></span> <span data-ttu-id="3f878-161">В случаях возникает необходимость простой кода невозможно можно непосредственно с помощью класса DbContext, как и многие разработчики.</span><span class="sxs-lookup"><span data-stu-id="3f878-161">In cases where you want the simplest code possible, you might want to directly use the DbContext class, as many developers do.</span></span>

<span data-ttu-id="3f878-162">Однако реализация пользовательских репозиториев предоставляет несколько преимуществ при реализации более сложной микрослужбами или приложений.</span><span class="sxs-lookup"><span data-stu-id="3f878-162">However, implementing custom repositories provides several benefits when implementing more complex microservices or applications.</span></span> <span data-ttu-id="3f878-163">Единица работы и репозитория шаблоны предназначены для инкапсуляции уровень сохраняемости инфраструктуры, поэтому оно связано с уровнями модели домена приложения и.</span><span class="sxs-lookup"><span data-stu-id="3f878-163">The Unit of Work and Repository patterns are intended to encapsulate the infrastructure persistence layer so it is decoupled from the application and domain model layers.</span></span> <span data-ttu-id="3f878-164">Реализация этих шаблонах позволяет упростить использование макетов репозиториев имитация доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-164">Implementing these patterns can facilitate the use of mock repositories simulating access to the database.</span></span>

<span data-ttu-id="3f878-165">На рисунке 9-18 можно увидеть различия между не с помощью репозиториев (непосредственно с помощью EF DbContext) сравнению с репозиториев, которые облегчают макета таких репозиториев.</span><span class="sxs-lookup"><span data-stu-id="3f878-165">In Figure 9-18 you can see the differences between not using repositories (directly using the EF DbContext) versus using repositories which make it easier to mock those repositories.</span></span>

![](./media/image19.png)

<span data-ttu-id="3f878-166">**На рисунке 9-18**.</span><span class="sxs-lookup"><span data-stu-id="3f878-166">**Figure 9-18**.</span></span> <span data-ttu-id="3f878-167">С помощью пользовательских репозиториев и простой DbContext</span><span class="sxs-lookup"><span data-stu-id="3f878-167">Using custom repositories versus a plain DbContext</span></span>

<span data-ttu-id="3f878-168">Существует несколько вариантов при имитации.</span><span class="sxs-lookup"><span data-stu-id="3f878-168">There are multiple alternatives when mocking.</span></span> <span data-ttu-id="3f878-169">Удалось макета просто репозиториев или удалось макета всей единица работы.</span><span class="sxs-lookup"><span data-stu-id="3f878-169">You could mock just repositories or you could mock a whole unit of work.</span></span> <span data-ttu-id="3f878-170">Обычно имитации просто репозиториев достаточно и сложности для выделения и макета всей единица работы обычно не требуется.</span><span class="sxs-lookup"><span data-stu-id="3f878-170">Usually mocking just the repositories is enough, and the complexity to abstract and mock a whole unit of work is usually not needed.</span></span>

<span data-ttu-id="3f878-171">Позже когда мы сосредоточим внимание на уровне приложения, вы увидите как работает внедрение зависимостей в ASP.NET Core, и его реализация при использовании репозиториев.</span><span class="sxs-lookup"><span data-stu-id="3f878-171">Later, when we focus on the application layer, you will see how Dependency Injection works in ASP.NET Core and how it is implemented when using repositories.</span></span>

<span data-ttu-id="3f878-172">Иными словами пользовательские репозитории позволяют упростить тестирование кода с модульными тестами, которые не влияет на состояние уровня данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-172">In short, custom repositories allow you to test code more easily with unit tests that are not impacted by the data tier state.</span></span> <span data-ttu-id="3f878-173">При выполнении тестов, которые также обращаться к реальной базы данных через Entity Framework, они не являются модульные тесты, но интеграции тестов, которые выполняются гораздо медленнее.</span><span class="sxs-lookup"><span data-stu-id="3f878-173">If you run tests that also access the actual database through the Entity Framework, they are not unit tests but integration tests, which are a lot slower.</span></span>

<span data-ttu-id="3f878-174">Если вы использовали непосредственно DbContext, единственным вариантом нужно было бы будет для выполнения модульных тестов с помощью SQL Server в памяти с прогнозируемых данных для модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="3f878-174">If you were using DbContext directly, the only choice you would have would be to run unit tests by using an in-memory SQL Server with predictable data for unit tests.</span></span> <span data-ttu-id="3f878-175">Управлять таким же образом на уровне репозитория макетов объектов и фальшивых данных будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="3f878-175">You would not be able to control mock objects and fake data in the same way at the repository level.</span></span> <span data-ttu-id="3f878-176">Конечно вы всегда тестировать контроллеров MVC.</span><span class="sxs-lookup"><span data-stu-id="3f878-176">Of course, you could always test the MVC controllers.</span></span>

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="3f878-177">Время существования экземпляра EF DbContext и IUnitOfWork в контейнер IoC</span><span class="sxs-lookup"><span data-stu-id="3f878-177">EF DbContext and IUnitOfWork instance lifetime in your IoC container</span></span>

<span data-ttu-id="3f878-178">Объект DbContext (доступный в виде объекта IUnitOfWork), необходимо быть общим для нескольких репозиториев в той же области запроса HTTP.</span><span class="sxs-lookup"><span data-stu-id="3f878-178">The DbContext object (exposed as an IUnitOfWork object) might need to be shared among multiple repositories within the same HTTP request scope.</span></span> <span data-ttu-id="3f878-179">Например, это справедливо при выполняемой операции приходится иметь дело с нескольких статистических выражений или просто потому, что вы используете несколько экземпляров репозитория.</span><span class="sxs-lookup"><span data-stu-id="3f878-179">For example, this is true when the operation being executed must deal with multiple aggregates, or simply because you are using multiple repository instances.</span></span> <span data-ttu-id="3f878-180">Это также необходимо упомянуть, интерфейс IUnitOfWork входит в состав домена, а не тип EF.</span><span class="sxs-lookup"><span data-stu-id="3f878-180">It is also important to mention that the IUnitOfWork interface is part of the domain, not an EF type.</span></span>

<span data-ttu-id="3f878-181">Для этого экземпляра объекта DbContext должна иметь время существования службы присвоено значение ServiceLifetime.Scoped.</span><span class="sxs-lookup"><span data-stu-id="3f878-181">In order to do that, the instance of the DbContext object has to have its service lifetime set to ServiceLifetime.Scoped.</span></span> <span data-ttu-id="3f878-182">Это время жизни по умолчанию, когда регистрация DbContext с службы. AddDbContext в контейнер IoC из метода ConfigureServices файла Startup.cs файла в проекте веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3f878-182">This is the default lifetime when registering a DbContext with services.AddDbContext in your IoC container from the ConfigureServices method of the Startup.cs file in your ASP.NET Core Web API project.</span></span> <span data-ttu-id="3f878-183">Это проиллюстрировано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="3f878-183">The following code illustrates this.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc(options =>
    {
        options.Filters.Add(typeof(HttpGlobalExceptionFilter));
    }).AddControllersAsServices();

    services.AddEntityFrameworkSqlServer()
    .AddDbContext<OrderingContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlop => sqlop.MigrationsAssembly(typeof(Startup).GetTypeInfo().
        Assembly.GetName().Name));
    },
    ServiceLifetime.Scoped // Note that Scoped is the default choice
    // in AddDbContext. It is shown here only for
    // pedagogic purposes.
    );
}
```

<span data-ttu-id="3f878-184">Не следует настраивать режим при создании экземпляра DbContext как ServiceLifetime.Transient или ServiceLifetime.Singleton.</span><span class="sxs-lookup"><span data-stu-id="3f878-184">The DbContext instantiation mode should not be configured as ServiceLifetime.Transient or ServiceLifetime.Singleton.</span></span>

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a><span data-ttu-id="3f878-185">Время существования экземпляра репозитория в контейнер IoC</span><span class="sxs-lookup"><span data-stu-id="3f878-185">The repository instance lifetime in your IoC container</span></span>

<span data-ttu-id="3f878-186">Аналогичным образом время существования репозитория обычно должна быть задана как области (InstancePerLifetimeScope в Autofac).</span><span class="sxs-lookup"><span data-stu-id="3f878-186">In a similar way, repository’s lifetime should usually be set as scoped (InstancePerLifetimeScope in Autofac).</span></span> <span data-ttu-id="3f878-187">Также это может быть временной (InstancePerDependency в Autofac), но служба будет более эффективным в отношении памяти, при использовании с областью времени существования.</span><span class="sxs-lookup"><span data-stu-id="3f878-187">It could also be transient (InstancePerDependency in Autofac), but your service will be more efficient in regards memory when using the scoped lifetime.</span></span>

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

<span data-ttu-id="3f878-188">Следует отметить, что время жизни singleton для репозитория может привести к вам параллелизма серьезных проблем при вашей DbContext равно времени существования (InstancePerLifetimeScope) (по умолчанию время существования для DBContext) в области видимости.</span><span class="sxs-lookup"><span data-stu-id="3f878-188">Note that using the singleton lifetime for the repository could cause you serious concurrency problems when your DbContext is set to scoped (InstancePerLifetimeScope) lifetime (the default lifetimes for a DBContext).</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="3f878-189">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="3f878-189">Additional resources</span></span>

-   <span data-ttu-id="3f878-190">**Реализация репозитория и единицы шаблонов рабочих элементов в приложении ASP.NET MVC**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span><span class="sxs-lookup"><span data-stu-id="3f878-190">**Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application**
[*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)</span></span>

-   <span data-ttu-id="3f878-191">**Аллен Джонатан. Стратегии реализации для репозитория с Entity Framework Dapper, шаблон и прикрепить**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span><span class="sxs-lookup"><span data-stu-id="3f878-191">**Jonathan Allen. Implementation Strategies for the Repository Pattern with Entity Framework, Dapper, and Chain**
[*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)</span></span>

-   <span data-ttu-id="3f878-192">**Сезар де ла Торре (Cesar de la Torre). Сравнение времени существования службы контейнер ASP.NET Core IoC с областями экземпляр контейнер Autofac IoC**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span><span class="sxs-lookup"><span data-stu-id="3f878-192">**Cesar de la Torre. Comparing ASP.NET Core IoC container service lifetimes with Autofac IoC container instance scopes**
[*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)</span></span>

## <a name="table-mapping"></a><span data-ttu-id="3f878-193">Сопоставление таблиц</span><span class="sxs-lookup"><span data-stu-id="3f878-193">Table mapping</span></span>

<span data-ttu-id="3f878-194">Сопоставление таблиц определяет данные таблицы должны запрашиваться из и сохранены в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-194">Table mapping identifies the table data to be queried from and saved to the database.</span></span> <span data-ttu-id="3f878-195">Ранее было показано, как сущности домена (например, домен продукта или заказа) может использоваться для создания схемы связанной базы данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-195">Previously you saw how domain entities (for example, a product or order domain) can be used to generate a related database schema.</span></span> <span data-ttu-id="3f878-196">EF строго построена на концепции *соглашения*.</span><span class="sxs-lookup"><span data-stu-id="3f878-196">EF is strongly designed around the concept of *conventions*.</span></span> <span data-ttu-id="3f878-197">Соглашения о решать вопросы, например «Как имя таблицы будет?»</span><span class="sxs-lookup"><span data-stu-id="3f878-197">Conventions address questions like “What will the name of a table be?”</span></span> <span data-ttu-id="3f878-198">или «какое свойство является первичным ключом?»</span><span class="sxs-lookup"><span data-stu-id="3f878-198">or “What property is the primary key?”</span></span> <span data-ttu-id="3f878-199">Соглашения обычно основаны на обычные имена — например, он является типичным для первичного ключа, как свойство, которое заканчивается на идентификатор.</span><span class="sxs-lookup"><span data-stu-id="3f878-199">Conventions are typically based on conventional names—for example, it is typical for the primary key to be a property that ends with Id.</span></span>

<span data-ttu-id="3f878-200">По соглашению, каждая сущность будет настроен для сопоставления с таблицей с тем же именем, что DbSet&lt;TEntity&gt; свойство, которое предоставляет сущности в контексте производной.</span><span class="sxs-lookup"><span data-stu-id="3f878-200">By convention, each entity will be set up to map to a table with the same name as the DbSet&lt;TEntity&gt; property that exposes the entity on the derived context.</span></span> <span data-ttu-id="3f878-201">Если не DbSet&lt;TEntity&gt; значение предоставляется для заданной сущности, используется имя класса.</span><span class="sxs-lookup"><span data-stu-id="3f878-201">If no DbSet&lt;TEntity&gt; value is provided for the given entity, the class name is used.</span></span>

### <a name="data-annotations-versus-fluent-api"></a><span data-ttu-id="3f878-202">Заметок к данным или Fluent API</span><span class="sxs-lookup"><span data-stu-id="3f878-202">Data Annotations versus Fluent API</span></span>

<span data-ttu-id="3f878-203">Существует множество дополнительных соглашения EF Core, и большинство из них может быть изменен с помощью заметок к данным или Fluent API-Интерфейс, реализованный в методе OnModelCreating.</span><span class="sxs-lookup"><span data-stu-id="3f878-203">There are many additional EF Core conventions, and most of them can be changed by using either data annotations or Fluent API, implemented within the OnModelCreating method.</span></span>

<span data-ttu-id="3f878-204">Заметок к данным необходимо использовать в классы сущностей модели самостоятельно, что является более активное вмешательство с точки зрения DDD способом.</span><span class="sxs-lookup"><span data-stu-id="3f878-204">Data annotations must be used on the entity model classes themselves, which is a more intrusive way from a DDD point of view.</span></span> <span data-ttu-id="3f878-205">Это происходит потому что засоряет модели с заметками данные, относящиеся к базе данных инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3f878-205">This is because you are contaminating your model with data annotations related to the infrastructure database.</span></span> <span data-ttu-id="3f878-206">С другой стороны Fluent API является удобным способом изменить большинство соглашения и сопоставления в вашей инфраструктуре уровень сохраняемости данных, таким образом модели сущности, очистить и отделенный от инфраструктуры сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="3f878-206">On the other hand, Fluent API is a convenient way to change most conventions and mappings within your data persistence infrastructure layer, so the entity model will be clean and decoupled from the persistence infrastructure.</span></span>

### <a name="fluent-api-and-the-onmodelcreating-method"></a><span data-ttu-id="3f878-207">Fluent API и методе OnModelCreating</span><span class="sxs-lookup"><span data-stu-id="3f878-207">Fluent API and the OnModelCreating method</span></span>

<span data-ttu-id="3f878-208">Как уже упоминалось, чтобы изменить сопоставления и соглашения можно использовать метод OnModelCreating класса DbContext.</span><span class="sxs-lookup"><span data-stu-id="3f878-208">As mentioned, in order to change conventions and mappings, you can use the OnModelCreating method in the DbContext class.</span></span> <span data-ttu-id="3f878-209">В следующем примере показано, как это делается в упорядочивания микрослужбу в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="3f878-209">The following example shows how we do this in the ordering microservice in eShopOnContainers.</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    //Other entities
    modelBuilder.Entity<OrderStatus>(ConfigureOrderStatus);
    //Other entities
}

void ConfigureOrder(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Property(o => o.Id).ForSqlServerUseSequenceHiLo("orderseq", DEFAULT_SCHEMA);
    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    orderConfiguration.Property<string>("Street").IsRequired();
    orderConfiguration.Property<string>("State").IsRequired();
    orderConfiguration.Property<string>("City").IsRequired();
    orderConfiguration.Property<string>("ZipCode").IsRequired();
    orderConfiguration.Property<string>("Country").IsRequired();
    orderConfiguration.Property<int>("BuyerId").IsRequired();
    orderConfiguration.Property<int>("OrderStatusId").IsRequired();
    orderConfiguration.Property<int>("PaymentMethodId").IsRequired();

    var navigation =
    orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));
    // DDD Patterns comment:
    // Set as Field (new since EF 1.1) to access
    // the OrderItem collection property as a field
    navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

    orderConfiguration.HasOne(o => o.PaymentMethod)
        .WithMany()
        .HasForeignKey("PaymentMethodId")
        .OnDelete(DeleteBehavior.Restrict);
        orderConfiguration.HasOne(o => o.Buyer)
        .WithMany()
        .HasForeignKey("BuyerId");
        orderConfiguration.HasOne(o => o.OrderStatus)
        .WithMany()
        .HasForeignKey("OrderStatusId");
}
```

<span data-ttu-id="3f878-210">Можно задать все сопоставления Fluent API в один и тот же метод OnModelCreating, но рекомендуется для разделения кода и имеют несколько submethods, по одному на сущности, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="3f878-210">You could set all the Fluent API mappings within the same OnModelCreating method, but it is advisable to partition that code and have multiple submethods, one per entity, as shown in the example.</span></span> <span data-ttu-id="3f878-211">Для моделей, особенно большой он даже может рекомендуется иметь отдельным файлам исходного кода (статические классы) для настройки различных типов сущностей.</span><span class="sxs-lookup"><span data-stu-id="3f878-211">For particularly large models, it can even be advisable to have separate source files (static classes) for configuring different entity types.</span></span>

<span data-ttu-id="3f878-212">Код в примере является явным.</span><span class="sxs-lookup"><span data-stu-id="3f878-212">The code in the example is explicit.</span></span> <span data-ttu-id="3f878-213">EF Core соглашения выполнить, большая часть этой автоматически, поэтому фактический код, необходимо написать для достижения то же самое будет намного меньше.</span><span class="sxs-lookup"><span data-stu-id="3f878-213">However, EF Core conventions do most of this automatically, so the actual code you would need to write to achieve the same thing would be much smaller.</span></span>

### <a name="the-hilo-algorithm-in-ef-core"></a><span data-ttu-id="3f878-214">Алгоритм Hi/Lo EF ядра</span><span class="sxs-lookup"><span data-stu-id="3f878-214">The Hi/Lo algorithm in EF Core</span></span>

<span data-ttu-id="3f878-215">Интересным аспектом кода в предыдущем примере является применение [алгоритм Hi/Lo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) в рамках стратегии создания ключей.</span><span class="sxs-lookup"><span data-stu-id="3f878-215">An interesting aspect of code in the preceding example is that it uses the [Hi/Lo algorithm](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) as the key generation strategy.</span></span>

<span data-ttu-id="3f878-216">Алгоритм Hi/Lo полезен в тех случаях, когда требуется уникальные ключи.</span><span class="sxs-lookup"><span data-stu-id="3f878-216">The Hi/Lo algorithm is useful when you need unique keys.</span></span> <span data-ttu-id="3f878-217">В сводке алгоритм Hi-Lo присваивает уникальные идентификаторы строк таблицы пока не в зависимости от немедленно хранения строк в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-217">As a summary, the Hi-Lo algorithm assigns unique identifiers to table rows while not depending on storing the row in the database immediately.</span></span> <span data-ttu-id="3f878-218">Это позволяет запустить прямо сейчас, используя идентификаторы, как происходит с обычной базой данных последовательные идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="3f878-218">This lets you start using the identifiers right away, as happens with regular sequential database IDs.</span></span>

<span data-ttu-id="3f878-219">Алгоритм Hi/Lo описывает механизм для создания безопасного ID на стороне клиента, а не в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-219">The Hi/Lo algorithm describes a mechanism for generating safe IDs on the client side rather than in the database.</span></span> <span data-ttu-id="3f878-220">*Безопасный* в данном контексте означает без конфликтов.</span><span class="sxs-lookup"><span data-stu-id="3f878-220">*Safe* in this context means without collisions.</span></span> <span data-ttu-id="3f878-221">Этот алгоритм является интересные по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="3f878-221">This algorithm is interesting for these reasons:</span></span>

-   <span data-ttu-id="3f878-222">Он не прерывает шаблон единицу работы.</span><span class="sxs-lookup"><span data-stu-id="3f878-222">It does not break the Unit of Work pattern.</span></span>

-   <span data-ttu-id="3f878-223">Не требуется выполнять циклов приема-передачи генераторы последовательности как в других СУБД.</span><span class="sxs-lookup"><span data-stu-id="3f878-223">It does not require round trips the way sequence generators do in other DBMSs.</span></span>

-   <span data-ttu-id="3f878-224">Он создает удобочитаемый идентификатор, в отличие от методов, которые используют идентификаторы GUID.</span><span class="sxs-lookup"><span data-stu-id="3f878-224">It generates a human readable identifier, unlike techniques that use GUIDs.</span></span>

<span data-ttu-id="3f878-225">EF Core поддерживает [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) с помощью метода ForSqlServerUseSequenceHiLo, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="3f878-225">EF Core supports [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) with the ForSqlServerUseSequenceHiLo method, as shown in the preceding example.</span></span>

### <a name="mapping-fields-instead-of-properties"></a><span data-ttu-id="3f878-226">Сопоставление полей вместо свойств</span><span class="sxs-lookup"><span data-stu-id="3f878-226">Mapping fields instead of properties</span></span>

<span data-ttu-id="3f878-227">С помощью функции EF Core 1.1, которая сопоставляет столбцы с полями можно не использовать какие-либо свойства в класс сущностей и просто для сопоставления столбцов таблицы с полями.</span><span class="sxs-lookup"><span data-stu-id="3f878-227">With the feature of EF Core 1.1 that maps columns to fields, it is possible to not use any properties in the entity class, and just to map columns from a table to fields.</span></span> <span data-ttu-id="3f878-228">Обычно используются, будет закрытым полям для любого внутреннего состояния, которые не обязательно должны быть доступны извне сущности.</span><span class="sxs-lookup"><span data-stu-id="3f878-228">A common use for that would be private fields for any internal state that do not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="3f878-229">EF 1.1 поддерживает сопоставление поля без связанного свойства со столбцом в базе данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-229">EF 1.1 supports a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="3f878-230">Это можно сделать с одного поля или также коллекций, такие как список&lt; &gt; поля.</span><span class="sxs-lookup"><span data-stu-id="3f878-230">You can do this with single fields or also with collections, like a List&lt;&gt; field.</span></span> <span data-ttu-id="3f878-231">Эта точка упомянутая ранее, когда мы рассмотрели моделирования классы модели домена, но здесь можно увидеть, как это сопоставление выполняется с конфигурацией PropertyAccessMode.Field, выделяются в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="3f878-231">This point was mentioned earlier when we discussed modeling the domain model classes, but here you can see how that mapping is performed with the PropertyAccessMode.Field configuration highlighted in the previous code.</span></span>

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a><span data-ttu-id="3f878-232">С помощью замещения свойств в объектах значение скрытого удостоверений на уровне инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="3f878-232">Using shadow properties in value objects for hidden IDs at the infrastructure level</span></span>

<span data-ttu-id="3f878-233">Свойства, которые не существуют в модели сущности класса свойства тени EF ядра:</span><span class="sxs-lookup"><span data-stu-id="3f878-233">Shadow properties in EF Core are properties that do not exist in your entity class model.</span></span> <span data-ttu-id="3f878-234">Значения и состояния эти свойства сохраняются только в [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) класса на уровне инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3f878-234">The values and states of these properties are maintained purely in the [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) class at the infrastructure level.</span></span>

<span data-ttu-id="3f878-235">С точки зрения DDD замещения свойств — удобный способ реализации значение объектов, скрывая ID в качестве первичного ключа свойства тени.</span><span class="sxs-lookup"><span data-stu-id="3f878-235">From a DDD point of view, shadow properties are a convenient way to implement value objects by hiding the ID as a shadow property primary key.</span></span> <span data-ttu-id="3f878-236">Это важно, так как объект значения не следует идентификаторов (по крайней мере, не должно быть идентификатор в уровне модели домена при формировании значения объектов).</span><span class="sxs-lookup"><span data-stu-id="3f878-236">This is important, because a value object should not have identity (at least, you should not have the ID in the domain model layer when shaping value objects).</span></span> <span data-ttu-id="3f878-237">Это значит, начиная с текущей версии ядра EF EF Core у способ реализации объектов значение как [сложных типов](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), насколько это возможно в EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="3f878-237">The point here is that as of the current version of EF Core, EF Core does not have a way to implement value objects as [complex types](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), as is possible in EF 6.x.</span></span> <span data-ttu-id="3f878-238">Именно поэтому в настоящее время необходимо реализовать объект значения, как сущность с Идентификатором скрытый (первичный ключ) установлено в качестве свойства тени.</span><span class="sxs-lookup"><span data-stu-id="3f878-238">That is why you currently need to implement a value object as an entity with a hidden ID (primary key) set as a shadow property.</span></span>

<span data-ttu-id="3f878-239">Как видно в [объект значение адреса](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) в eShopOnContainers, в модели адрес отсутствует идентификатор:</span><span class="sxs-lookup"><span data-stu-id="3f878-239">As you can see in the [Address value object](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) in eShopOnContainers, in the Address model you do not see an ID:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }
    //Constructor initializing, etc
}
```

<span data-ttu-id="3f878-240">Но на самом деле, необходимо указать ИД таким образом, чтобы основные EF возможность сохранить эти данные в таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="3f878-240">But under the covers, we need to provide an ID so that EF Core is able to persist this data in the database tables.</span></span> <span data-ttu-id="3f878-241">Что мы делаем в методе ConfigureAddress [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) класса на уровне инфраструктуры, поэтому мы не засоряет моделью домена с кодом EF инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="3f878-241">We do that in the ConfigureAddress method of the [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) class at the infrastructure level, so we do not pollute the domain model with EF infrastructure code.</span></span>

```csharp
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    // DDD pattern comment:
    // Implementing the Address ID as a shadow property, because the
    // address is a value object and an identity is not required for a
    // value object
    // EF Core just needs the ID so it can store it in a database table
    // See: https://docs.microsoft.com/ef/core/modeling/shadow-properties
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

#### <a name="additional-resources"></a><span data-ttu-id="3f878-242">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="3f878-242">Additional resources</span></span>

-   <span data-ttu-id="3f878-243">**Таблица сопоставления**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span><span class="sxs-lookup"><span data-stu-id="3f878-243">**Table Mapping**
[*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)</span></span>

-   <span data-ttu-id="3f878-244">**Использовать для создания ключей с Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span><span class="sxs-lookup"><span data-stu-id="3f878-244">**Use HiLo to generate keys with Entity Framework Core**
[*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)</span></span>

-   <span data-ttu-id="3f878-245">**Резервного поля**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span><span class="sxs-lookup"><span data-stu-id="3f878-245">**Backing Fields**
[*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)</span></span>

-   <span data-ttu-id="3f878-246">**Стив Смит. Инкапсулированный коллекций в Entity Framework Core**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span><span class="sxs-lookup"><span data-stu-id="3f878-246">**Steve Smith. Encapsulated Collections in Entity Framework Core**
[*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)</span></span>

-   <span data-ttu-id="3f878-247">**Скрывать свойства**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="3f878-247">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3f878-248">[Предыдущие] (инфраструктуры сохраняемости слоя design.md) [Далее] (nosql-базы данных сохраняемости infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="3f878-248">[Previous] (infrastructure-persistence-layer-design.md) [Next] (nosql-database-persistence-infrastructure.md)</span></span>
