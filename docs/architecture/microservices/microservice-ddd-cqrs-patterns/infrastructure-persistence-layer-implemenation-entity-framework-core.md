---
title: Реализация уровня сохраняемости инфраструктуры с помощью Entity Framework Core
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Сведения о реализации уровня сохраняемости инфраструктуры с помощью Entity Framework Core.
ms.date: 10/08/2018
ms.openlocfilehash: b70ede6b47cbf990d0435aef841416c68f6439b4
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737910"
---
# <a name="implement-the-infrastructure-persistence-layer-with-entity-framework-core"></a>Реализация уровня сохраняемости инфраструктуры с помощью Entity Framework Core

При использовании реляционных баз данных, таких как SQL Server, Oracle или PostgreSQL, рекомендуемый подход заключается в реализации уровня сохраняемости на основе Entity Framework (EF). EF поддерживает LINQ и предоставляет строго типизированные объекты для вашей модели, а также упрощенную сохраняемость в базу данных.

Entity Framework имеет длинную историю в составе .NET Framework. При использовании .NET Core следует также использовать технологию Entity Framework Core, которая работает в Windows или Linux таким же образом, как .NET Core. EF Core — это полностью переработанная технология Entity Framework, реализованная с гораздо меньшими требованиями по ресурсам и важными улучшениями в производительности.

## <a name="introduction-to-entity-framework-core"></a>Знакомство с Entity Framework Core

Entity Framework (EF) — это упрощенная, расширяемая и кроссплатформенная версия популярной технологии для доступа к данным Entity Framework. Она появилась в .NET Core в середине 2016 г.

