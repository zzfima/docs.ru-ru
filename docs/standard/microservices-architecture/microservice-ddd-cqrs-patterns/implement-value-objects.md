---
title: "Реализации объектов значение"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Реализации объектов значение"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a><span data-ttu-id="72423-104">Реализации объектов значение</span><span class="sxs-lookup"><span data-stu-id="72423-104">Implementing value objects</span></span>

<span data-ttu-id="72423-105">Как отмечалось в предыдущих разделах о сущностях и статистические выражения, удостоверения — это основа для сущностей.</span><span class="sxs-lookup"><span data-stu-id="72423-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="72423-106">Тем не менее существует множество объектов и элементов данных в системе, не требующих идентификацию и отслеживание, такие как значение объектов.</span><span class="sxs-lookup"><span data-stu-id="72423-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="72423-107">Объект значения можно ссылаться на другие сущности.</span><span class="sxs-lookup"><span data-stu-id="72423-107">A value object can reference other entities.</span></span> <span data-ttu-id="72423-108">Например, в приложении, которое создает маршрут, который содержит сведения о получении из одной точки в другую этот маршрут будет объект значения.</span><span class="sxs-lookup"><span data-stu-id="72423-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="72423-109">Было бы моментальный снимок точек на конкретный маршрут, но предлагаемый маршрута не будет удостоверение, несмотря на то, что внутренне оно может ссылаться на сущности, такие как город, дорожный, и т. д.</span><span class="sxs-lookup"><span data-stu-id="72423-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="72423-110">Рис. 9-13 показано значение адреса объекта в статистическое выражение Order.</span><span class="sxs-lookup"><span data-stu-id="72423-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="72423-111">**Рис. 9-13**.</span><span class="sxs-lookup"><span data-stu-id="72423-111">**Figure 9-13**.</span></span> <span data-ttu-id="72423-112">Значение объекта в порядке статистическое выражение адреса</span><span class="sxs-lookup"><span data-stu-id="72423-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="72423-113">Как показано на рисунке 9-13, сущность обычно состоит из нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="72423-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="72423-114">Например заказ может моделируется как сущность с использованием идентификатора и внутренне состоит из набора атрибутов, таких как OrderId OrderDate, OrderItems, и т. д. Однако адрес, который является просто сложное значение, состоящие из страны, улица, Город, т. д. должны быть смоделированы и рассматривается в качестве значения объекта.</span><span class="sxs-lookup"><span data-stu-id="72423-114">For example, Order can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="72423-115">Важные характеристики объектов значение</span><span class="sxs-lookup"><span data-stu-id="72423-115">Important characteristics of value objects</span></span>

<span data-ttu-id="72423-116">Существует два основных характеристик для объектов значение:</span><span class="sxs-lookup"><span data-stu-id="72423-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="72423-117">Они имеют не идентификатор.</span><span class="sxs-lookup"><span data-stu-id="72423-117">They have no identity.</span></span>

-   <span data-ttu-id="72423-118">Они являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="72423-118">They are immutable.</span></span>

<span data-ttu-id="72423-119">Первая характеристика уже обсуждались.</span><span class="sxs-lookup"><span data-stu-id="72423-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="72423-120">Неизменность является важным требованием.</span><span class="sxs-lookup"><span data-stu-id="72423-120">Immutability is an important requirement.</span></span> <span data-ttu-id="72423-121">Значения объекта значения должны быть неизменяемыми после создания объекта.</span><span class="sxs-lookup"><span data-stu-id="72423-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="72423-122">Таким образом при создании объекта необходимо указать необходимые значения, но не должно допускать их можно изменять во время существования объекта.</span><span class="sxs-lookup"><span data-stu-id="72423-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="72423-123">Значение объектов позволяют выполнять некоторые рекомендации для производительности благодаря своей природе неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="72423-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="72423-124">Это особенно важно в системах которых может быть тысячи значение экземпляры объектов, многие из которых имеют одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="72423-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="72423-125">Неизменяемый характера позволяет им для повторного использования; они могут быть взаимозаменяемыми объектами, поскольку их значения совпадают, и они не имеют ни одна учетная запись.</span><span class="sxs-lookup"><span data-stu-id="72423-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="72423-126">Этот тип оптимизации иногда можно провести различие между медленного выполнения и программ с высокой производительностью.</span><span class="sxs-lookup"><span data-stu-id="72423-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="72423-127">Конечно всех этих случаях зависят от среды приложения и контекст развертывания.</span><span class="sxs-lookup"><span data-stu-id="72423-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="72423-128">Реализация объекта значение в C\#</span><span class="sxs-lookup"><span data-stu-id="72423-128">Value object implementation in C\#</span></span>

