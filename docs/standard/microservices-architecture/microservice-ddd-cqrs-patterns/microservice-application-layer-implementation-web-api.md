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
# <a name="implementing-the-microservice-application-layer-using-the-web-api"></a>Реализации микрослужбу уровня приложения, с помощью веб-API

## <a name="using-dependency-injection-to-inject-infrastructure-objects-into-your-application-layer"></a>С помощью внедрения зависимости для вставки объектов инфраструктуры на уровне приложений

Как упоминалось ранее, уровень приложения может осуществляться в рамках артефакта, создании, таких как в проект веб-API или проект веб-приложения MVC. В случае микрослужбу, созданного с помощью ASP.NET Core уровень приложения обычно будет библиотеки веб-API. Если необходимо разделить предстоящие из ASP.NET Core (свою инфраструктуру, а также контроллеров) из пользовательского приложения слой кода, можно также поместить на уровне приложения в отдельной библиотеке классов, но это необязательно.

Для экземпляра код уровня приложения для упорядочивания микрослужбу непосредственно реализуется как часть **Ordering.API** проект (проект веб-API ASP.NET Core), как показано на рисунке 9-19.

![](./media/image20.png)

**На рисунке 9-19**. Уровень приложения в проекте веб-API Ordering.API ASP.NET Core

ASP.NET Core включает в себя простую [встроенные контейнер IoC](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection) (представленное интерфейс IServiceProvider), поддерживающем внедрение конструктора по умолчанию и ASP.NET можно использовать посредством DI определенных служб. ASP.NET Core используется термин *службы* для любых типов, регистрации, которые будут внесены через DI. Необходимо настроить службы встроенного контейнера ConfigureServices метода в класс запуска приложения. Зависимости будут реализованы в службы, которые требуется тип.

Как правило требуется внедрения зависимостей, реализующих объектов инфраструктуры. Зависимость весьма типичен для вставки — это хранилище. Однако может запустить другой инфраструктуры зависимости, то, возможно. Для простой реализации может напрямую внедрить объект шаблон единицы работы (объект EF DbContext), поскольку класс DBContext также является реализацией сохраняемости объектов вашей инфраструктуры.

В следующем примере вы увидите, как .NET Core внедряет объектов требуется хранилище с помощью конструктора. Класс представляет обработчик команд, в которой будут рассмотрены в следующем разделе.

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

Этот класс использует подставляемого репозиториев для выполнения транзакции и сохранить изменения состояния. Он не имеет значения, является ли этот класс является допустимым обработчиком команд, метод контроллера веб-API ASP.NET Core или [службы приложения DDD](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/). Он представляет собой простой класс, который использует репозиториев, домена сущностей и другие приложения координации аналогично обработчика команд. Работает внедрение зависимостей одинаково для всех упомянутых классов, как показано в примере с помощью DI на основании конструктор.

### <a name="registering-the-dependency-implementation-types-and-interfaces-or-abstractions"></a>Регистрация типов реализации зависимостей и интерфейсы или абстрактные классы

Прежде чем использовать объекты, введенный через конструкторы, необходимо знать, где зарегистрировать интерфейсы и классы, создавать объекты, внедренные в ваши приложения классы через DI. (Подобно DI на основе конструктора, как показано выше.)

#### <a name="using-the-built-in-ioc-container-provided-by-aspnet-core"></a>С помощью встроенных контейнер IoC, предоставляемый ASP.NET Core

При использовании встроенных контейнер IoC, предоставляемый ASP.NET Core, можно зарегистрировать типы, которые нужно внедрить в методе ConfigureServices в файле Startup.cs файла, как показано в следующем коде:

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

Чаще всего встречается при регистрации типов в контейнер IoC является регистрация парой типов — интерфейс и его связанные реализацию класса. Затем при запросе объекта контейнер IoC через любой конструктор запроса объекта определенного типа интерфейса. Например в предыдущем примере последней строки состояния, если любой из конструкторах с зависимостями от IMyCustomRepository (интерфейс или абстракции) контейнер IoC добавит экземпляр реализации MyCustomSQLServerRepository класс.