Поскольку общие сведения о EF Core уже доступны в документации Майкрософт, здесь будут просто приведены ссылки на эту информацию.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Entity Framework Core** \
  [https://docs.microsoft.com/ef/core/](/ef/core/)

- **Начало работы с ASP.NET Core и Entity Framework Core с использованием Visual Studio** \
  [https://docs.microsoft.com/aspnet/core/data/ef-mvc/](/aspnet/core/data/ef-mvc/)

- **Класс DbContext** \
  [https://docs.microsoft.com/dotnet/api/microsoft.entityframeworkcore.dbcontext](xref:Microsoft.EntityFrameworkCore.DbContext)

- **Сравнение EF Core и EF6.x** \
  [https://docs.microsoft.com/ef/efcore-and-ef6/index](/ef/efcore-and-ef6/index)

## <a name="infrastructure-in-entity-framework-core-from-a-ddd-perspective"></a>Инфраструктура в Entity Framework Core с точки зрения DDD

С точки зрения DDD важной особенностью EF является возможность использования сущностей предметной области POCO, которые в терминологии EF также называются *сущностями code-first*. При использовании сущностей предметной области POCO ваши классы модели предметной области являются неустойчивыми, следуя принципам [Persistence Ignorance](https://deviq.com/persistence-ignorance/) (независимости сохраняемости) и [Infrastructure Ignorance](https://ayende.com/blog/3137/infrastructure-ignorance) (независимости инфраструктуры).

В шаблонах DDD вы должны инкапсулировать правила и поведение домена в самом классе сущностей, чтобы он мог управлять инвариантами, проверками и правилами при доступе к любой коллекции. Таким образом, в DDD не рекомендуется разрешать общий доступ к коллекциям дочерних сущностей или объектов значений. Вместо этого следует предоставить методы, определяющие, как и когда могут обновляться поля и коллекции свойств, и какое поведение и действия должны осуществляться, когда это происходит.

Начиная с EF Core 1.1, для удовлетворения этих требований DDD можно создавать в своих сущностях простые поля вместо общедоступных свойств. Если вы не хотите, чтобы поле сущности было доступно извне, можно просто создать атрибут или поле вместо свойства. Можно также использовать методы задания закрытых свойств.

Аналогичным образом, теперь вы можете иметь доступ к коллекциям только на чтение, используя общедоступное свойство, написанное как `IReadOnlyCollection<T>`, которое поддерживается закрытым членом поля для коллекции (например `List<T>`) в вашей сущности, основанной на EF для сохраняемости. В предыдущих версиях Entity Framework требовалось наличие свойств коллекции для поддержки `ICollection<T>`, что означало, что любой разработчик, использующий родительский класс сущностей, может добавлять или удалять элементы с помощью его коллекций свойств. Эта возможность противоречила бы рекомендуемым шаблонам в DDD.

Вы можете использовать закрытую коллекцию при предоставлении объекта `IReadOnlyCollection<T>` только для чтения, как показано в следующем примере кода.

```csharp
public class Order : Entity
{
    // Using private fields, allowed since EF Core 1.1
    private DateTime _orderDate;
    // Other fields ...

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

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

        var orderItem = new OrderItem(productId, productName,
                                      unitPrice, discount,
                                      pictureUrl, units);
        _orderItems.Add(orderItem);
    }
}
```

Обратите внимание, что свойство `OrderItems` может быть доступно только для чтения с помощью `IReadOnlyCollection<OrderItem>`. Этот тип доступен только для чтения, поэтому он защищен от обычных внешних обновлений.

EF Core предоставляет способ сопоставления модели предметной области с физической базой данных без "засорения" этой модели предметной области. Это чистый код POCO .NET, так как действие сопоставления реализовано на уровне сохраняемости. В данном действии сопоставления необходимо настроить сопоставление полей с базой данных. В следующем примере метода `OnModelCreating` из `OrderingContext` и класса `OrderEntityTypeConfiguration` вызов `SetPropertyAccessMode` указывает EF Core на необходимость обратиться к свойству `OrderItems` через его поле.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
        orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
        // Other configuration

        var navigation =
              orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

        //EF access the OrderItem collection property through its backing field
        navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

        // Other configuration
    }
}
```

При использовании полей вместо свойств сущность `OrderItem` сохраняется так же, как если бы она имела свойство `List<OrderItem>`. Однако она предоставляет единственный метод доступа `AddOrderItem` для добавления в заказ новых элементов. В результате поведение и данные оказываются связаны друг с другом и будут согласованными во всем коде приложения, использующем модель предметной области.

## <a name="implement-custom-repositories-with-entity-framework-core"></a>Реализация пользовательских репозиториев с помощью Entity Framework Core

На уровне реализации репозиторий является просто классом с кодом сохраняемости данных, координируемым единицей работы (DBContext в EF Core) при выполнении обновлений, как показано в следующем классе:

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

        public BuyerRepository(OrderingContext context)
        {
            _context = context ?? throw new ArgumentNullException(nameof(context));
        }

        public Buyer Add(Buyer buyer)
        {
            return _context.Buyers.Add(buyer).Entity;
        }

        public async Task<Buyer> FindAsync(string BuyerIdentityGuid)
        {
            var buyer = await _context.Buyers
                .Include(b => b.Payments)
                .Where(b => b.FullName == BuyerIdentityGuid)
                .SingleOrDefaultAsync();

            return buyer;
        }
    }
}
```

Обратите внимание, что интерфейс IBuyerRepository поступает из уровня модели предметной области как контракт. Однако реализация репозитория выполняется на уровне сохраняемости и инфраструктуры.

DbContext EF поступает через конструктор путем внедрения зависимостей. Он совместно используется несколькими репозиториями внутри одной области запроса HTTP благодаря его времени существования по умолчанию (`ServiceLifetime.Scoped`) в контейнере IoC (что также можно явно задать с помощью `services.AddDbContext<>`).

### <a name="methods-to-implement-in-a-repository-updates-or-transactions-versus-queries"></a>Методы, реализуемые в репозитории (обновления или транзакции по отношению к запросам)

В каждом классе репозитория следует поместить методы сохраняемости, которые обновляют состояние сущностей, содержащихся в связанном с ним агрегате. Помните, что имеется однозначное соответствие между агрегатом и связанным с ним репозиторием. Также учитывайте, что корневой объект сущности агрегата может иметь внедренные дочерние сущности в своем графе EF. Например, покупатель может иметь несколько способов оплаты в виде связанных дочерних сущностей.

Поскольку этот подход для микрослужбы заказов в eShopOnContainers также основан на CQS/CQRS, большинство запросов не реализуется в пользовательских репозиториях. Разработчики имеют право создавать нужные им запросы и соединения для уровня представления данных без ограничений, установленных агрегатами, пользовательскими репозиториями в агрегатах и DDD в целом. Большинство пользовательских репозиториев, предлагаемых в данном руководстве, имеют несколько методов обновления или транзакций, но только те методы запросов, которые необходимы для получения обновляемых данных. Например, репозиторий BuyerRepository реализует метод FindAsync, так как приложению нужно узнать, существует ли конкретный покупатель, прежде чем создавать нового покупателя, связанного с заказом.

Однако реальные методы запросов для получения данных для отправки на уровень представления данных или в клиентские приложения реализуются, как было указано, в запросах CQRS на основе гибких запросов с помощью Dapper.

### <a name="using-a-custom-repository-versus-using-ef-dbcontext-directly"></a>Применение пользовательского репозитория по сравнению с непосредственным применением DbContext EF

Класс DbContext Entity Framework основан на шаблонах Unit of Work (единицы работы) и Repository (репозитория); его можно использовать непосредственно из кода приложения, например из контроллера MVC ASP.NET Core. Именно так можно создать простейший код, как в микрослужбе каталога CRUD в eShopOnContainers. В случаях, когда требуется создать максимально простой код, вы можете захотеть напрямую воспользоваться классом DbContext, как делают многие разработчики.

Однако реализация пользовательских репозиториев обеспечивает определенные преимущества при реализации более сложных микрослужб или приложений. Шаблоны Unit of Work и Repository предназначены для инкапсуляции уровня сохраняемости инфраструктуры, поэтому он отделен от уровней приложения и модели предметной области. Реализация этих шаблонов позволяет упростить использование макетов репозиториев, моделирующих доступ к базе данных.

На рис. 7-18 можно увидеть различия между отсутствием использования репозиториев (применением класса DbContext EF напрямую) и использованием репозиториев, что упрощает макетирование таких репозиториев.

![Схема, на которой показаны компоненты и поток данных в двух репозиториях.](./media/infrastructure-persistence-layer-implemenation-entity-framework-core/custom-repo-versus-db-context.png)

**Рис. 7-18**. Применение пользовательских репозиториев по сравнению с простым DbContext

На рис. 7-18 показано, что применение пользовательского репозитория добавляет уровень абстракции, который может использоваться для упрощения тестирования путем макетирования репозитория. Существует несколько вариантов макетирования. Можно макетировать только репозитории или макетировать всю единицу работы. Как правило, достаточно макетирования только репозиториев, и сложность абстрагирования и макетирования всей единицы работы обычно не требуется.

Позднее, когда мы будем рассматривать уровень приложения, вы увидите, как работает внедрение зависимостей в ASP.NET Core и как оно реализуется при использовании репозиториев.

Короче говоря, пользовательские репозитории позволяют упростить тестирование кода с помощью модульных тестов, на которые не влияет состояние уровня данных. Если выполняются тесты, которые также обращаются к реальной базе данных через Entity Framework, то это не модульные тесты, а интеграционные тесты, которые выполняются гораздо медленнее.

Если вы использовали DbContext напрямую, вам потребовалось бы выполнить его макетирование или запуск модульных тестов с помощью SQL Server в памяти с прогнозируемыми данными для модульных тестов. Однако макетирование DbContext или управление фиктивными данными требует больше усилий, чем макетирование на уровне репозитория. Конечно, вы всегда можете тестировать контроллеры MVC.

## <a name="ef-dbcontext-and-iunitofwork-instance-lifetime-in-your-ioc-container"></a>Время существования экземпляра IUnitOfWork и DbContext EF в контейнере IoC

Необходимо реализовать общий доступ к объекту `DbContext` (предоставляемому как объект `IUnitOfWork`) из нескольких репозиториев в рамках одной и той же области запроса HTTP. Например, это может требоваться, когда выполняемая операция должна иметь дело с несколькими агрегаторами, или просто потому, что вы используете несколько экземпляров репозитория. Также важно упомянуть, что интерфейс `IUnitOfWork` является частью уровня домена, а не типом EF Core.

Для этого время существования службы экземпляра объекта `DbContext` должно быть установлено в значение ServiceLifetime.Scoped. Это время существования по умолчанию при регистрации `DbContext` с помощью `services.AddDbContext` в контейнере IoC из метода ConfigureServices файла `Startup.cs` в проекте веб-API ASP.NET Core. Это проиллюстрировано в следующем коде.

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
                               sqlOptions => sqlOptions.MigrationsAssembly(typeof(Startup).GetTypeInfo().
                                                                                    Assembly.GetName().Name));
      },
      ServiceLifetime.Scoped // Note that Scoped is the default choice
                             // in AddDbContext. It is shown here only for
                             // pedagogic purposes.
      );
}
```

Режим создания экземпляра DbContext не должен быть настроен как ServiceLifetime.Transient или ServiceLifetime.Singleton.

## <a name="the-repository-instance-lifetime-in-your-ioc-container"></a>Время существования экземпляра репозитория в контейнере IoC

Аналогичным образом время существования репозитория обычно должно быть задано как scoped — ограниченное областью (InstancePerLifetimeScope в Autofac). Оно также может быть задано как transient — временное (InstancePerDependency в Autofac), но служба будет более эффективной в отношении памяти при использовании времени существования, ограниченного областью.

```csharp
// Registering a Repository in Autofac IoC container
builder.RegisterType<OrderRepository>()
    .As<IOrderRepository>()
    .InstancePerLifetimeScope();