<span data-ttu-id="72423-129">С точки зрения реализации может иметь значение объекта базовый класс, имеющий основные служебные методы как на основе сравнения между атрибутами (так как объект значения не должен быть основан на удостоверении) и другие основные характеристики равенства.</span><span class="sxs-lookup"><span data-stu-id="72423-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="72423-130">Следующий пример показывает значение объекта базовый класс, используемый в упорядочивания микрослужбу из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="72423-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }
    // Other utilility methods
}
```

<span data-ttu-id="72423-131">Этот класс можно использовать при реализации фактическое значение объекта, как и в объект значения адреса, показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72423-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a><span data-ttu-id="72423-132">Скрытие характеристика идентификаторов при использовании EF ядра для сохранения объектов значение</span><span class="sxs-lookup"><span data-stu-id="72423-132">Hiding the identity characteristic when using EF Core to persist value objects</span></span>

<span data-ttu-id="72423-133">Ограничения при использовании EF ядра, что в текущей версии (EF Core 1.1) нельзя использовать [сложных типов](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) , определенный в EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="72423-133">A limitation when using EF Core is that in its current version (EF Core 1.1) you cannot use [complex types](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) as defined in EF 6.x.</span></span> <span data-ttu-id="72423-134">Таким образом как сущность EF необходимо хранить значение объекта.</span><span class="sxs-lookup"><span data-stu-id="72423-134">Therefore, you must store your value object as an EF entity.</span></span> <span data-ttu-id="72423-135">Тем не менее можно скрыть его идентификатор, станет ясно удостоверение не важно в модели, объект значения.</span><span class="sxs-lookup"><span data-stu-id="72423-135">However, you can hide its ID so you make clear that the identity is not important in the model that the value object is part of.</span></span> <span data-ttu-id="72423-136">Скрыть идентификатор, используя идентификатор как свойство тени.</span><span class="sxs-lookup"><span data-stu-id="72423-136">You hide the ID is by using the ID as a shadow property.</span></span> <span data-ttu-id="72423-137">Поскольку, скрытия идентификатор модели настройки на уровне инфраструктуры, он будет прозрачным для модели домена и его реализации инфраструктуры может измениться в будущем.</span><span class="sxs-lookup"><span data-stu-id="72423-137">Since that configuration for hiding the ID in the model is set up in the infrastructure level, it will be transparent for your domain model, and its infrastructure implementation could change in the future.</span></span>

<span data-ttu-id="72423-138">В eShopOnContainers скрытый идентификатор Затребован EF базовой инфраструктуры реализуется на уровне DbContext следующим образом с помощью плавного API в проект инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="72423-138">In eShopOnContainers, the hidden ID needed by EF Core infrastructure is implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span>

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

<span data-ttu-id="72423-139">Таким образом идентификатор скрыта от домена модели точки зрения, и в будущем, в инфраструктуре значение объекта может также быть реализован как сложный тип или другим способом.</span><span class="sxs-lookup"><span data-stu-id="72423-139">Therefore, the ID is hidden from the domain model point of view, and in the future, the value object infrastructure could also be implemented as a complex type or another way.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72423-140">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72423-140">Additional resources</span></span>

-   <span data-ttu-id="72423-141">**Мартин Фоулер (Martin Fowler). Шаблон ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="72423-141">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="72423-142">**Эрик Эванс (Eric Evans). Проектирование на основе домена: Выполняемой сложность лежит в основе программного обеспечения.**</span><span class="sxs-lookup"><span data-stu-id="72423-142">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="72423-143">(Книга; включает в себя обсуждение значение объектов) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="72423-143">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="72423-144">**Вон Вернон (Vaughn Vernon). Реализация разработки на основе домена.**</span><span class="sxs-lookup"><span data-stu-id="72423-144">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="72423-145">(Книга; включает в себя обсуждение значение объектов) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="72423-145">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="72423-146">**Скрывать свойства**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="72423-146">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="72423-147">**Сложные типы или объектов, значение**.</span><span class="sxs-lookup"><span data-stu-id="72423-147">**Complex types and/or value objects**.</span></span> <span data-ttu-id="72423-148">Обсуждение в репозитории EF Core GitHub (вкладка «проблемы») [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="72423-148">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="72423-149">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="72423-149">**ValueObject.cs.**</span></span> <span data-ttu-id="72423-150">Базовое значение класса объекта в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="72423-150">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="72423-151">*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/SeedWork/ValueObject.cs*</span><span class="sxs-lookup"><span data-stu-id="72423-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="72423-152">**Адрес класса.**</span><span class="sxs-lookup"><span data-stu-id="72423-152">**Address class.**</span></span> <span data-ttu-id="72423-153">Пример класса значения объекта в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="72423-153">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="72423-154">*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/AggregatesModel/OrderAggregate/Address.cs*</span><span class="sxs-lookup"><span data-stu-id="72423-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
<span data-ttu-id="72423-155">[Предыдущие] (seedwork-domain-model-base-classes-interfaces.md) [Далее] (перечисление классы over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="72423-155">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
