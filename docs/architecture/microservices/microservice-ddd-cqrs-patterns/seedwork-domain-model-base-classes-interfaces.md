---
title: Seedwork (многократно используемые базовые классы и интерфейсы для модели предметной области)
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Использование концепции seedwork в качестве отправной точки для запуска реализации для модели предметной области, ориентированной на DDD.
ms.date: 10/08/2018
ms.openlocfilehash: ab0aadc28dbd1175c75b04dadca29b7b0947f29b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116565"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="1200e-103">Seedwork (многократно используемые базовые классы и интерфейсы для модели предметной области)</span><span class="sxs-lookup"><span data-stu-id="1200e-103">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="1200e-104">В папке решения имеется папка *SeedWork*.</span><span class="sxs-lookup"><span data-stu-id="1200e-104">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="1200e-105">В этой папке содержатся пользовательские базовые классы, которые можно использовать в качестве основы для сущностей предметной области и объектов значений.</span><span class="sxs-lookup"><span data-stu-id="1200e-105">This folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="1200e-106">Используйте эти базовые классы, чтобы не было избыточного кода в классе объектов каждого домена.</span><span class="sxs-lookup"><span data-stu-id="1200e-106">Use these base classes so you don't have redundant code in each domain’s object class.</span></span> <span data-ttu-id="1200e-107">Папка для этих типов классов называется *SeedWork*, а не как-нибудь похоже на *Framework*.</span><span class="sxs-lookup"><span data-stu-id="1200e-107">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="1200e-108">Эта папка называется *SeedWork*, так как в ней содержится только небольшое подмножество многократно используемых классов, которое в действительности не может считаться структурой.</span><span class="sxs-lookup"><span data-stu-id="1200e-108">It's called *SeedWork* because the folder contains just a small subset of reusable classes that cannot really be considered a framework.</span></span> <span data-ttu-id="1200e-109">Термин *Seedwork* был введен [Майклом Фезерсом (Michael Feathers)](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) и получил распространение благодаря [Мартину Фаулеру (Martin Fowler)](https://martinfowler.com/bliki/Seedwork.html), но можно также назвать эту папку Common, SharedKernel или аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="1200e-109">*Seedwork* is a term introduced by [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="1200e-110">На рис. 7-12 показаны классы, формирующие набор seedwork модели предметной области в микрослужбе заказов.</span><span class="sxs-lookup"><span data-stu-id="1200e-110">Figure 7-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="1200e-111">В нем имеется несколько пользовательских базовых классов, таких как Entity, ValueObject и Enumeration, а также несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1200e-111">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="1200e-112">Эти интерфейсы (IRepository и IUnitOfWork) информируют уровень инфраструктуры о том, что должно быть реализовано.</span><span class="sxs-lookup"><span data-stu-id="1200e-112">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="1200e-113">Эти интерфейсы также используются через внедрение зависимостей из прикладного уровня.</span><span class="sxs-lookup"><span data-stu-id="1200e-113">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Снимок экрана: классы, содержащиеся в папке SeedWork.":::
<span data-ttu-id="1200e-115">Подробное содержимое папки SeedWork, содержащей базовые классы и интерфейсы: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs и ValueObject.cs.</span><span class="sxs-lookup"><span data-stu-id="1200e-115">The detailed contents of the SeedWork folder, containing base classes and interfaces: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs, and ValueObject.cs.</span></span>
:::image-end:::

<span data-ttu-id="1200e-116">**Рис. 7-12**.</span><span class="sxs-lookup"><span data-stu-id="1200e-116">**Figure 7-12**.</span></span> <span data-ttu-id="1200e-117">Пример набора базовых классов и интерфейсов "seedwork" модели предметной области</span><span class="sxs-lookup"><span data-stu-id="1200e-117">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="1200e-118">Это разновидность копирования и вставки, которую многие разработчики используют в проектах, а не формальная структура.</span><span class="sxs-lookup"><span data-stu-id="1200e-118">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="1200e-119">Вы можете иметь наборы seedwork на любом уровне или в любой библиотеке.</span><span class="sxs-lookup"><span data-stu-id="1200e-119">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="1200e-120">Однако если набор классов и интерфейсов становится достаточно большим, вам может понадобиться создать единую библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="1200e-120">However, if the set of classes and interfaces gets large enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="1200e-121">Пользовательский базовый класс Entity</span><span class="sxs-lookup"><span data-stu-id="1200e-121">The custom Entity base class</span></span>