```

Обратите внимание, что использование для репозитория времени существования singleton может вызвать серьезные проблемы с параллелизмом, если для DbContext установлено время существования scoped (InstancePerLifetimeScope) (время существования по умолчанию для DBContext).

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Реализация шаблонов репозитория и единиц работы в приложении ASP.NET MVC** \
  <https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

- **Джонатан Аллен (Jonathan Allen). Стратегии реализации для шаблона репозитория в Entity Framework, Dapper и Chain** \
  <https://www.infoq.com/articles/repository-implementation-strategies>

- **Сезар де ла Торре (Cesar de la Torre). Сравнение времени существования службы контейнеров IoC ASP.NET Core с областями действия экземпляра контейнера IoC Autofac** \
  <https://devblogs.microsoft.com/cesardelatorre/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/>

## <a name="table-mapping"></a>Сопоставление таблиц

Сопоставление таблиц определяет таблицы, данные которых должны запрашиваться и сохраняться в базе данных. Ранее было показано, как сущности предметной области (например, предметная область продуктов или заказов) могут использоваться для создания схемы связанной базы данных. Технология EF строго построена на концепции *соглашений*. Соглашения разрешают, например, такие вопросы, как "Каким будет имя таблицы?" или "Какое свойство является первичным ключом?" Как правило, соглашения основываются на условных именованиях — например, первичный ключ обычно является свойством, которое заканчивается на Id.

По соглашению каждая сущность будет настроена для сопоставления с таблицей с именем, указанным в свойстве `DbSet<TEntity>`, которое предоставляет сущность в производном контексте. Если для конкретной сущности значение свойства `DbSet<TEntity>` не задано, то используется имя класса.

### <a name="data-annotations-versus-fluent-api"></a>Заметки к данным и текучий API

Существует множество дополнительных соглашений EF Core, и большинство из них можно изменить с помощью заметок к данным или текучего API, реализованного в методе OnModelCreating.

Заметки к данным необходимо использовать в самих классах модели сущностей, что является более навязчивым способом с точки зрения DDD. Это связано с тем, что вы засоряете модель заметками к данным, относящимися к базе данных инфраструктуры. С другой стороны, текучий API представляет удобный способ изменения большинства соглашений и сопоставлений на уровне инфраструктуры сохраняемости данных; таким образом, модель сущностей будет чистой и отделенной от инфраструктуры сохраняемости.

### <a name="fluent-api-and-the-onmodelcreating-method"></a>Текучий API и метод OnModelCreating

Как уже упоминалось, для изменения соглашений и сопоставлений можно использовать метод OnModelCreating класса DbContext.

Микрослужба заказов в eShopOnContainers реализует явное сопоставление и конфигурацию, когда это необходимо, как показано в следующем коде.

```csharp
// At OrderingContext.cs from eShopOnContainers
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
   // ...
   modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
   // Other entities’ configuration ...
}

