---
title: "Реализация модели домена микрослужбу с .NET Core"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализация модели домена микрослужбу с .NET Core"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a>Реализация модели домена микрослужбу с .NET Core 

В предыдущем разделе были представлены основные принципы и шаблоны для проектирования модели домена. Теперь настало время для изучения способов реализации модели домена с помощью .NET Core (plain C\# кода) и EF Core. Обратите внимание, что модель домена будет состоять просто из кода. Он будет иметь только EF основных требований модели, но не реальными зависимости EF. Не следует жестких зависимостей или ссылки на основные EF или любые другие ORM в модели домена.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Структура модели домена в пользовательская библиотека .NET Standard

Используется для приложений ссылки eShopOnContainers организации папки демонстрирует DDD модели для приложения. Может оказаться, что организация другую папку более четко взаимодействует конструктора, выбранные для вашего приложения. Как видно на рисунке 9-10 упорядочивания модели домена существует два статистических выражений, статистическое выражение order и покупатель агрегатной функции. Каждый агрегат — это группа домена сущностей и объектов значение, несмотря на то, что у вас может быть статистического выражения, состоящие из одного домена сущности (статистические корневой или корневую сущность) также.

![](./media/image11.png)

**Рис. 9-10**. Структура модели домена для упорядочивания микрослужбу в eShopOnContainers

Кроме того уровень модели домена содержит контракты репозитория (интерфейсы), которые требований к инфраструктуре модели домена. Другими словами, эти интерфейсы express репозиториев, какие необходимо реализовать уровень инфраструктуры и каким образом. Очень важно, что реализация репозиториями располагаться за пределами уровень модели домена, в библиотеке инфраструктуры слоя, уровень модели домена не «окрашены» API или классы из технологий инфраструктуры, такие как Entity Framework.

Можно также просмотреть [SeedWork](https://martinfowler.com/bliki/Seedwork.html) папку, содержащую пользовательские базовые классы, которые можно использовать в качестве базы для сущности домена и значение объектов, поэтому нет избыточный код в класс объекта для каждого домена.

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a>Структурирование статистические выражения в пользовательская библиотека .NET Standard

Статистическое выражение ссылается на кластере объекты домена, сгруппированных для сопоставления согласованность транзакций. Плюс любые объекты дополнительное значение этих объектов может быть экземпляры сущностей (один из которых является корневой статистические или корневой объект).

Согласованность транзакций означает, что статистическое гарантированно согласованное и обновлен на конец действия бизнес. Например порядок статистическое выражение из eShopOnContainers, упорядочение модель домена микрослужбу состоит как показано на рисунке 9-11.

![](./media/image12.png)

**Рис. 9-11**. Порядок агрегатных в решении Visual Studio

При открытии этих файлов в папке aggregate, вы увидите как она помечена как пользовательского базового класса или интерфейса, как сущность или значение объекта, как осуществляется в [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) папки.

## <a name="implementing-domain-entities-as-poco-classes"></a>Реализация сущностей домена как классов POCO

Реализуйте модель домена в .NET путем создания классов POCO, реализующих сущности домена. В следующем примере определяется класс Order, как сущность, а также как статистические корневой каталог. Поскольку класс Order является производным от базового класса сущности, можно повторно использовать общий код, относящиеся к сущности. Не забывайте, что эти базовые классы и интерфейсы определяются вы в проекте модели домена, поэтому код, с ORM как EF не код инфраструктуры.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

Это важно отметить, что это сущности домена, реализованы в виде класса POCO. Он не имеет прямой зависимости в Entity Framework Core или любой другой структуре инфраструктуры. Эта реализация является ожидаемым значениям, просто C\# код, реализующий модель домена.

Кроме того класс снабжен интерфейс с именем IAggregateRoot. Этот интерфейс является пустой интерфейс, иногда называется *интерфейс-маркер*, в котором используется только для указания, что этого класса сущности также корневого каталога статистические.

Иногда интерфейс считается антишаблон; Однако это также чистой способ пометить класс, особенно в том случае, если этот интерфейс может развивается. Атрибут может быть другой Выбор маркера, но проще и быстрее просмотреть базовый класс (сущности) рядом с интерфейс IAggregate вместо того, чтобы маркер на статистическом атрибуте выше класса. Это metter предпочтений, в любом случае.

Наличие статистических корневой означает, что большая часть кода, связанные с согласованности и бизнес-правила сущностей статистической функции должны быть реализованы как методы в классе корневого статистические заказа (например, AddOrderItem при добавлении объекта к OrderItem статистического выражения) . Не следует создать или обновить объекты OrderItems независимо друг от друга или напрямую. Класс AggregateRoot должно сохраняться, управления и согласованность любой операции обновления от его дочерних сущностей.

Например, вы должны *не* выполните следующие действия на любой обработчик метода или приложения уровня класс команд:

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

В этом случае метод Add может выполняться исключительно для добавления данных с прямой доступ к коллекции OrderItems. Таким образом большая часть логики домена, правил или проверки, относящиеся к, операции с на дочерние объекты будут распределяться на уровне приложения (обработчики команд и контроллеров веб-API).

При переходе вокруг статистические корневой статистические корневой не может гарантировать его инварианты его действительность и ее согласованности. В конечном итоге будет иметь тестированию кода или код скрипта транзакций.

Следовать DDD шаблонов, сущности не должен иметь открытый задания все свойства сущности. Изменения в сущности должны управляться явные методы с явной единый язык об изменениях, которые они выполняют в сущности.

Кроме того, коллекции сущности (например, элементов заказа), должны быть только для чтения свойства (метод AsReadOnly рассматривается позже). Вы сможете обновить его только из внутри корневой статистические методы класса или дочерних методов сущности.

Как видно в коде для корня статистические порядок, все задания должны быть закрытым или хотя бы доступны только для чтения извне, чтобы выполнения любой операции над сущности данных или ее дочерних сущностей должно выполняться с помощью методов в классе сущностей. Это обеспечивает согласованность управляемой и объектно ориентированного способом вместо реализации код скрипта транзакций.

В следующем фрагменте кода показан правильный способ кодирования задачу при добавлении объекта OrderItem статистическое выражение Order.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

В этом фрагменте кода большинство проверки и процедуры, относящиеся к созданию объекта OrderItem будут управляться статистические корневого заказа — в методе AddOrderItem — особенно проверок и логику, связанные с другими элементами в агрегатной. Например можно получить тот же элемент продукта, в результате нескольких вызовов AddOrderItem. В этом методе можно проверить элементы по продукту и консолидировать тем же элементам продукта в один объект OrderItem с несколькими единицами. Кроме того Если существуют разные скидки суммы, но идентификатор продукта совпадает, скорее всего применить выше скидки. Этот принцип применяется к другой логики домена OrderItem объекта.

Кроме того новая операция OrderItem(params) также быть управляются и выполняемое методом AddOrderItem от корня статистические заказа. Таким образом большая часть логики или проверкам, относящиеся к что операция (особенно все, что влияет на согласованность между другими сущностями дочернего) будет в одном месте в пределах статистической корневого каталога. Это назначение ultimate статистические корневой шаблон.

При использовании Entity Framework 1.1 сущности DDD можно выполнить быстрее, так как одна из новых функций Entity Framework Core 1.1 является то, что [сопоставление с полями](https://docs.microsoft.com/ef/core/modeling/backing-field) Помимо свойств. Это полезно при защите коллекции дочерних сущностей или объектов значение. Это улучшение можно использовать простой закрытых полей вместо свойств и вы реализовать любое обновление для коллекции полей в открытых методов и предоставить доступ только для чтения в методе AsReadOnly.

Поэтому ддд, необходимо обновить только через методы в сущности (или конструктор), чтобы управлять любой инвариантный и согласованность данных в сущности, свойства определяются только с методом доступа get. Закрытые поля, поддерживаемых свойств. Закрытые члены может осуществляться только из класса. Однако есть одно исключение: необходимо установить эти поля также EF Core.

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Сопоставление свойств только с методы доступа get для поля в таблице базы данных

Сопоставления свойств для столбцов таблицы базы данных не ответственности домена, но часть слоя инфраструктуры и сохраняемость. Мы ссылаются на этот здесь точно так же, поэтому существует вероятность, новые возможности в версии 1.1 EF, относящиеся к как можно моделировать сущности. Дополнительные сведения по этой теме описаны в разделе инфраструктуры и сохраняемость.

При использовании EF 1.0, в течение DbContext, необходимо сопоставить свойства, которые определены только для методов получения фактического полей в таблице базы данных. Это делается с помощью метода HasField PropertyBuilder класса.

### <a name="mapping-fields-without-properties"></a>Сопоставление полей без свойств

С помощью новой функции в версии 1.1 Core EF для сопоставления столбцов с полями можно также использовать свойства не. Вместо этого можно сопоставить только столбцы из таблицы с полями. Распространенным вариантом применения для этого является закрытым полям для внутреннего состояния, не должны быть доступны извне сущности.

Например, в предыдущем примере \_someOrderInternalState поле не имеет связанных свойств для setter или getter. Это поле также вычисляются в порядке бизнес-логики и будут использоваться с помощью методов заказа, но он должен быть сохранен в базе данных также. Таким образом в версии 1.1 EF дает возможность сопоставить поле без связанного свойства со столбцом в базе данных. Это также объясняется [уровень инфраструктуры](#the-infrastructure-layer) данного руководства.

### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Вон Вернон (Vaughn Vernon). Моделирование агрегаты с DDD и Entity Framework.** Обратите внимание, что это *не* Entity Framework Core.
    [*https://vaughnvernon.co/?p=879*](https://vaughnvernon.co/?p=879)

-   **Джули Лерман. Кодирование для разработки на основе домена: советы по ориентированные на данные разработчики**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)

-   **UDI Dahan. Как создать полностью инкапсулирован моделей домена**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)


>[!div class="step-by-step"]
[Предыдущие] (микрослужбу домена model.md) [Далее] (seedwork-domain-model-base-classes-interfaces.md)