#### <a name="using-the-scrutor-library-for-automatic-types-registration"></a>С помощью библиотеки Scrutor для типов автоматической регистрации

При использовании DI в .NET Core, можно иметь возможность проверять сборки и автоматически зарегистрировала свои типы по соглашению. Этот компонент недоступен в ASP.NET Core. Тем не менее, можно использовать [Scrutor](https://github.com/khellang/Scrutor) библиотеки для этого. Такой подход удобен при наличии десятков типов, которые должны быть зарегистрированы в контейнер IoC.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Мэтью Кинг. Регистрация служб с Scrutor**
    [*https://mking.io/blog/registering-services-with-scrutor*](https://mking.io/blog/registering-services-with-scrutor)

<!-- -->

-   **Кристиан Hellang. Scrutor.** В репозитории GitHub.
    [*https://github.com/khellang/Scrutor*](https://github.com/khellang/Scrutor)

#### <a name="using-autofac-as-an-ioc-container"></a>С помощью Autofac как контейнер IoC

Можно также использовать дополнительные контейнеры IoC и подключите их к конвейеру ASP.NET Core, как и порядка сортировки микрослужбу в eShopOnContainers, который использует [Autofac](https://autofac.org/). При использовании Autofac обычно регистрации типов через модули, которые позволяют разделить типы регистрации между несколькими файлами в зависимости от расположения к типам, так же, как можно создать типы приложений, распределенные по нескольким библиотеки классов.

Например, ниже приведен [модуль приложения Autofac](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Infrastructure/AutofacModules/ApplicationModule.cs) для [Ordering.API веб-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.API) проекта с типами, которые требуется вставить.

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

Процесс регистрации и основные понятия очень аналогично тому, как можно зарегистрировать типы с помощью встроенных контейнера iOS ASP.NET Core, но синтаксис при использовании Autofac немного отличается.

В примере кода абстракции IOrderRepository регистрируется вместе с реализацией класса OrderRepository. Это означает, что каждый раз, когда зависимостей через абстракции IOrderRepository или интерфейс объявляет конструктор, контейнер IoC добавит экземпляр класса OrderRepository.

Тип области экземпляр определяет, как экземпляр совместно запросов для той же службы или зависимостей. При обращении к зависимости контейнер IoC может вернуть следующее:

-   Один экземпляр на время существования области (в контейнер ASP.NET Core IoC как называется *область*).

-   Новый экземпляр каждого зависимостей (в контейнер ASP.NET Core IoC как называется *временных*).

-   Один экземпляр, общими для всех объектов, используя контейнер IoC (Далее в контейнер ASP.NET Core IoC как *одноэлементный*).

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Общие сведения о внедрение зависимостей в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection*](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection)

-   **Autofac.** Официальной документации.
    [*http://docs.autofac.org/en/Latest/*](http://docs.autofac.org/en/latest/)

-   **Сезар де ла Торре (Cesar de la Torre). Сравнение времени существования службы контейнер ASP.NET Core IoC с областями экземпляр контейнер Autofac IoC**
    [*https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/ Comparing-ASP-NET-Core-IoC-Service-Life-Times-and-autofac-IoC-Instance-scopes/*](https://blogs.msdn.microsoft.com/cesardelatorre/2017/01/26/comparing-asp-net-core-ioc-service-life-times-and-autofac-ioc-instance-scopes/)

## <a name="implementing-the-command-and-command-handler-patterns"></a>Реализация шаблонов команда и обработчика команд

В примере DI через конструктор, показанном в предыдущем разделе контейнер IoC был вводится репозиториев через конструктор в классе. Но точно где были они внедрены? В простой веб-API (например, каталог микрослужбу в eShopOnContainers) запустить их на уровне контроллеров MVC в конструкторе контроллера. Однако в исходный код в этом разделе ( [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) класса из службы Ordering.API в eShopOnContainers), внедрение зависимостей выполняется с помощью конструктора определенной команды обработчик. Сообщите нам объяснить является команда обработчик и зачем вам нужно использовать.

По своей природе команд связана с CQRS шаблон, который был введен ранее в этом руководстве. CQRS есть две стороны. Первая область-запросы, с помощью упрощенного запросы с [Dapper](https://github.com/StackExchange/dapper-dot-net) micro ORM, который был описан ранее. Вторая область-команд, которые являются отправной точкой для операций и входной канал из вне этой службы.

Как показано на рисунке 9-20, шаблон основан на прием команд на стороне клиента, обработки их на основе модели правил домена и наконец сохранение состояния с транзакциями.

![](./media/image21.png)

**Рис. 9-20**. Высокоуровневое представление команд или «транзакций стороны» в шаблоне CQRS

### <a name="the-command-class"></a>Класс команд

Команда — это запрос, чтобы выполнить действие, которое изменяет состояние системы система. Команды императивный и будут обрабатываться только один раз.

Поскольку команды условиям, обычно именуются с помощью команды в императивном модальности (например, «создание» или «update»), и они могут включать агрегатного типа, например CreateOrderCommand. В отличие от события команда не факт в прошлом; он представляет собой запрос и таким образом, может быть отклонено.

Команды могут быть получены из пользовательского интерфейса, в результате пользователь инициирует запрос или из диспетчера процессов при диспетчер процессов направляет статистическую функцию для выполнения действия.

Важной характеристикой команды — что он должен обрабатываться только один раз один получатель. Это так, как команда — это единственное действие или транзакции, которую требуется выполнить в приложении. Например одной и той же команды создания заказа не должны обрабатываться несколько раз. Это важное отличие между команды и события. События могут обрабатываться несколько раз, так как многие системы или микрослужбами могут быть заинтересованы в событии.

Кроме того важно команду обработки только один раз в случае, если команда не является идемпотентными. Команда является идемпотентной, если он может выполняться несколько раз без изменения результатов, либо из-за характера команды, либо из-за того, система обрабатывает команды.

Рекомендуется всегда команд и обновляет идемпотентными, когда это имеет смысл в области бизнес-правил для вашего домена и инварианты. Например использовать тот же пример, если для какой-либо причине (логику повторных попыток, взлому, т. д.) одной и той же команде CreateOrder достигает компьютер несколько раз, можно для идентификации и обеспечить не создания нескольких заказов. Для этого необходимо присоединить какой-либо удостоверения в операциях и идентифицировать ли команда или обновления уже был обработан.

Отправить команду к одному получателю; команда не будет опубликована. Публикацию можно использовать для интеграции события с сообщением факт, что что-то произошло и может представлять интерес для приемников событий. В случае события у издателя есть никаких проблем, о которых получить приемники события и что они делают его. Однако события интеграции другую статью, уже представленные в предыдущих разделах.

Команда реализуется с помощью класса, содержащего поля данных или коллекций, в которых все сведения, необходимые для выполнения этой команды. Команда — это особый тип объекта данных передачи объекта (DTO), который специально используется для запроса изменений или операции. Саму команду основан на данные, необходимые для обработки команды и ничего более.

В примере показан упрощенный класс CreateOrderCommand. Это неизменяемый команды, используемой в упорядочивания микрослужбу в eShopOnContainers.

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

По существу класс команд содержит все данные, необходимые для выполнения бизнес-транзакции с помощью объектов модели домена. Таким образом команды, просто структур данных, содержащих данные только для чтения и нет поведения. Указывает имя команды, его назначение. Во многих языках, таких как C\#, команды отображаются в виде классов, но они не являются true классов в реальных объектно ориентированного смысла.

Как дополнительные характеристики команды являются неизменяемыми, так как они обрабатываются моделью домена ожидаемого режима использования. Они не должны измениться во время их предполагаемое время существования. В языке C\# класса, неизменность достигается при этом не все задания или другие методы, изменяющие внутреннего состояния.

Например класс команд для создания заказа аналогична, возможно, с точки зрения данных порядке, в котором вы хотите создать, но, возможно, не требуется те же атрибуты. Для экземпляра CreateOrderCommand имеет идентификатор заказа, так как порядок еще не создана.

Многие классы команд могут быть простыми, требует лишь несколько полей о некоторое состояние, которое требуется изменить. Это было бы так при изменении состояния заказа из «выполнение» для только что «платная» или «отправить», используя команду следующего вида:

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

Некоторые разработчики их запроса объекты пользовательского интерфейса отдельно от их DTO команды, однако, является лишь предпочтения. Она является трудоемкой разделение с не added объем работы и объекты имеют практически так же фигуры. Например в eShopOnContainers, команды поступать непосредственно на стороне клиента.

### <a name="the-command-handler-class"></a>Класс обработчика команд

Следует реализовать класс обработчика конкретной команды для каждой команды. Это как шаблон работает, и это, где используется объект команды, объекты домена и объекты репозитория инфраструктуры. Обработчик команд на самом деле является сердцем платформы на уровне приложения с точки зрения CQRS и ддд. Однако вся логика домена должен находиться внутри домена классы — в пределах статистической корни (корневой сущности), дочерних сущностей или [доменных служб](https://lostechies.com/jimmybogard/2008/08/21/services-in-domain-driven-design/), но не в обработчике команды — это класс, из приложения слой.

Обработчик команд получает команды и получает результат из статистическое выражение, которое используется. Результат должен быть успешное выполнение команды или исключение. В случае возникновения исключения состояния системы следует без изменений.

Обычно обработчик команд выполняет следующие действия:

-   Получает объект команды, такие как DTO (из [посредником](https://en.wikipedia.org/wiki/Mediator_pattern) или другой объект инфраструктуры).

-   Она проверяет, что команда является допустимым (если не проверить с помощью посредника).

-   Он создает экземпляр статистические корневого, который является целевым объектом текущую команду.

-   Он выполняет метод на экземпляре статистические корневой получения необходимых данных из команды.

-   Она сохраняет новое состояние агрегатной функции в связанной базе данных. Эта последняя операция является фактические транзакции.

Как правило обработчик команд связана с одной статистической функции, обусловленных статистические корень (корневую сущность). Если несколько статистических выражений должно повлиять на получение одной команды, можно использовать события домена распространяться состояния и действия по несколько статистических выражений

Здесь важно то, что при обработке команды всю логику домена должен быть внутри модели домена (статистические выражения), полностью инкапсулированный и готова для модульного тестирования. Обработчик команд действует только способ получить модель домена из базы данных, а последнее действие, чтобы определить уровень инфраструктуры (репозиториев) для сохранения изменений при смене модели. Преимущество такого подхода является можно выполнить рефакторинг доменную логику модели изолированной, полностью инкапсулированный, широкие возможности, поведения домена без изменения кода в приложении или инфраструктуре слои, которые находятся на уровне направляющее (обработчики команд, веб-API репозиториев и т. д.).

Когда обработчики команд get сложными, слишком большой объем логики, который может быть вонь от кода. Ознакомление с ними, если Доменная логика, рефакторинг кода для перемещения этого поведения домена в методы объектов домена (статистические корневые и дочерние сущности).

В качестве примера класса обработчика команд код отображает тот же класс CreateOrderCommandHandler видно в начале данной главы. В этом случае мы выделения дескриптора метода и операции с домена модели объектов или статистические выражения.

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

Это обработчик команды необходимо выполнить дополнительные действия.

-   Используйте данные команды для работы с корня статистические методы и поведение.

-   Внутренне в объекты домена создавать события, домена, во время выполнения транзакции, но это прозрачное с команда обработчик точки зрения.

-   При успешном выполнении результат операции статистическое выражение и после завершения транзакции, вызывают обработчик команд события интеграции. (Они могут также возникать классами инфраструктуры, например репозиториев.)

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Марк Симанн. Границы, приложения, не объектно-ориентированного**
    [*http://blog.ploeh.dk/2011/05/31/AttheBoundaries, ориентированных на ApplicationsareNotObject /*](http://blog.ploeh.dk/2011/05/31/AttheBoundaries,ApplicationsareNotObject-Oriented/)

-   **Команды и события**
    [*http://cqrs.nu/Faq/commands-and-events*](http://cqrs.nu/Faq/commands-and-events)

-   **Что делает обработчик команд? ** 
     [ *http://cqrs.nu/Faq/command-handlers*](http://cqrs.nu/Faq/command-handlers)

-   **Джимми Богард (Jimmy Bogard). Шаблоны команд домена — обработчики**
    [*https://jimmybogard.com/domain-command-patterns-handlers/*](https://jimmybogard.com/domain-command-patterns-handlers/)

-   **Джимми Богард (Jimmy Bogard). Шаблоны команд домена — проверка**
    [*https://jimmybogard.com/domain-command-patterns-validation/*](https://jimmybogard.com/domain-command-patterns-validation/)

## <a name="the-command-process-pipeline-how-to-trigger-a-command-handler"></a>Процесс конвейере: активация является допустимым обработчиком команд

Следующий вопрос заключается в вызов обработчика команд. Вручную может вызвать его из каждого связанные контроллера ASP.NET Core. Тем не менее что подходом было бы слишком связаны и не идеальное решение.

Другие два основных варианта, которые рекомендуется использовать параметры, являются:

-   Через шаблон артефакта посредника в памяти.

-   Асинхронное сообщение очереди сообщений, между контроллерами и обработчики.

### <a name="using-the-mediator-pattern-in-memory-in-the-command-pipeline"></a>С помощью шаблона посредником (в памяти) в конвейере

Как показано на рисунке 9-21, подход CQRS используется интеллектуальная посредника, аналогично шине в памяти, который способен перенаправить на основе типа команды или получения DTO обработчик команда right. Один черной стрелки между компонентами представляют зависимости между объектами (во многих случаях введенного через DI) с их связанных с ними взаимодействий.

![](./media/image22.png)

**На рисунке 9-21**. С помощью посредника шаблона процесса в одном микрослужбу CQRS

Причина, используя шаблон посредником имеет смысл в том, что в корпоративных приложениях обработки запросов может усложняться. Вы хотите иметь возможность добавить открытые количество решении общих задач ведения журнала, проверки, аудита и безопасности. В таких случаях можно положиться на конвейере посредником (см. [шаблон посредником](https://en.wikipedia.org/wiki/Mediator_pattern)) для предоставления средства эти дополнительные поведения или проблемы пересечения.

Объект, инкапсулирующий «как» этого процесса является посредником: он координирует выполнение на основе состояния, вызывается метод обработчика команды или полезные данные, указываемые в обработчик. С компонентом посредником можно применить проблемы пересечения централизованное и прозрачным способом, применяя декораторов (или [конвейер поведений](https://github.com/jbogard/MediatR/wiki/Behaviors) с момента посредником v3). (Дополнительные сведения см. в разделе [шаблон Decorator](https://en.wikipedia.org/wiki/Decorator_pattern).)

Поведение и декораторы аналогичны [аспект ориентированного программирования (AOP)](https://en.wikipedia.org/wiki/Aspect-oriented_programming)только для применения конвейер определенного процесса, управляемого компонентом посредником. Аспекты в AOP, реализующих проблемы пересечения применяются на основе *weavers аспект* введенного во время компиляции или на основании перехвата объекта вызова. Оба типичные подходы AOP иногда называются работать «как magic», так как он не легко увидеть, каким образом AOP выполняет свою работу. При работе с серьезной проблемы или ошибки, AOP может быть трудно отлаживать. С другой стороны декораторы и поведение являются явные и применяется только в контексте посредника, поэтому отладка гораздо большей предсказуемостью и легко.

Например, в eShopOnContainers, упорядочение микрослужбу, мы реализовали декораторов два образца, [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) класса и [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) класса. В следующем разделе описывается реализация декоратор. Обратите внимание, что в будущих версиях eShopOnContainers перенесет [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) и переместить [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) вместо использования декораторов.

### <a name="using-message-queues-out-of-proc-in-the-commands-pipeline"></a>С помощью очереди сообщений (вне процесса) в конвейере команд

Другой вариант — использование асинхронных сообщений на основе брокеров или очереди сообщений, как показано на рисунке 9-22. Этот параметр может быть совмещена с компонент посредником прямо перед обработчик команд.

![](./media/image23.png)

**На рисунке 9-22**. С помощью очереди сообщений (вне процесса и связи между процессами) с помощью команд CQRS

С помощью сообщений очереди, чтобы принять дополнительные команды могут усложнить конвейера в команду, так как, возможно, понадобится разбиение конвейера на два процесса подключается через внешние сообщения очереди. Тем не менее ее следует использовать, если необходимо повышение масштабируемости и производительности в зависимости от асинхронного обмена сообщениями. Примите во внимание в случае рисунок 9 – 22, просто контроллер отправляет сообщение команды в очередь и возвращает. Затем обработчик команды обработку сообщений в своем темпе. То есть значительные преимущества очередей — очереди сообщений может выступать в качестве буфера в случаях при необходимости, например, биржевые сводки или любом другом сценарии, с большим объемом входящих данных hyper масштабируемости.

Однако из-за характера асинхронной очереди сообщений, необходимо понять, как взаимодействовать с клиентским приложением об успешном или неуспешном процесса команды. Как правило никогда не следует использовать команды «Отправить и забыть». Каждый бизнес-приложение должно быть известно, если команда была обработана успешно, или по крайней мере проверки и принято.

Таким образом не сможет отвечать клиенту после проверки команда сообщения, отправленного в очередь асинхронных усложняет систему по сравнению с процесс команды в процессе, который возвращает результат операции после запуска транзакции. С использованием очередей, может потребоваться вернуть результат процесс команды с помощью других сообщений результат операции, которые требуют дополнительных компонентов и пользовательские связи в системе.

Кроме того, команды async, односторонний команды, в которых во многих случаях может не потребоваться, как описано в следующих интересные обмена данными между Алексей Burtsev и Янг Грег в [обсуждения](https://groups.google.com/forum/#!msg/dddcqrs/xhJHVxDx2pM/WP9qP8ifYCwJ):

\[Алексей Burtsev\] найти множество кода которых используется обработка асинхронных команд или одним из способов команды, обмен сообщениями без какой-либо причине, чтобы сделать это (они не реализуют некоторые длительной операции, они не выполняются внешних асинхронного кода, они даже не пересекали приложения граница будет использовать канал сообщений). Почему они вызвать это излишнее усложнение? И в действительности не видели пример кода CQRS с на данный момент блокирует обработчики команд на то, что он будет работать корректно, в большинстве случаев.

\[Грег Янг\] \[... \] асинхронную команду не существует; это фактически другое событие. Если необходимо принять, что вы отправлять мне и инициировать событие, если не принимаю, он больше не вы говорите каким-либо. Это действительно вы сообщает, что-то было сделано. На первый взгляд незначительные различия на первый, но она влияет на множество.

Асинхронные команды значительно увеличивается сложность системы, так как нет простого способа сведения о сбоях. Таким образом асинхронных команд не рекомендуются отличный от при масштабировании требования или в особых случаях при взаимодействии внутренней микрослужбами посредством обмена сообщениями. В таких случаях необходимо создать отдельные отчеты и восстановления системы сбоев.

В первоначальную версию eShopOnContainers мы решили использовать обработку синхронных команд, запущен из HTTP-запросы и набором шаблон посредником. Легко позволяет вернуться успешность процесса, как и в [CreateOrderCommandHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Commands/CreateOrderCommandHandler.cs) реализации.

В любом случае это должна быть принятия решений, в зависимости от приложения или элемента микрослужбу бизнес-требований.

## <a name="implementing-the-command-process-pipeline-with-a-mediator-pattern-mediatr"></a>Реализация конвейера процесса команда посредником шаблоном (MediatR)

Как образец реализации в этом руководстве предлагаются с помощью конвейера в процессе на основе шаблона посредника для приема команда диска и маршрутизации, в памяти, обработчиками команд вправо. Руководство предлагает применение декораторов или [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) для разделения проблемы пересечения.

Для реализации в .NET Core нет несколько открытая библиотеки доступны, реализующих шаблон посредником. В этом руководстве используется библиотека [MediatR](https://github.com/jbogard/MediatR) библиотеки открытым исходным кодом (созданное Джимми Богард), но может использовать другой подход. MediatR — это библиотека небольших и простых, которая позволяет обрабатывать сообщения в памяти как команды, при применении декораторов или поведения.

С помощью шаблона посредником помогает уменьшить взаимозависимости и изолировать проблемы запрашиваемую работу при автоматическом соединении обработчик, который выполняет эту работу — в этом случае для обработчиков команд.

Другой веская причина для использования шаблона посредником объяснялось, Джимми Богард при просмотре в этом руководстве:

Я думаю, возможно, следует упомянуть здесь тестирование — он предоставляет окно согласованной работы с низким приоритетом в поведение системы. В запрос, выход ответа. Мы обнаружили этого аспекта весьма ценным в здании согласованно работает тестов.

Во-первых сообщите нам взгляните на код контроллера когда фактически используется объект посредником. Если вы не используете объект посредником, необходимо ввести все зависимости для контроллера, такие как объект средства ведения журнала и другие. Таким образом конструктор будет довольно сложными. С другой стороны Если вы используете объект посредником, конструктор контроллера может быть гораздо проще всего несколько зависимостей вместо много зависимостей, которые потребовалось бы, если у вас есть по одному на операцию пересечения, как показано в следующем примере:

```csharp
public class OrdersController : Controller
{
    public OrdersController(IMediator mediator,
        IOrderQueries orderQueries)
    // ...
```

Вы увидите, что посредника предоставляет чистого и экономичных конструктором контроллера веб-API. Кроме того в методы контроллера, код для отправки команды к объекту посредником, почти одну строку:

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

Чтобы MediatR следует учитывать классов обработчика команды необходимо зарегистрировать посредником классов и классов обработчика команд в контейнер IoC. По умолчанию MediatR Autofac используется как контейнер IoC, но можно также использовать встроенные контейнер ASP.NET Core IoC или любым другим контейнером, поддерживаемый MediatR.

Следующий код показано, как зарегистрировать типы посредником и команд при использовании Autofac модулей.

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

Поскольку каждый обработчик команд реализует интерфейс с универсальным IAsyncRequestHandler&lt;T&gt; и затем просматривает RegisteredAssemblyTypes объекта обработчик возможность связать каждую команду его обработчик команд, так как, отношение выражается в классе CommandHandler, как показано в следующем примере:

```csharp
public class CreateOrderCommandHandler
  : IAsyncRequestHandler<CreateOrderCommand, bool>
{
```

Это код, который сопоставляет команды с обработчиков команд. Обработчик является простой класс, но он наследует RequestHandler&lt;T&gt;, и MediatR обеспечивает ее вызова возвращает правильный полезных данных.

## <a name="applying-cross-cutting-concerns-when-processing-commands-with-the-mediator-and-decorator-patterns"></a>Применение перекрестными проблемы при обработке команды с шаблонами посредника и Decorator

Есть еще одно: возможность применить при решении общих задач в конвейере посредником. Можно также просмотреть в конце код модуля регистрации Autofac как регистрирующий декоратор введите, в частности, пользовательский класс LogDecorator.

Обратите внимание, что будущая версия eShopOnContainers она будет перемещена [MediatR 3](https://www.nuget.org/packages/MediatR/3.0.0) и переместить [поведения](https://github.com/jbogard/MediatR/wiki/Behaviors) вместо использования декораторов.

Что [LogDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/LogDecorator.cs) класса могут быть реализованы как следующий код, который записывает сведения о выполняемой обработчик команд и был успешно или нет.

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

Просто путем реализации этого класса decorator и дополняя конвейера с ним всех команд, обработанных с помощью MediatR входа сведения о выполнении.

EShopOnContainers упорядочение микрослужбу также применяется декоратор второй основных проверок [ValidatorDecorator](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Decorators/ValidatorDecorator.cs) класс, который зависит от [FluentValidation](https://github.com/JeremySkinner/FluentValidation) библиотеки, как показано в Следующий код:

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

Затем на основе [FluentValidation](https://github.com/JeremySkinner/FluentValidation) библиотеки, мы создали проверки для данных, передаваемых с CreateOrderCommand, как показано в следующем коде:

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

Можно создать дополнительные проверки. Это очень простой и элегантный способ реализации проверки вашей команды.

Аналогичным образом можно реализовать другие декораторов Дополнительные аспекты или решении общих задач, которые необходимо применить к командам, при их обработке.

#### <a name="additional-resources"></a>Дополнительные ресурсы

##### <a name="the-mediator-pattern"></a>Шаблон посредника

-   **Шаблон посредником**
    [*https://en.wikipedia.org/wiki/Mediator\_шаблон*](https://en.wikipedia.org/wiki/Mediator_pattern)

##### <a name="the-decorator-pattern"></a>Шаблон decorator

-   **Шаблон декоратора**
    [*https://en.wikipedia.org/wiki/Decorator\_шаблон*](https://en.wikipedia.org/wiki/Decorator_pattern)

##### <a name="mediatr-jimmy-bogard"></a>MediatR (Джимми Богард)

-   **MediatR.** В репозитории GitHub.
    [*https://github.com/jbogard/MediatR*](https://github.com/jbogard/MediatR)

-   **CQRS с MediatR и AutoMapper**
    [*https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/*](https://lostechies.com/jimmybogard/2015/05/05/cqrs-with-mediatr-and-automapper/)

-   **Разместить контроллеры на диеты: в блогах и команд. ** 
     [ *https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/*](https://lostechies.com/jimmybogard/2013/12/19/put-your-controllers-on-a-diet-posts-and-commands/)

-   **Решение проблемы пересечения с конвейером посредником**
    [*https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/*](https://lostechies.com/jimmybogard/2014/09/09/tackling-cross-cutting-concerns-with-a-mediator-pipeline/)

-   **CQRS и REST: найденного совпадения**
    [*https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/*](https://lostechies.com/jimmybogard/2016/06/01/cqrs-and-rest-the-perfect-match/)

-   **Примеры конвейера MediatR**
    [*https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/*](https://lostechies.com/jimmybogard/2016/10/13/mediatr-pipeline-examples/)

-   **Основы для вертикального ползунка тестирования MediatR и ASP.NET Core**
    *<https://lostechies.com/jimmybogard/2016/10/24/vertical-slice-test-fixtures-for-mediatr-and-asp-net-core/>*

-   **MediatR расширений для внедрения зависимостей Корпорация Майкрософт выпустила**
    [*https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/*](https://lostechies.com/jimmybogard/2016/07/19/mediatr-extensions-for-microsoft-dependency-injection-released/)

##### <a name="fluent-validation"></a>Fluent проверки

-   **Скиннер Jeremy. FluentValidation.** В репозитории GitHub.
    [*https://github.com/JeremySkinner/FluentValidation*](https://github.com/JeremySkinner/FluentValidation)

>[!div class="step-by-step"]
[Предыдущие] (microservice-application-layer-web-api-design.md) [Далее] (.. /Implement-Resilient-Applications/index.MD)