// At OrderEntityTypeConfiguration.cs from eShopOnContainers
class OrderEntityTypeConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> orderConfiguration)
    {
            orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);

            orderConfiguration.HasKey(o => o.Id);

            orderConfiguration.Ignore(b => b.DomainEvents);

            orderConfiguration.Property(o => o.Id)
                .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

            //Address Value Object persisted as owned entity type supported since EF Core 2.0
            orderConfiguration.OwnsOne(o => o.Address);

            orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
            orderConfiguration.Property<int?>("BuyerId").IsRequired(false);
            orderConfiguration.Property<int>("OrderStatusId").IsRequired();
            orderConfiguration.Property<int?>("PaymentMethodId").IsRequired(false);
            orderConfiguration.Property<string>("Description").IsRequired(false);

            var navigation = orderConfiguration.Metadata.FindNavigation(nameof(Order.OrderItems));

            // DDD Patterns comment:
            //Set as field (New since EF 1.1) to access the OrderItem collection property through its field
            navigation.SetPropertyAccessMode(PropertyAccessMode.Field);

            orderConfiguration.HasOne<PaymentMethod>()
                .WithMany()
                .HasForeignKey("PaymentMethodId")
                .IsRequired(false)
                .OnDelete(DeleteBehavior.Restrict);

            orderConfiguration.HasOne<Buyer>()
                .WithMany()
                .IsRequired(false)
                .HasForeignKey("BuyerId");

            orderConfiguration.HasOne(o => o.OrderStatus)
                .WithMany()
                .HasForeignKey("OrderStatusId");
    }
}
```

Можно задать все сопоставления текучего API в одном и том же методе OnModelCreating, но рекомендуется разбить этот код на несколько классов конфигурации, по одному на сущность, как показано в примере. В первую очередь отдельные классы конфигурации для настройки разных типов сущностей рекомендуется использовать для особо больших моделей.

В примере кода показано несколько явных объявлений и сопоставлений. Однако соглашения EF Core выполняют многие из этих сопоставлений автоматически, так что фактический код, который понадобится в вашем случае, может иметь меньший размер.

### <a name="the-hilo-algorithm-in-ef-core"></a>Алгоритм Hi/Lo в EF Core

Интересным аспектом кода в предыдущем примере является применение [алгоритма Hi/Lo](https://vladmihalcea.com/the-hilo-algorithm/) в качестве стратегии создания ключей.

Алгоритм Hi/Lo удобно использовать в тех случаях, когда требуются уникальные ключи перед фиксацией изменений. Вкратце, алгоритм Hi-Lo присваивает строкам таблицы уникальные идентификаторы, которые не зависят от немедленного сохранения строк в базе данных. Это позволяет начинать использовать идентификаторы сразу, как это происходит с обычными последовательными идентификаторами базы данных.

Алгоритм Hi/Lo описывает механизм для получения пакета уникальных идентификаторов из последовательности связанной базы данных. Эти идентификаторы являются безопасными для использования, так как база данных гарантирует уникальность, исключая конфликты между пользователями. Этот алгоритм представляет интерес по следующим причинам.

- Он не нарушает шаблон единицы работы.

- Он получает идентификаторы последовательности в пакетах, чтобы свести к минимуму количество обращений к базе данных.

- Он создает удобный для восприятия идентификатор, в отличие от методов, в которых используются идентификаторы GUID.

EF Core поддерживает алгоритм [HiLo](https://stackoverflow.com/questions/282099/whats-the-hi-lo-algorithm) с помощью метода ForSqlServerUseSequenceHiLo, как показано в предыдущем примере.

### <a name="map-fields-instead-of-properties"></a>Сопоставление полей вместо свойств

Эта функция, появившаяся в EF Core 1.1, позволяет сопоставлять столбцы с полями напрямую. Теперь существует возможность не использовать свойства в классе сущностей, а просто сопоставлять столбцы таблицы с полями. Эта возможность часто используется в закрытых полях для хранения внутреннего состояния, доступ к которому не должен осуществляться извне сущности.

Это можно делать как с отдельными полями, так и с коллекциями, например с `List<>`. Этот момент упоминался ранее, когда мы обсуждали моделирование классов модели предметной области, но здесь можно видеть, как это сопоставление выполняется для конфигурации `PropertyAccessMode.Field`, выделенной в предыдущем коде.

### <a name="use-shadow-properties-in-ef-core-hidden-at-the-infrastructure-level"></a>Использование теневых свойств в EF Core, скрытых на уровне инфраструктуры

Теневые свойства в EF Core — это свойства, которые не существуют в вашей модели классов сущностей. Значения и состояния этих свойств сохраняются только в классе [ChangeTracker](https://docs.microsoft.com/ef/core/api/microsoft.entityframeworkcore.changetracking.changetracker) на уровне инфраструктуры.

## <a name="implement-the-query-specification-pattern"></a>Реализация шаблона спецификации запроса

Как говорилось ранее в разделе, посвященном проектированию, шаблон спецификации запроса — это шаблон предметно-ориентированного проектирования, в котором можно поместить определение запроса с дополнительной логикой сортировки и разбиения на страницы.

Шаблон спецификации запроса определяет запрос в объекте. Например, чтобы инкапсулировать постраничный запрос, который выполняет поиск некоторых продуктов, вы можете создать спецификацию PagedProduct, которая принимает необходимые входные параметры (номер страницы, размер страницы, фильтр и т. д.). Затем в любом методе репозитория (обычно в перегрузке List()) вы можете принять IQuerySpecification и запустить ожидаемый запрос на основе этой спецификации.

Пример универсального интерфейса спецификации приведен в следующем коде из [eShopOnWeb](https://github.com/dotnet-architecture/eShopOnWeb).

```csharp
// GENERIC SPECIFICATION INTERFACE
// https://github.com/dotnet-architecture/eShopOnWeb

