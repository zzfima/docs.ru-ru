---
title: Реализация объектов значений
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Реализация объектов значений
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: 4ba2e48e742e580a1c96743fa89e413c488b8dc7
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106727"
---
# <a name="implementing-value-objects"></a><span data-ttu-id="c5142-103">Реализация объектов значений</span><span class="sxs-lookup"><span data-stu-id="c5142-103">Implementing value objects</span></span>

<span data-ttu-id="c5142-104">Как отмечалось в предыдущих разделах о сущностях и статистических выражениях, удостоверение — это базовый компонент сущностей.</span><span class="sxs-lookup"><span data-stu-id="c5142-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="c5142-105">Тем не менее в системе существует множество объектов и элементов данных, не требующих удостоверений и их отслеживания, такие как объекты значений.</span><span class="sxs-lookup"><span data-stu-id="c5142-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="c5142-106">Объект значения может ссылаться на другие сущности.</span><span class="sxs-lookup"><span data-stu-id="c5142-106">A value object can reference other entities.</span></span> <span data-ttu-id="c5142-107">Например, в приложении, которое создает маршрут, содержащий сведения о том, как добраться из одной точки в другую, этот маршрут будет являться объектом значения.</span><span class="sxs-lookup"><span data-stu-id="c5142-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="c5142-108">Это может быть набор точек конкретного маршрута, но такой маршрут не будет иметь удостоверения, несмотря на то, что внутренне он может ссылаться на сущности, такие как город, трасса и т. д.</span><span class="sxs-lookup"><span data-stu-id="c5142-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="c5142-109">На рисунке 9-13 изображен объект значения Address (адрес) в статистическом выражении Order (заказ).</span><span class="sxs-lookup"><span data-stu-id="c5142-109">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="c5142-110">**Рисунок 9-13**.</span><span class="sxs-lookup"><span data-stu-id="c5142-110">**Figure 9-13**.</span></span> <span data-ttu-id="c5142-111">Объект значения Address (адрес) в статистическом выражении Order (заказ)</span><span class="sxs-lookup"><span data-stu-id="c5142-111">Address value object within the Order aggregate</span></span>

<span data-ttu-id="c5142-112">Как показано на рисунке 9-13, сущность обычно состоит из нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c5142-112">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="c5142-113">Например, сущность `Order` можно смоделировать как сущность с удостоверением и внутренне состоящей из набора свойств, таких как OrderId, OrderDate, OrderItems и т. д. Но адрес, который является просто сложным значением, состоящим из страны, улица, города и т. д. и не имеющим удостоверения в этом домене, необходимо моделировать и рассматривать как объект значения.</span><span class="sxs-lookup"><span data-stu-id="c5142-113">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. and has no identity in this domain,  must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="c5142-114">Важные характеристики объектов значений</span><span class="sxs-lookup"><span data-stu-id="c5142-114">Important characteristics of value objects</span></span>

<span data-ttu-id="c5142-115">У объектов значений две основные характеристики:</span><span class="sxs-lookup"><span data-stu-id="c5142-115">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="c5142-116">У них нет удостоверения.</span><span class="sxs-lookup"><span data-stu-id="c5142-116">They have no identity.</span></span>

-   <span data-ttu-id="c5142-117">Они неизменяемы.</span><span class="sxs-lookup"><span data-stu-id="c5142-117">They are immutable.</span></span>

<span data-ttu-id="c5142-118">Первая характеристика уже обсуждались.</span><span class="sxs-lookup"><span data-stu-id="c5142-118">The first characteristic was already discussed.</span></span> <span data-ttu-id="c5142-119">Неизменяемость является важным требованием.</span><span class="sxs-lookup"><span data-stu-id="c5142-119">Immutability is an important requirement.</span></span> <span data-ttu-id="c5142-120">После создания объекта значения он должен оставаться неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="c5142-120">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="c5142-121">Таким образом, при создании объекта необходимо задать необходимые значения, и они не должны изменяться в течение всего времени существования объекта.</span><span class="sxs-lookup"><span data-stu-id="c5142-121">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="c5142-122">Благодаря своей неизменяемости объекты значений позволяют применять некоторые приемы для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="c5142-122">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="c5142-123">Это особенно справедливо для систем, содержащих тысячи экземпляров объектов значений, многие из которых имеют одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="c5142-123">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="c5142-124">Неизменяемость позволяет использовать их повторно, они могут быть взаимозаменяемыми объектами, поскольку их значения совпадают и они не имеют удостоверений.</span><span class="sxs-lookup"><span data-stu-id="c5142-124">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="c5142-125">Такая оптимизация иногда может провести грань между медленным приложением и приложением с высокой производительностью.</span><span class="sxs-lookup"><span data-stu-id="c5142-125">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="c5142-126">Конечно, все это зависит от среды приложения и контекста развертывания.</span><span class="sxs-lookup"><span data-stu-id="c5142-126">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="c5142-127">Реализация объекта значения в C\#</span><span class="sxs-lookup"><span data-stu-id="c5142-127">Value object implementation in C\#</span></span>