<span data-ttu-id="1200e-122">Следующий код представляет пример базового класса Entity, где можно разместить код, который может многократно использоваться тем же способом в любой сущности предметной области, например идентификатор сущности, [операторы равенства](../../../csharp/language-reference/operators/equality-operators.md), список событий предметной области по сущностям и т. п.</span><span class="sxs-lookup"><span data-stu-id="1200e-122">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](../../../csharp/language-reference/operators/equality-operators.md), a domain event list per entity, etc.</span></span>

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;
    private List<INotification> _domainEvents;
    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://docs.microsoft.com/archive/blogs/ericlippert/guidelines-and-rules-for-gethashcode
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

<span data-ttu-id="1200e-123">Предыдущий код, использующий список событий предметной области по сущностям, будет рассматриваться в следующих разделах при изучении событий предметной области.</span><span class="sxs-lookup"><span data-stu-id="1200e-123">The previous code using a domain event list per entity will be explained in the next sections when focusing on domain events.</span></span>

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="1200e-124">Контракты репозиториев (интерфейсы) на уровне модели предметной области</span><span class="sxs-lookup"><span data-stu-id="1200e-124">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="1200e-125">Контракты репозиториев являются просто интерфейсами .NET, выражающими требования контрактов репозиториев, которые должны использоваться для каждого агрегата.</span><span class="sxs-lookup"><span data-stu-id="1200e-125">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span>

<span data-ttu-id="1200e-126">Сами по себе репозитории, с кодом EF Core или любыми другими зависимостями инфраструктуры и кодом (Linq, SQL и т. п.), не должны реализовываться в рамках модели предметной области; репозитории должны только реализовывать интерфейсы, определенные вами в модели предметной области.</span><span class="sxs-lookup"><span data-stu-id="1200e-126">The repositories themselves, with EF Core code or any other infrastructure dependencies and code (Linq, SQL, etc.), must not be implemented within the domain model; the repositories should only implement the interfaces you define in the domain model.</span></span>

<span data-ttu-id="1200e-127">С этим подходом (размещение интерфейсов репозиториев на уровне модели предметной области) связан шаблон Separated Interface (разделенного интерфейса).</span><span class="sxs-lookup"><span data-stu-id="1200e-127">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="1200e-128">Как [объяснил](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Мартин Фаулер, "используйте шаблон Separated Interface для определения интерфейса в одном пакете и реализации его в другом.</span><span class="sxs-lookup"><span data-stu-id="1200e-128">As [explained](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="1200e-129">Таким образом, клиент, которому требуется зависимость от интерфейса, может ничего не знать о реализации".</span><span class="sxs-lookup"><span data-stu-id="1200e-129">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="1200e-130">Использование шаблона Separated Interface позволяет прикладному уровню (в данном случае это проект веб-API для микрослужбы) иметь зависимость от требований, определенных в модели предметной области, но не прямую зависимость от уровня инфраструктуры или существования.</span><span class="sxs-lookup"><span data-stu-id="1200e-130">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="1200e-131">Кроме того, вы можете использовать внедрение зависимостей для изоляции реализации, которая реализована на уровне инфраструктуры или существования с помощью репозиториев.</span><span class="sxs-lookup"><span data-stu-id="1200e-131">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="1200e-132">Например, в следующем примере с интерфейсом IOrderRepository определяется, какие операции класс OrderRepository должен будет реализовывать на уровне инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="1200e-132">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="1200e-133">В текущей реализации приложения код должен просто добавлять или обновлять заказы в базе данных, так как согласно упрощенному подходу CQRS запросы разделяются.</span><span class="sxs-lookup"><span data-stu-id="1200e-133">In the current implementation of the application, the code just needs to add or update orders to the database, since queries are split following the simplified CQRS approach.</span></span>

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="1200e-134">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="1200e-134">Additional resources</span></span>

- <span data-ttu-id="1200e-135">**Мартин Фоулер (Martin Fowler). Отделяемый интерфейс.**</span><span class="sxs-lookup"><span data-stu-id="1200e-135">**Martin Fowler. Separated Interface.**</span></span> \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
><span data-ttu-id="1200e-136">[Назад](net-core-microservice-domain-model.md)
>[Вперед](implement-value-objects.md)</span><span class="sxs-lookup"><span data-stu-id="1200e-136">[Previous](net-core-microservice-domain-model.md)
[Next](implement-value-objects.md)</span></span>