public interface ISpecification<T>
{
    Expression<Func<T, bool>> Criteria { get; }
    List<Expression<Func<T, object>>> Includes { get; }
    List<string> IncludeStrings { get; }
}
```

Реализация базового класса универсальной спецификации выглядит следующим образом.

```csharp
// GENERIC SPECIFICATION IMPLEMENTATION (BASE CLASS)
// https://github.com/dotnet-architecture/eShopOnWeb

public abstract class BaseSpecification<T> : ISpecification<T>
{
    public BaseSpecification(Expression<Func<T, bool>> criteria)
    {
        Criteria = criteria;
    }
    public Expression<Func<T, bool>> Criteria { get; }

    public List<Expression<Func<T, object>>> Includes { get; } =
                                           new List<Expression<Func<T, object>>>();

    public List<string> IncludeStrings { get; } = new List<string>();

    protected virtual void AddInclude(Expression<Func<T, object>> includeExpression)
    {
        Includes.Add(includeExpression);
    }

    // string-based includes allow for including children of children
    // e.g. Basket.Items.Product
    protected virtual void AddInclude(string includeString)
    {
        IncludeStrings.Add(includeString);
    }
}
```

Следующая спецификация загружает одну сущность корзины, заданную идентификатором корзины или идентификатором покупателя, которому принадлежит корзина. Она будет [безотлагательно загружать](https://docs.microsoft.com/ef/core/querying/related-data) коллекцию Items корзины.

```csharp
// SAMPLE QUERY SPECIFICATION IMPLEMENTATION

