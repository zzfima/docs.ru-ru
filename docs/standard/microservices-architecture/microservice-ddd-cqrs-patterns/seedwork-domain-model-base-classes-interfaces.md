---
title: "Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="503ae-104">Seedwork (многократно используемые базовые классы и интерфейсы для модели домена)</span><span class="sxs-lookup"><span data-stu-id="503ae-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="503ae-105">Папка решения содержит *SeedWork* папки.</span><span class="sxs-lookup"><span data-stu-id="503ae-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="503ae-106">*SeedWork* папка содержит пользовательские базовые классы, которые можно использовать в качестве базы для вашего домена сущностей и объектов значение.</span><span class="sxs-lookup"><span data-stu-id="503ae-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="503ae-107">Используйте эти базовые классы, поэтому нет избыточный код в класс объекта для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="503ae-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="503ae-108">Папка для этих типов классов называется *SeedWork* , а не то, как *Framework*.</span><span class="sxs-lookup"><span data-stu-id="503ae-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="503ae-109">Он вызывается *SeedWork* , так как папка содержит только небольшое подмножество многократно используемые классы, которые действительно не может считаться платформу.</span><span class="sxs-lookup"><span data-stu-id="503ae-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="503ae-110">*Seedwork* термин введенный [Майкла Физерса](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) и Кроме того, [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) , но можно также назвать эту папку Общие, SharedKernel, или же.</span><span class="sxs-lookup"><span data-stu-id="503ae-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="503ae-111">Рис. 9-12 показывает классы, формирующие seedwork модели домена в микрослужбу порядка сортировки.</span><span class="sxs-lookup"><span data-stu-id="503ae-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="503ae-112">Он имеет несколько пользовательских базовых классов сущностей, ValueObject и перечисления, а также несколько интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="503ae-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="503ae-113">Эти интерфейсы (IRepository и IUnitOfWork) уровень инфраструктуры сообщают о том, что должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="503ae-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="503ae-114">Эти интерфейсы также используются через внедрения зависимости от уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="503ae-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="503ae-115">**Рис. 9-12**.</span><span class="sxs-lookup"><span data-stu-id="503ae-115">**Figure 9-12**.</span></span> <span data-ttu-id="503ae-116">Образец набора домена модели «seedwork» базовые классы и интерфейсы</span><span class="sxs-lookup"><span data-stu-id="503ae-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="503ae-117">Это тип, копировать и вставить многократного использования, многие разработчики совместно использовать проектов, не формальных framework.</span><span class="sxs-lookup"><span data-stu-id="503ae-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="503ae-118">Может иметь seedworks в любой уровень или в библиотеке.</span><span class="sxs-lookup"><span data-stu-id="503ae-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="503ae-119">Тем не менее если набор классов и интерфейсов получает достаточно большой, может потребоваться создание одной библиотеке классов.</span><span class="sxs-lookup"><span data-stu-id="503ae-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="503ae-120">Пользовательские сущности базового класса</span><span class="sxs-lookup"><span data-stu-id="503ae-120">The custom Entity base class</span></span>

<span data-ttu-id="503ae-121">Ниже приведен пример базового класса сущности расположения кода, который может использоваться так же, как любой сущности домена, такие как идентификатор сущности, [операторы равенства](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx)и т. д.</span><span class="sxs-lookup"><span data-stu-id="503ae-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="503ae-122">Репозиторий контрактов (интерфейсы), в уровне модели домена</span><span class="sxs-lookup"><span data-stu-id="503ae-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="503ae-123">Репозиторий контракты являются просто интерфейсы платформы .NET, представляющие контрактом требований репозиториями для каждого статистического выражения.</span><span class="sxs-lookup"><span data-stu-id="503ae-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="503ae-124">Сами репозиториями с EF основного кода или другие зависимости инфраструктуры и кодом, не должен быть реализован в пределах модели домена; репозиториями только должен реализовывать интерфейсы, определенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="503ae-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="503ae-125">Разделенные интерфейс является шаблон, связанные с такой подход (разместите интерфейсы репозитория в уровне модели домена).</span><span class="sxs-lookup"><span data-stu-id="503ae-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="503ae-126">Как [описано](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) по Martin Fowler «интерфейс Separated используется для определения интерфейса в одном пакета, но реализовать его в другой.</span><span class="sxs-lookup"><span data-stu-id="503ae-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="503ae-127">Таким образом клиент, который требуется зависимостей на интерфейс может быть малейшего реализации.»</span><span class="sxs-lookup"><span data-stu-id="503ae-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="503ae-128">Следующий шаблон запятыми интерфейс позволяет на уровне приложения (в данном случае проект веб-API для микрослужбу) на зависимость для требований, которые определены в модели домена, а не прямой зависимости инфраструктуры и сохраняемости слой.</span><span class="sxs-lookup"><span data-stu-id="503ae-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="503ae-129">Кроме того, можно использовать для изоляции реализацию, которая реализована в инфраструктуре внедрения зависимостей и уровень сохраняемости с помощью репозиториев.</span><span class="sxs-lookup"><span data-stu-id="503ae-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="503ae-130">Например в следующем примере с помощью интерфейса IOrderRepository определяется какие операции OrderRepository класс должен реализовывать на уровне инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="503ae-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="503ae-131">В текущей реализации приложения код просто необходимо добавить порядок в базе данных, так как запросы являются следующие разбиение CQS подход и обновления заказов не реализована.</span><span class="sxs-lookup"><span data-stu-id="503ae-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a><span data-ttu-id="503ae-132">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="503ae-132">Additional resources</span></span>

-   <span data-ttu-id="503ae-133">**Мартин Фоулер (Martin Fowler). Интерфейс, разделенных запятыми. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="503ae-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="503ae-134">[Предыдущие] (net-core микрослужбу домена model.md) [Далее] (objects.md реализуйте значение)</span><span class="sxs-lookup"><span data-stu-id="503ae-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