<span data-ttu-id="c5142-128">С точки зрения реализации можно создать базовый класс объекта значения, имеющий основные служебные методы, такие как сравнение, основанное на сравнении всех атрибутов (поскольку объект значения не должен задаваться удостоверением) и других основных характеристик.</span><span class="sxs-lookup"><span data-stu-id="c5142-128">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="c5142-129">Следующий пример показывает создание базового класса объекта значения, используемого в микрослужбе заказов из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c5142-129">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

    public override int GetHashCode()
    {
        return GetAtomicValues()
         .Select(x => x != null ? x.GetHashCode() : 0)
         .Aggregate((x, y) => x ^ y);
    }        
    // Other utilility methods
}
```

<span data-ttu-id="c5142-130">Этот класс можно использовать при реализации реального объекта значения, как это показано на примере объекта значения Address в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="c5142-130">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; }
    public String City { get; }
    public String State { get; }
    public String Country { get; }
    public String ZipCode { get; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="c5142-131">Хранение объектов значений в базе данных в EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5142-131">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="c5142-132">Мы узнали, как определить объект значения в модели домена.</span><span class="sxs-lookup"><span data-stu-id="c5142-132">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="c5142-133">Но как же сохранить его в базе данных через Entity Framework (EF) Core, который обычно обращается к сущностям по удостоверению?</span><span class="sxs-lookup"><span data-stu-id="c5142-133">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="c5142-134">Общие сведения и устаревший подход с использованием EF Core 1.1</span><span class="sxs-lookup"><span data-stu-id="c5142-134">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="c5142-135">Для справки: при использовании EF Core 1.0 и 1.1 было невозможно использовать [сложные типы](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute), как они назывались в EF 6.x в традиционном .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5142-135">As background, a limitation when using EF Core 1.0 and 1.1 was that you cannot use  [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="c5142-136">Таким образом, при использовании EF Core 1.0 и 1.1 необходимо хранить объект значения в виде сущности EF с полем ID.</span><span class="sxs-lookup"><span data-stu-id="c5142-136">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="c5142-137">Затем, чтобы сущность больше походила на объект значения, нужно скрыть поле ID, дав понять таким образом, что удостоверение объекта значения не важно в данной модели домена.</span><span class="sxs-lookup"><span data-stu-id="c5142-137">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="c5142-138">Можно скрыть поле ID при помощи [затемнения свойства](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span><span class="sxs-lookup"><span data-stu-id="c5142-138">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="c5142-139">Так как такой вариант скрытия удостоверения в модели задается на уровне инфраструктуры EF, это будет в каком-то смысле прозрачно для модели домена.</span><span class="sxs-lookup"><span data-stu-id="c5142-139">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="c5142-140">В первоначальной версии eShopOnContainers (.NET Core 1.1) скрытие поля ID, необходимое для инфраструктуры EF Core, было реализовано на уровне DbContext при помощи текучего API в инфраструктуре проекта следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c5142-140">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="c5142-141">Таким образом, удостоверение было скрыто с точки зрения модели домена, но все еще присутствует в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="c5142-141">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration) 
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA); 

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

<span data-ttu-id="c5142-142">Тем не менее сохраняемость этого объекта значения в базе данных обеспечивалась так же, как и обычной сущности в любой другой таблице.</span><span class="sxs-lookup"><span data-stu-id="c5142-142">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="c5142-143">В EF Core 2.0 появились новые и лучшие способы хранения объектов значений.</span><span class="sxs-lookup"><span data-stu-id="c5142-143">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="c5142-144">Хранение объектов значений в виде принадлежащих типов сущностей в EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5142-144">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="c5142-145">Даже при некоторых преимуществах канонического шаблона объекта значения в предметно-ориентированном проектировании (DDD) перед принадлежащим типом сущности EF Core сейчас это является наилучшим способом хранения объектов значений в EF Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5142-145">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="c5142-146">Существующие ограничения приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c5142-146">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="c5142-147">Возможность использования принадлежащих типов сущностей была добавлена в EF Core начиная с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5142-147">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="c5142-148">Принадлежащий тип сущности позволяет сопоставить типы, которые не имеют своего удостоверения, определены явным образом в модели домена и используются в качестве свойств, таких как объект значения, в любой сущности.</span><span class="sxs-lookup"><span data-stu-id="c5142-148">An owned entity type allows you to map types that do not have their own identity explicitely defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="c5142-149">Принадлежащий тип сущности предоставляет другому типу сущности тот же тип среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c5142-149">An owned entity type shares the same CLR type with another entity type.</span></span> <span data-ttu-id="c5142-150">Сущность, содержащая определяющую навигацию, является сущностью-владельцем.</span><span class="sxs-lookup"><span data-stu-id="c5142-150">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="c5142-151">При запросе владельца по умолчанию включаются принадлежащие типы.</span><span class="sxs-lookup"><span data-stu-id="c5142-151">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="c5142-152">При взгляде на модель домена принадлежащий тип выглядит так, как будто он не имеет удостоверения.</span><span class="sxs-lookup"><span data-stu-id="c5142-152">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span>
<span data-ttu-id="c5142-153">На самом деле принадлежащие типы имеют удостоверения, но свойство навигации владельца является частью этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="c5142-153">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="c5142-154">Удостоверение экземпляров принадлежащих типов не является полностью их собственным.</span><span class="sxs-lookup"><span data-stu-id="c5142-154">The identity of instances of own types is not completely their own.</span></span> <span data-ttu-id="c5142-155">Оно состоит из трех компонентов:</span><span class="sxs-lookup"><span data-stu-id="c5142-155">It consists of three components:</span></span>

- <span data-ttu-id="c5142-156">Удостоверение владельца</span><span class="sxs-lookup"><span data-stu-id="c5142-156">The identity of the owner</span></span>

- <span data-ttu-id="c5142-157">Указывающее на него свойство навигации</span><span class="sxs-lookup"><span data-stu-id="c5142-157">The navigation property pointing to them</span></span>

- <span data-ttu-id="c5142-158">В случае с коллекциями принадлежащих типов — независимый компонент (пока не поддерживается в EF Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="c5142-158">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0).</span></span>

<span data-ttu-id="c5142-159">Например, в модели домена Ordering в eShopOnContainers объект значения Address, являющийся частью сущности Order, реализован как принадлежащий тип сущности в рамках сущности-владельца, которой является сущность Order.</span><span class="sxs-lookup"><span data-stu-id="c5142-159">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="c5142-160">Адрес — это тип, не имеющий определенного в модели домена свойства-удостоверения.</span><span class="sxs-lookup"><span data-stu-id="c5142-160">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="c5142-161">Он используется как свойство сущности Order для указания адреса доставки конкретного заказа.</span><span class="sxs-lookup"><span data-stu-id="c5142-161">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="c5142-162">По соглашению для принадлежащего типа создается теневой первичный ключ, и этот тип сопоставляется с той же таблицей, что и владелец, с помощью разбиения таблицы.</span><span class="sxs-lookup"><span data-stu-id="c5142-162">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="c5142-163">Это позволяет использовать принадлежащие типы аналогично сложным типам в EF6 в традиционном .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5142-163">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="c5142-164">Важно отметить, что по соглашению принадлежащие типы никогда не обнаруживаются EF Core, поэтому их необходимо объявлять явно.</span><span class="sxs-lookup"><span data-stu-id="c5142-164">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="c5142-165">В eShopOnContainers, в файле OrderingContext.cs, в методе OnModelCreating() применяется несколько конфигураций инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="c5142-165">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="c5142-166">Одна из них относится к сущности Order.</span><span class="sxs-lookup"><span data-stu-id="c5142-166">One of them is related to the Order entity.</span></span>

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
// 
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

<span data-ttu-id="c5142-167">В следующем коде инфраструктура сохраняемости определяется для сущности Order:</span><span class="sxs-lookup"><span data-stu-id="c5142-167">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

```csharp
// Part of the OrderEntityTypeConfiguration.cs class 
// 
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();
    
    //...Additional validations, constraints and code...
    //...
}
```

<span data-ttu-id="c5142-168">В приведенном выше коде метод `orderConfiguration.OwnsOne(o => o.Address)` указывает, что свойство `Address` принадлежит сущности типа `Order`.</span><span class="sxs-lookup"><span data-stu-id="c5142-168">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="c5142-169">По умолчанию соглашения EF Core именуют столбцы базы данных для свойств принадлежащего типа сущностей следующим образом: `EntityProperty_OwnedEntityProperty`.</span><span class="sxs-lookup"><span data-stu-id="c5142-169">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="c5142-170">Следовательно, внутренние свойства типа `Address` будут отображаться в таблице `Orders` с именами `Address_Street`, `Address_City` (и так далее для свойств `State`, `Country` и `ZipCode`).</span><span class="sxs-lookup"><span data-stu-id="c5142-170">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="c5142-171">Можно переименовать эти столбцы, добавив текучий метод `Property().HasColumnName()`.</span><span class="sxs-lookup"><span data-stu-id="c5142-171">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="c5142-172">В случае, когда свойство `Address` является общедоступным свойством, сопоставление будет выполняться подобным образом:</span><span class="sxs-lookup"><span data-stu-id="c5142-172">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="c5142-173">Метод `OwnsOne` возможно объединять в цепочку для текучего сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c5142-173">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="c5142-174">В следующем гипотетическом примере сущность `OrderDetails` владеет `BillingAddress` и `ShippingAddress`, которые принадлежат к типу `Address`.</span><span class="sxs-lookup"><span data-stu-id="c5142-174">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="c5142-175">А `OrderDetails`, в свою очередь, принадлежит типу `Order`.</span><span class="sxs-lookup"><span data-stu-id="c5142-175">Then `OrderDetails` is owned by the `Order` type.</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="c5142-176">Дополнительные сведения о принадлежащих типах сущностей</span><span class="sxs-lookup"><span data-stu-id="c5142-176">Additional details on owned entity types</span></span>

<span data-ttu-id="c5142-177">• Принадлежащие типы определяются при настройке свойства навигации конкретного типа при помощи текучего API OwnsOne.</span><span class="sxs-lookup"><span data-stu-id="c5142-177">•   Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

<span data-ttu-id="c5142-178">• Определение принадлежащего типа в нашей модели метаданных состоит из следующих элементов: тип владельца, свойство навигации и тип среды CLR принадлежащего типа.</span><span class="sxs-lookup"><span data-stu-id="c5142-178">•   The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

<span data-ttu-id="c5142-179">• Удостоверение (ключ) экземпляра принадлежащего типа в нашем стеке состоит из удостоверения владельца и определения принадлежащего типа.</span><span class="sxs-lookup"><span data-stu-id="c5142-179">•   The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="c5142-180">Возможности принадлежащих сущностей:</span><span class="sxs-lookup"><span data-stu-id="c5142-180">Owned entities capabilities:</span></span>

<span data-ttu-id="c5142-181">• Принадлежащий тип может ссылаться на другие сущности, как принадлежащие (вложенные принадлежащие типы), так и не принадлежащие (обычные ссылки свойств навигации на другие сущности).</span><span class="sxs-lookup"><span data-stu-id="c5142-181">•   Owned type can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

<span data-ttu-id="c5142-182">• Можно сопоставлять одной сущности-владельцу одни и те же типы среды CLR как разные принадлежащие типы при помощи различных свойств навигации.</span><span class="sxs-lookup"><span data-stu-id="c5142-182">•   You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

<span data-ttu-id="c5142-183">• По соглашению выполняется разделение таблицы, однако можно отказаться от этого и сопоставить принадлежащий тип в другую таблицу, используя метод ToTable.</span><span class="sxs-lookup"><span data-stu-id="c5142-183">•   Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

<span data-ttu-id="c5142-184">• Безотложная загрузка для принадлежащих типов выполняется автоматически, т. е. нет необходимости вызывать метод Include() в запросе.</span><span class="sxs-lookup"><span data-stu-id="c5142-184">•   Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="c5142-185">Ограничения принадлежащих сущностей:</span><span class="sxs-lookup"><span data-stu-id="c5142-185">Owned entities limitations:</span></span>

<span data-ttu-id="c5142-186">• Нельзя создать коллекцию DbSet<T> из принадлежащих типов (изначально не предусмотрено).</span><span class="sxs-lookup"><span data-stu-id="c5142-186">•   You cannot create a DbSet<T> of an owned type (by design).</span></span>

<span data-ttu-id="c5142-187">• Невозможно вызвать метод ModelBuilder.Entity<T>() в принадлежащих типах (в настоящее время не предусмотрено).</span><span class="sxs-lookup"><span data-stu-id="c5142-187">•   You cannot call ModelBuilder.Entity<T>() on owned types (currently by design).</span></span>

<span data-ttu-id="c5142-188">• Пока не предусмотрено коллекций принадлежащих типов (они появятся в версиях после EF Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="c5142-188">•   No collections of owned types yet (but they will be supported in versions after EF Core 2.0).</span></span>

<span data-ttu-id="c5142-189">• Не поддерживается их настройка через атрибуты.</span><span class="sxs-lookup"><span data-stu-id="c5142-189">•   No support for configuring them via an attribute.</span></span>

<span data-ttu-id="c5142-190">• Не поддерживаются необязательные (т. е. допускающие значение NULL) принадлежащие типы, которые сопоставляются с владельцем в одной таблице (т. е. с помощью разделения таблицы).</span><span class="sxs-lookup"><span data-stu-id="c5142-190">•   No support for optional (i.e. nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="c5142-191">Это так, поскольку для значения null не существует граничной метки.</span><span class="sxs-lookup"><span data-stu-id="c5142-191">This is because we don't have a separate sentinel for the null.</span></span>

<span data-ttu-id="c5142-192">• Не поддерживается наследование сопоставления для принадлежащих типов, но мы можем сопоставить два конечных типа одной иерархии наследования как два различных принадлежащих типа.</span><span class="sxs-lookup"><span data-stu-id="c5142-192">•   No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="c5142-193">EF Core не будет учитывать тот факт, что они являются частью одной иерархии.</span><span class="sxs-lookup"><span data-stu-id="c5142-193">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="c5142-194">Основные отличия от сложных типов EF6</span><span class="sxs-lookup"><span data-stu-id="c5142-194">Main differences with EF6's complex types</span></span>

<span data-ttu-id="c5142-195">• Разделение таблицы является необязательным, т. е. они также могут быть сопоставлены с отдельной таблицей и по-прежнему быть принадлежащими типами.</span><span class="sxs-lookup"><span data-stu-id="c5142-195">•   Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

<span data-ttu-id="c5142-196">• Они могут ссылаться на другие сущности (т. е. они могут выступать зависимой стороной в отношениях с другими не принадлежащими типами).</span><span class="sxs-lookup"><span data-stu-id="c5142-196">•   They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="c5142-197">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="c5142-197">Additional resources</span></span>

-   <span data-ttu-id="c5142-198">**Мартин Фоулер (Martin Fowler). Шаблон ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="c5142-198">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="c5142-199">**Эрик Эванс (Eric Evans). Предметно-ориентированное проектирование (DDD). Структуризация сложных программных систем.**</span><span class="sxs-lookup"><span data-stu-id="c5142-199">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="c5142-200">(Книга, в которой рассматриваются объекты значений) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="c5142-200">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="c5142-201">**Вон Вернон (Vaughn Vernon). Реализация проблемно-ориентированного проектирования (DDD).**</span><span class="sxs-lookup"><span data-stu-id="c5142-201">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="c5142-202">(Книга, в которой рассматриваются объекты значений) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="c5142-202">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="c5142-203">**Свойства тени**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="c5142-203">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="c5142-204">**Сложные типы и (или) объекты значений**.</span><span class="sxs-lookup"><span data-stu-id="c5142-204">**Complex types and/or value objects**.</span></span> <span data-ttu-id="c5142-205">Обсуждение EF Core в репозитории сервиса GitHub (вкладка "Issues" (Вопросы)) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="c5142-205">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="c5142-206">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="c5142-206">**ValueObject.cs.**</span></span> <span data-ttu-id="c5142-207">Базовый класс объекта значений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c5142-207">Base value object class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="c5142-208">**Класс Address.**</span><span class="sxs-lookup"><span data-stu-id="c5142-208">**Address class.**</span></span> <span data-ttu-id="c5142-209">Пример класса объекта значений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="c5142-209">Sample value object class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)



>[!div class="step-by-step"]
<span data-ttu-id="c5142-210">[Назад](seedwork-domain-model-base-classes-interfaces.md)
[Вперед](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="c5142-210">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