public class BasketWithItemsSpecification : BaseSpecification<Basket>
{
    public BasketWithItemsSpecification(int basketId)
        : base(b => b.Id == basketId)
    {
        AddInclude(b => b.Items);
    }
    public BasketWithItemsSpecification(string buyerId)
        : base(b => b.BuyerId == buyerId)
    {
        AddInclude(b => b.Items);
    }
}
```

И, наконец, ниже вы видите, как универсальный репозиторий EF может использовать такую спецификацию для фильтрации и безотложной загрузки данных, связанных с типом T заданной сущности.

```csharp
// GENERIC EF REPOSITORY WITH SPECIFICATION
// https://github.com/dotnet-architecture/eShopOnWeb

public IEnumerable<T> List(ISpecification<T> spec)
{
    // fetch a Queryable that includes all expression-based includes
    var queryableResultWithIncludes = spec.Includes
        .Aggregate(_dbContext.Set<T>().AsQueryable(),
            (current, include) => current.Include(include));

    // modify the IQueryable to include any string-based include statements
    var secondaryResult = spec.IncludeStrings
        .Aggregate(queryableResultWithIncludes,
            (current, include) => current.Include(include));

    // return the result of the query using the specification's criteria expression
    return secondaryResult
                    .Where(spec.Criteria)
                    .AsEnumerable();
}
```

Помимо инкапсуляции логики фильтрации, эта спецификация может указывать форму возвращаемых данных, включая свойства, которые следует заполнить.

Хотя не рекомендуется возвращать IQueryable из репозитория, совершенно нормально использовать их в репозитории для создания набора результатов. Вы видели применение этого подхода в методе List выше, где промежуточные выражения IQueryable использовались для построения списка Includes запроса перед выполнением запроса с условиями спецификации в последней строке.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Сопоставление таблиц** \
  [https://docs.microsoft.com/ef/core/modeling/relational/tables](/ef/core/modeling/relational/tables)

- **Применение HiLo для создания ключей с использованием Entity Framework Core** \
  <https://www.talkingdotnet.com/use-hilo-to-generate-keys-with-entity-framework-core/>

- **Резервные поля** \
  [https://docs.microsoft.com/ef/core/modeling/backing-field](/ef/core/modeling/backing-field)

- **Стив Смит (Steve Smith). Инкапсулированные коллекции в Entity Framework Core** \
  <https://ardalis.com/encapsulated-collections-in-entity-framework-core>

- **Свойства тени** \
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- **Шаблон спецификации** \
  <https://deviq.com/specification-pattern/>

> [!div class="step-by-step"]
> [Назад](infrastructure-persistence-layer-design.md)
> [Вперед](nosql-database-persistence-infrastructure.md)
