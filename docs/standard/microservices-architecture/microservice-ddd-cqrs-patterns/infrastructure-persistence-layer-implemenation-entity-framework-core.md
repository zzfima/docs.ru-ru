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
# <a name="implementing-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Реализация уровня инфраструктуры сохраняемости с Entity Framework Core

При использовании реляционных баз данных, например SQL Server, Oracle или PostgreSQL, рекомендуемый подход заключается в реализации на уровне хранения на основе на Entity Framework (EF). EF поддерживает LINQ и предоставляет строго типизированных объектов для модели, а также упрощенное сохраняемости в базу данных.

Платформа Entity Framework имеет длинную историю в составе .NET Framework. При использовании .NET Core, следует также использовать Entity Framework Core, который выполняется на Windows или Linux в так же, как .NET Core. EF лежит полностью переписан платформы Entity Framework реализована с помощью намного меньше памяти и важные улучшения в производительности.

## <a name="introduction-to-entity-framework-core"></a>Общие сведения об Entity Framework Core

Core Entity Framework (EF) является упрощенным, расширяемым, и технология доступа к версии кросс платформенных популярных данных Entity Framework. Она появилась в .NET Core в середине 2016.

Поскольку введение в основные EF недоступные в документации Microsoft, здесь просто содержатся ссылки на эти сведения.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Entity Framework Core**
    [*https://docs.microsoft.com/ef/core/*](https://docs.microsoft.com/ef/core/)

-   **Приступая к работе с ASP.NET Core и Entity Framework с помощью Visual Studio**
    [*https://docs.microsoft.com/aspnet/core/data/ef-mvc/*](https://docs.microsoft.com/aspnet/core/data/ef-mvc/)

-   **Класс DbContext**
    [*https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext*](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.dbcontext)

-   **Сравнение основных EF & EF6.x**
    [*https://docs.microsoft.com/ef/efcore-and-ef6/index*](https://docs.microsoft.com/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>С точки зрения DDD инфраструктуры Entity Framework Core

С точки зрения DDD являются важной характеристикой EF является возможность использования сущности POCO домена, в терминологии EF как POCO также называется *сначала код сущности*. При использовании домена сущности POCO, ваши классы модели домена сохраняемость, следуя [сохраняемости](http://deviq.com/persistence-ignorance/) и [пропуск инфраструктуры](https://ayende.com/blog/3137/infrastructure-ignorance) принципы.

В шаблонах DDD следует инкапсулируют поведение домена и правил в класс сущностей, благодаря чему можно контролировать инварианты, проверки и правила, при доступе к любой коллекции. Таким образом это не рекомендуется в ддд, чтобы разрешить общий доступ к коллекции дочерних сущностей или объектов значение. Вместо этого необходимо предоставлять методы, определяющие, как и когда поля и коллекциях свойств могут обновляться, и какое поведение, а также действия должно выполняться, когда это происходит.

В EF Core 1.1 для удовлетворения этих требований DDD могут иметь простых полей в сущностях вместо свойств с помощью открытые и закрытые методы задания. Если не хотите, чтобы поле сущности для будет доступен, достаточно просто создать атрибут или поле, а не свойства. Нет необходимости использовать частного задания, если вы предпочитаете такой подход очистки.

Аналогичным образом, теперь вы можете открыть доступ только для чтения к коллекциям с помощью открытые свойства, типизированное как IEnumerable&lt;T&gt;, который резервируется членом закрытое поле для коллекции (такие как список&lt;&gt;) в вашей сущность, использующая EF для сохраняемости. Предыдущие версии платформы Entity Framework требуют наличия свойства коллекции для поддержки ICollection&lt;T&gt;, которой означает, что любому разработчику, использующему родительского класса сущности может добавлять или удалять элементы из коллекции его свойства. Чтобы можно было бы от рекомендуемых шаблонов в ддд.

Можно использовать частной коллекции при предоставлении доступа к объект IEnumerable, только для чтения, как показано в следующем примере кода:

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

Обратите внимание, что свойство OrderItems только доступно только для чтения с помощью списка&lt;&gt;. AsReadOnly(). Этот метод создает оболочку закрытого списка только для чтения, чтобы он защищен от внешних обновлений. Это значительно дешевле, чем с помощью метода ToList, так как не включает копирование всех элементов в коллекции; Вместо этого он выполняет только для одной операции выделения кучи для экземпляра оболочки.

EF Core предоставляет способ для сопоставления модели домена физическую базу данных без что засоряет модели домена. Это чисто .NET POCO код, так как сопоставление это реализовано в уровне сохраняемости. В данному действию сопоставления необходимо настроить сопоставления полей для базы данных. В следующем примере метод OnModelCreating выделенный код сообщает EF ядер и доступ к свойству OrderItems через его поля.

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

При использовании полей вместо свойств сущности OrderItem сохраняется, как если бы оно находилось список&lt;OrderItem&gt; свойство. Однако он предоставляет один метод доступа (метод AddOrderItem) для добавления новых элементов в порядке. В результате поведение и данных связаны друг с другом и будет несогласованной в код приложения, использующего модель домена.

## <a name="implementing-custom-repositories-with-entity-framework-core"></a>Реализация пользовательских репозиториев с Entity Framework Core

На уровне реализации репозитория является просто классом с кодом сохраняемости данных, координируемое единица работы (DBContext ядра EF) при выполнении обновления, как показано в следующем классе:

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

Обратите внимание, что интерфейс IBuyerRepository поступают из уровня модели домена. Однако реализация репозитория выполняется в сохраняемости и уровень инфраструктуры.

EF DbContext поступает через конструктор через внедрения зависимостей. Используется совместно несколькими репозиториями внутри одной области запроса HTTP, благодаря существования по умолчанию (ServiceLifetime.Scoped) в контейнер IoC (их можно также явно задать со службами. AddDbContext&lt;&gt;).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Методы, реализуемые в репозитории (обновления или транзакций и запросы)

В каждом классе репозитория следует разместить методы сохраняемости, обновляющих состояние сущности его связанные агрегатной функции. Помните, что имеется однозначное соответствие между статистическое выражение и его связанные репозитория. Принять во внимание, что объект сущности статистические корневой могут внедрять дочерних сущностей в его графе EF. Например покупатель может быть несколько способов оплаты связанных дочерних сущностей.

Поскольку подход для упорядочивания микрослужбу в eShopOnContainers также основана на CQS/CQRS, большинство запросов не реализованы в пользовательские репозитории. Разработчики имеют возможность создавать запросы и соединения, необходимые для уровня представления без ограничений, установленных для статистических выражений, пользовательские репозитории каждого статистического выражения и DDD в целом. Большинство пользовательских репозиториев, предлагаемые в данном руководстве имеют несколько обновлений или методы транзакций, но только методы запросов, необходимых для получения данных для обновления. Например репозитории BuyerRepository реализует метод FindAsync, так как приложению нужно знать, существует ли определенный покупатель перед созданием нового покупатель порядка.

Однако методы реальные запросов для получения данных для отправки презентации слоя или клиентского приложения реализации, как упоминалось в CQRS запросы, основанные на гибкие запросы, с помощью Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>С помощью пользовательского репозитория или непосредственно с помощью EF DbContext

Класс Entity Framework DbContext основана на шаблонах единицей работы и репозитория, а также можно использовать напрямую из кода приложения, такие как с помощью контроллера ASP.NET Core MVC. То есть способ вы можете создать простой код, как микрослужбу каталога CRUD в eShopOnContainers. В случаях возникает необходимость простой кода невозможно можно непосредственно с помощью класса DbContext, как и многие разработчики.

Однако реализация пользовательских репозиториев предоставляет несколько преимуществ при реализации более сложной микрослужбами или приложений. Единица работы и репозитория шаблоны предназначены для инкапсуляции уровень сохраняемости инфраструктуры, поэтому оно связано с уровнями модели домена приложения и. Реализация этих шаблонах позволяет упростить использование макетов репозиториев имитация доступ к базе данных.

На рисунке 9-18 можно увидеть различия между не с помощью репозиториев (непосредственно с помощью EF DbContext) сравнению с репозиториев, которые облегчают макета таких репозиториев.

![](./media/image19.png)

**На рисунке 9-18**. С помощью пользовательских репозиториев и простой DbContext

Существует несколько вариантов при имитации. Удалось макета просто репозиториев или удалось макета всей единица работы. Обычно имитации просто репозиториев достаточно и сложности для выделения и макета всей единица работы обычно не требуется.

Позже когда мы сосредоточим внимание на уровне приложения, вы увидите как работает внедрение зависимостей в ASP.NET Core, и его реализация при использовании репозиториев.

Иными словами пользовательские репозитории позволяют упростить тестирование кода с модульными тестами, которые не влияет на состояние уровня данных. При выполнении тестов, которые также обращаться к реальной базы данных через Entity Framework, они не являются модульные тесты, но интеграции тестов, которые выполняются гораздо медленнее.

Если вы использовали непосредственно DbContext, единственным вариантом нужно было бы будет для выполнения модульных тестов с помощью SQL Server в памяти с прогнозируемых данных для модульных тестов. Управлять таким же образом на уровне репозитория макетов объектов и фальшивых данных будет невозможно. Конечно вы всегда тестировать контроллеров MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Время существования экземпляра EF DbContext и IUnitOfWork в контейнер IoC

Объект DbContext (доступный в виде объекта IUnitOfWork), необходимо быть общим для нескольких репозиториев в той же области запроса HTTP. Например, это справедливо при выполняемой операции приходится иметь дело с нескольких статистических выражений или просто потому, что вы используете несколько экземпляров репозитория. Это также необходимо упомянуть, интерфейс IUnitOfWork входит в состав домена, а не тип EF.

Для этого экземпляра объекта DbContext должна иметь время существования службы присвоено значение ServiceLifetime.Scoped. Это время жизни по умолчанию, когда регистрация DbContext с службы. AddDbContext в контейнер IoC из метода ConfigureServices файла Startup.cs файла в проекте веб-API ASP.NET Core. Это проиллюстрировано в следующем коде.

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

Не следует настраивать режим при создании экземпляра DbContext как ServiceLifetime.Transient или ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Время существования экземпляра репозитория в контейнер IoC

Аналогичным образом время существования репозитория обычно должна быть задана как области (InstancePerLifetimeScope в Autofac). Также это может быть временной (InstancePerDependency в Autofac), но служба будет более эффективным в отношении памяти, при использовании с областью времени существования.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Следует отметить, что время жизни singleton для репозитория может привести к вам параллелизма серьезных проблем при вашей DbContext равно времени существования (InstancePerLifetimeScope) (по умолчанию время существования для DBContext) в области видимости.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Реализация репозитория и единицы шаблонов рабочих элементов в приложении ASP.NET MVC**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)

-   **Аллен Джонатан. Стратегии реализации для репозитория с Entity Framework Dapper, шаблон и прикрепить**
    [*https://www.infoq.com/articles/repository-implementation-strategies*](https://www.infoq.com/articles/repository-implementation-strategies)

-   **Сезар де ла Торре (Cesar de la Torre). Сравнение времени существования службы контейнер ASP.NET Core IoC с областями экземпляр контейнер Autofac IoC**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="table-mapping"></a>Сопоставление таблиц

Сопоставление таблиц определяет данные таблицы должны запрашиваться из и сохранены в базе данных. Ранее было показано, как сущности домена (например, домен продукта или заказа) может использоваться для создания схемы связанной базы данных. EF строго построена на концепции *соглашения*. Соглашения о решать вопросы, например «Как имя таблицы будет?» или «какое свойство является первичным ключом?» Соглашения обычно основаны на обычные имена — например, он является типичным для первичного ключа, как свойство, которое заканчивается на идентификатор.

По соглашению, каждая сущность будет настроен для сопоставления с таблицей с тем же именем, что DbSet&lt;TEntity&gt; свойство, которое предоставляет сущности в контексте производной. Если не DbSet&lt;TEntity&gt; значение предоставляется для заданной сущности, используется имя класса.

### <a name="data-annotations-versus-fluent-api"></a>Заметок к данным или Fluent API

Существует множество дополнительных соглашения EF Core, и большинство из них может быть изменен с помощью заметок к данным или Fluent API-Интерфейс, реализованный в методе OnModelCreating.

Заметок к данным необходимо использовать в классы сущностей модели самостоятельно, что является более активное вмешательство с точки зрения DDD способом. Это происходит потому что засоряет модели с заметками данные, относящиеся к базе данных инфраструктуры. С другой стороны Fluent API является удобным способом изменить большинство соглашения и сопоставления в вашей инфраструктуре уровень сохраняемости данных, таким образом модели сущности, очистить и отделенный от инфраструктуры сохраняемости.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>Fluent API и методе OnModelCreating

Как уже упоминалось, чтобы изменить сопоставления и соглашения можно использовать метод OnModelCreating класса DbContext. В следующем примере показано, как это делается в упорядочивания микрослужбу в eShopOnContainers.

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

Можно задать все сопоставления Fluent API в один и тот же метод OnModelCreating, но рекомендуется для разделения кода и имеют несколько submethods, по одному на сущности, как показано в примере. Для моделей, особенно большой он даже может рекомендуется иметь отдельным файлам исходного кода (статические классы) для настройки различных типов сущностей.

Код в примере является явным. EF Core соглашения выполнить, большая часть этой автоматически, поэтому фактический код, необходимо написать для достижения то же самое будет намного меньше.

### <a name="the-hilo-algorithm-in-ef-core"></a>Алгоритм Hi/Lo EF ядра

Интересным аспектом кода в предыдущем примере является применение [алгоритм Hi/Lo](https://vladmihalcea.com/2014/06/23/the-hilo-algorithm/) в рамках стратегии создания ключей.

Алгоритм Hi/Lo полезен в тех случаях, когда требуется уникальные ключи. В сводке алгоритм Hi-Lo присваивает уникальные идентификаторы строк таблицы пока не в зависимости от немедленно хранения строк в базе данных. Это позволяет запустить прямо сейчас, используя идентификаторы, как происходит с обычной базой данных последовательные идентификаторы.

Алгоритм Hi/Lo описывает механизм для создания безопасного ID на стороне клиента, а не в базе данных. *Безопасный* в данном контексте означает без конфликтов. Этот алгоритм является интересные по следующим причинам:

-   Он не прерывает шаблон единицу работы.

-   Не требуется выполнять циклов приема-передачи генераторы последовательности как в других СУБД.

-   Он создает удобочитаемый идентификатор, в отличие от методов, которые используют идентификаторы GUID.

EF Core поддерживает [HiLo](http://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) с помощью метода ForSqlServerUseSequenceHiLo, как показано в предыдущем примере.

### <a name="mapping-fields-instead-of-properties"></a>Сопоставление полей вместо свойств

С помощью функции EF Core 1.1, которая сопоставляет столбцы с полями можно не использовать какие-либо свойства в класс сущностей и просто для сопоставления столбцов таблицы с полями. Обычно используются, будет закрытым полям для любого внутреннего состояния, которые не обязательно должны быть доступны извне сущности.

EF 1.1 поддерживает сопоставление поля без связанного свойства со столбцом в базе данных. Это можно сделать с одного поля или также коллекций, такие как список&lt; &gt; поля. Эта точка упомянутая ранее, когда мы рассмотрели моделирования классы модели домена, но здесь можно увидеть, как это сопоставление выполняется с конфигурацией PropertyAccessMode.Field, выделяются в предыдущем примере кода.

### <a name="using-shadow-properties-in-value-objects-for-hidden-ids-at-the-infrastructure-level"></a>С помощью замещения свойств в объектах значение скрытого удостоверений на уровне инфраструктуры

Свойства, которые не существуют в модели сущности класса свойства тени EF ядра: Значения и состояния эти свойства сохраняются только в [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) класса на уровне инфраструктуры.

С точки зрения DDD замещения свойств — удобный способ реализации значение объектов, скрывая ID в качестве первичного ключа свойства тени. Это важно, так как объект значения не следует идентификаторов (по крайней мере, не должно быть идентификатор в уровне модели домена при формировании значения объектов). Это значит, начиная с текущей версии ядра EF EF Core у способ реализации объектов значение как [сложных типов](https://msdn.microsoft.com/library/jj680147(v=vs.113).aspx), насколько это возможно в EF 6.x. Именно поэтому в настоящее время необходимо реализовать объект значения, как сущность с Идентификатором скрытый (первичный ключ) установлено в качестве свойства тени.

Как видно в [объект значение адреса](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs) в eShopOnContainers, в модели адрес отсутствует идентификатор:

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

Но на самом деле, необходимо указать ИД таким образом, чтобы основные EF возможность сохранить эти данные в таблицах базы данных. Что мы делаем в методе ConfigureAddress [OrderingContext.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Infrastructure/OrderingContext.cs) класса на уровне инфраструктуры, поэтому мы не засоряет моделью домена с кодом EF инфраструктуры.

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

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Таблица сопоставления**
    [*https://docs.microsoft.com/ef/core/modeling/relational/tables*](https://docs.microsoft.com/ef/core/modeling/relational/tables)

-   **Использовать для создания ключей с Entity Framework Core HiLo**
    [*http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/*](http://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/)

-   **Резервного поля**
    [*https://docs.microsoft.com/ef/core/modeling/backing-field*](https://docs.microsoft.com/ef/core/modeling/backing-field)

-   **Стив Смит. Инкапсулированный коллекций в Entity Framework Core**
    [*http://ardalis.com/encapsulated-collections-in-entity-framework-core*](http://ardalis.com/encapsulated-collections-in-entity-framework-core)

-   **Скрывать свойства**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)


>[!div class="step-by-step"]
[Предыдущие] (инфраструктуры сохраняемости слоя design.md) [Далее] (nosql-базы данных сохраняемости infrastructure.md)
