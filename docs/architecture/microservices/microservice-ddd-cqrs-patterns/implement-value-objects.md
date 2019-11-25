---
title: Реализация объектов значений
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Знакомство с возможностями и параметрами для реализации объектов значений с использованием новых функций Entity Framework.
ms.date: 10/08/2018
ms.openlocfilehash: 2608517c4006f5e8da1d31b2c337d8ddd3ddd542
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739871"
---
# <a name="implement-value-objects"></a><span data-ttu-id="294b7-103">Реализация объектов значений</span><span class="sxs-lookup"><span data-stu-id="294b7-103">Implement value objects</span></span>

<span data-ttu-id="294b7-104">Как отмечалось в предыдущих разделах о сущностях и статистических выражениях, удостоверение — это базовый компонент сущностей.</span><span class="sxs-lookup"><span data-stu-id="294b7-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="294b7-105">Тем не менее в системе существует множество объектов и элементов данных, не требующих удостоверений и их отслеживания, такие как объекты значений.</span><span class="sxs-lookup"><span data-stu-id="294b7-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="294b7-106">Объект значения может ссылаться на другие сущности.</span><span class="sxs-lookup"><span data-stu-id="294b7-106">A value object can reference other entities.</span></span> <span data-ttu-id="294b7-107">Например, в приложении, которое создает маршрут, содержащий сведения о том, как добраться из одной точки в другую, этот маршрут будет являться объектом значения.</span><span class="sxs-lookup"><span data-stu-id="294b7-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="294b7-108">Это может быть набор точек конкретного маршрута, но такой маршрут не будет иметь удостоверения, несмотря на то, что внутренне он может ссылаться на сущности, такие как город, трасса и т. д.</span><span class="sxs-lookup"><span data-stu-id="294b7-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="294b7-109">На рисунке 7-13 изображен объект значения Address (адрес) в статистическом выражении Order (заказ).</span><span class="sxs-lookup"><span data-stu-id="294b7-109">Figure 7-13 shows the Address value object within the Order aggregate.</span></span>

![Схема, на которой показан объект значения Address (Адрес) в агрегате Order (Заказ).](./media/implement-value-objects/value-object-within-aggregate.png)

<span data-ttu-id="294b7-111">**Рис. 7-13**.</span><span class="sxs-lookup"><span data-stu-id="294b7-111">**Figure 7-13**.</span></span> <span data-ttu-id="294b7-112">Объект значения Address (адрес) в статистическом выражении Order (заказ)</span><span class="sxs-lookup"><span data-stu-id="294b7-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="294b7-113">Как показано на рисунке 7-13, сущность обычно состоит из нескольких атрибутов.</span><span class="sxs-lookup"><span data-stu-id="294b7-113">As shown in Figure 7-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="294b7-114">Например, сущность `Order` можно смоделировать как сущность с удостоверением и внутренне состоящей из набора свойств, таких как OrderId, OrderDate, OrderItems и т. д. Но адрес, который является просто сложным значением, состоящим из страны или региона, улицы, города и т. д. и не имеющим удостоверения в этом домене, необходимо моделировать и рассматривать как объект значения.</span><span class="sxs-lookup"><span data-stu-id="294b7-114">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex-value composed of country/region, street, city, etc. and has no identity in this domain, must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="294b7-115">Важные характеристики объектов значений</span><span class="sxs-lookup"><span data-stu-id="294b7-115">Important characteristics of value objects</span></span>

<span data-ttu-id="294b7-116">У объектов значений две основные характеристики:</span><span class="sxs-lookup"><span data-stu-id="294b7-116">There are two main characteristics for value objects:</span></span>

- <span data-ttu-id="294b7-117">У них нет удостоверения.</span><span class="sxs-lookup"><span data-stu-id="294b7-117">They have no identity.</span></span>

- <span data-ttu-id="294b7-118">Они неизменяемы.</span><span class="sxs-lookup"><span data-stu-id="294b7-118">They are immutable.</span></span>

<span data-ttu-id="294b7-119">Первая характеристика уже обсуждались.</span><span class="sxs-lookup"><span data-stu-id="294b7-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="294b7-120">Неизменяемость является важным требованием.</span><span class="sxs-lookup"><span data-stu-id="294b7-120">Immutability is an important requirement.</span></span> <span data-ttu-id="294b7-121">После создания объекта значения он должен оставаться неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="294b7-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="294b7-122">Таким образом, при создании объекта необходимо задать необходимые значения, и они не должны изменяться в течение всего времени существования объекта.</span><span class="sxs-lookup"><span data-stu-id="294b7-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="294b7-123">Благодаря своей неизменяемости объекты значений позволяют применять некоторые приемы для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="294b7-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="294b7-124">Это особенно справедливо для систем, содержащих тысячи экземпляров объектов значений, многие из которых имеют одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="294b7-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="294b7-125">Неизменяемость позволяет использовать их повторно, они могут быть взаимозаменяемыми объектами, поскольку их значения совпадают и они не имеют удостоверений.</span><span class="sxs-lookup"><span data-stu-id="294b7-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="294b7-126">Такая оптимизация иногда может провести грань между медленным приложением и приложением с высокой производительностью.</span><span class="sxs-lookup"><span data-stu-id="294b7-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="294b7-127">Конечно, все это зависит от среды приложения и контекста развертывания.</span><span class="sxs-lookup"><span data-stu-id="294b7-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="294b7-128">Реализация объекта значения в C\#</span><span class="sxs-lookup"><span data-stu-id="294b7-128">Value object implementation in C\#</span></span>

<span data-ttu-id="294b7-129">С точки зрения реализации можно создать базовый класс объекта значения, имеющий основные служебные методы, такие как сравнение, основанное на сравнении всех атрибутов (поскольку объект значения не должен задаваться удостоверением) и других основных характеристик.</span><span class="sxs-lookup"><span data-stu-id="294b7-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="294b7-130">Следующий пример показывает создание базового класса объекта значения, используемого в микрослужбе заказов из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="294b7-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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
    // Other utility methods
}
```

<span data-ttu-id="294b7-131">Этот класс можно использовать при реализации реального объекта значения, как это показано на примере объекта значения Address в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="294b7-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

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

<span data-ttu-id="294b7-132">Вы можете видеть, что у этой реализации объекта значения для Address нет удостоверения, а следовательно, и поля ID, ни в классе Address, ни даже в классе ValueObject.</span><span class="sxs-lookup"><span data-stu-id="294b7-132">You can see how this value object implementation of Address has no identity and therefore, no ID field, neither at the Address class not even at the ValueObject class.</span></span>

<span data-ttu-id="294b7-133">Отсутствие поля ID в классе, используемом Entity Framework, было недопустимым до выпуска EF Core 2.0. Эта возможность помогает реализовывать более эффективные объекты значений без ID.</span><span class="sxs-lookup"><span data-stu-id="294b7-133">Having no ID field in a class to be used by Entity Framework was not possible until EF Core 2.0, which greatly helps to implement better value objects with no ID.</span></span> <span data-ttu-id="294b7-134">Именно это пояснение используется в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="294b7-134">That is precisely the explanation of the next section.</span></span>

<span data-ttu-id="294b7-135">Можно возразить, что объекты значений, являясь неизменяемыми, должны быть доступны только для чтения (например, свойства, отвечающие только за получение), и это действительно так.</span><span class="sxs-lookup"><span data-stu-id="294b7-135">It could be argued that value objects, being immutable, should be read-only (i.e. get-only properties), and that’s indeed true.</span></span> <span data-ttu-id="294b7-136">Однако объекты значений обычно сериализируются и десериализируются для прохождения очередей сообщений, а наличие доступа только для чтения не позволяет десериализатору назначать значения, поэтому мы просто оставляем их в виде частного набора, доступного только для чтения, чего хватает для практического применения.</span><span class="sxs-lookup"><span data-stu-id="294b7-136">However, value objects are usually serialized and deserialized to go through message queues, and being read-only stops the deserializer from assigning values, so we just leave them as private set which is read-only enough to be practical.</span></span>

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="294b7-137">Хранение объектов значений в базе данных в EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="294b7-137">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="294b7-138">Мы узнали, как определить объект значения в модели домена.</span><span class="sxs-lookup"><span data-stu-id="294b7-138">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="294b7-139">Но как же сохранить его в базе данных через Entity Framework (EF) Core, который обычно обращается к сущностям по удостоверению?</span><span class="sxs-lookup"><span data-stu-id="294b7-139">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="294b7-140">Общие сведения и устаревший подход с использованием EF Core 1.1</span><span class="sxs-lookup"><span data-stu-id="294b7-140">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="294b7-141">Для справки: при использовании EF Core 1.0 и 1.1 было невозможно использовать [сложные типы](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) в том виде, в котором они были определены в EF 6.x в традиционном решении .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="294b7-141">As background, a limitation when using EF Core 1.0 and 1.1 was that you could not use [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="294b7-142">Таким образом, при использовании EF Core 1.0 и 1.1 необходимо хранить объект значения в виде сущности EF с полем ID.</span><span class="sxs-lookup"><span data-stu-id="294b7-142">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="294b7-143">Затем, чтобы сущность больше походила на объект значения, нужно скрыть поле ID, дав понять таким образом, что удостоверение объекта значения не важно в данной модели домена.</span><span class="sxs-lookup"><span data-stu-id="294b7-143">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="294b7-144">Можно скрыть поле ID при помощи [затемнения свойства](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span><span class="sxs-lookup"><span data-stu-id="294b7-144">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="294b7-145">Так как такой вариант скрытия удостоверения в модели задается на уровне инфраструктуры EF, это будет в каком-то смысле прозрачно для модели домена.</span><span class="sxs-lookup"><span data-stu-id="294b7-145">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="294b7-146">В первоначальной версии eShopOnContainers (.NET Core 1.1) скрытие поля ID, необходимое для инфраструктуры EF Core, было реализовано на уровне DbContext при помощи текучего API в инфраструктуре проекта следующим образом.</span><span class="sxs-lookup"><span data-stu-id="294b7-146">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="294b7-147">Таким образом, удостоверение было скрыто с точки зрения модели домена, но все еще присутствует в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="294b7-147">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

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

<span data-ttu-id="294b7-148">Тем не менее сохраняемость этого объекта значения в базе данных обеспечивалась так же, как и обычной сущности в любой другой таблице.</span><span class="sxs-lookup"><span data-stu-id="294b7-148">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="294b7-149">В EF Core 2.0 появились новые и лучшие способы хранения объектов значений.</span><span class="sxs-lookup"><span data-stu-id="294b7-149">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="294b7-150">Хранение объектов значений в виде принадлежащих типов сущностей в EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="294b7-150">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="294b7-151">Даже при некоторых преимуществах канонического шаблона объекта значения в предметно-ориентированном проектировании (DDD) перед принадлежащим типом сущности EF Core сейчас это является наилучшим способом хранения объектов значений в EF Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="294b7-151">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="294b7-152">Существующие ограничения приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="294b7-152">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="294b7-153">Возможность использования принадлежащих типов сущностей была добавлена в EF Core начиная с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="294b7-153">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="294b7-154">Принадлежащий тип сущности позволяет сопоставить типы, которые не имеют своего удостоверения, определены явным образом в модели домена и используются в качестве свойств, таких как объект значения, в любой сущности.</span><span class="sxs-lookup"><span data-stu-id="294b7-154">An owned entity type allows you to map types that do not have their own identity explicitly defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="294b7-155">Принадлежащий тип сущности предоставляет другому типу сущности тот же тип среды CLR (в данном случае это просто обычный класс).</span><span class="sxs-lookup"><span data-stu-id="294b7-155">An owned entity type shares the same CLR type with another entity type (that is, it’s just a regular class).</span></span> <span data-ttu-id="294b7-156">Сущность, содержащая определяющую навигацию, является сущностью-владельцем.</span><span class="sxs-lookup"><span data-stu-id="294b7-156">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="294b7-157">При запросе владельца по умолчанию включаются принадлежащие типы.</span><span class="sxs-lookup"><span data-stu-id="294b7-157">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="294b7-158">При взгляде на модель домена принадлежащий тип выглядит так, как будто он не имеет удостоверения.</span><span class="sxs-lookup"><span data-stu-id="294b7-158">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span> <span data-ttu-id="294b7-159">На самом деле принадлежащие типы имеют удостоверения, но свойство навигации владельца является частью этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="294b7-159">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="294b7-160">Удостоверение экземпляров принадлежащих типов не является полностью их собственным.</span><span class="sxs-lookup"><span data-stu-id="294b7-160">The identity of instances of owned types is not completely their own.</span></span> <span data-ttu-id="294b7-161">Оно состоит из трех компонентов:</span><span class="sxs-lookup"><span data-stu-id="294b7-161">It consists of three components:</span></span>

- <span data-ttu-id="294b7-162">Удостоверение владельца</span><span class="sxs-lookup"><span data-stu-id="294b7-162">The identity of the owner</span></span>

- <span data-ttu-id="294b7-163">Указывающее на него свойство навигации</span><span class="sxs-lookup"><span data-stu-id="294b7-163">The navigation property pointing to them</span></span>

- <span data-ttu-id="294b7-164">В случае с коллекциями принадлежащих типов — независимый компонент (пока не поддерживается в EF Core 2.0, ожидается в версии 2.2).</span><span class="sxs-lookup"><span data-stu-id="294b7-164">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0, coming up on 2.2).</span></span>

<span data-ttu-id="294b7-165">Например, в модели домена Ordering в eShopOnContainers объект значения Address, являющийся частью сущности Order, реализован как принадлежащий тип сущности в рамках сущности-владельца, которой является сущность Order.</span><span class="sxs-lookup"><span data-stu-id="294b7-165">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="294b7-166">Адрес — это тип, не имеющий определенного в модели домена свойства-удостоверения.</span><span class="sxs-lookup"><span data-stu-id="294b7-166">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="294b7-167">Он используется как свойство сущности Order для указания адреса доставки конкретного заказа.</span><span class="sxs-lookup"><span data-stu-id="294b7-167">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="294b7-168">По соглашению для принадлежащего типа создается теневой первичный ключ, и этот тип сопоставляется с той же таблицей, что и владелец, с помощью разбиения таблицы.</span><span class="sxs-lookup"><span data-stu-id="294b7-168">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="294b7-169">Это позволяет использовать принадлежащие типы аналогично сложным типам в EF6 в традиционном .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="294b7-169">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="294b7-170">Важно отметить, что по соглашению принадлежащие типы никогда не обнаруживаются EF Core, поэтому их необходимо объявлять явно.</span><span class="sxs-lookup"><span data-stu-id="294b7-170">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="294b7-171">В eShopOnContainers, в файле OrderingContext.cs, в методе OnModelCreating() применяется несколько конфигураций инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="294b7-171">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="294b7-172">Одна из них относится к сущности Order.</span><span class="sxs-lookup"><span data-stu-id="294b7-172">One of them is related to the Order entity.</span></span>

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

<span data-ttu-id="294b7-173">В следующем коде инфраструктура сохраняемости определяется для сущности Order:</span><span class="sxs-lookup"><span data-stu-id="294b7-173">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

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

<span data-ttu-id="294b7-174">В приведенном выше коде метод `orderConfiguration.OwnsOne(o => o.Address)` указывает, что свойство `Address` принадлежит сущности типа `Order`.</span><span class="sxs-lookup"><span data-stu-id="294b7-174">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="294b7-175">По умолчанию соглашения EF Core именуют столбцы базы данных для свойств принадлежащего типа сущностей следующим образом: `EntityProperty_OwnedEntityProperty`.</span><span class="sxs-lookup"><span data-stu-id="294b7-175">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="294b7-176">Следовательно, внутренние свойства типа `Address` будут отображаться в таблице `Orders` с именами `Address_Street`, `Address_City` (и так далее для свойств `State`, `Country` и `ZipCode`).</span><span class="sxs-lookup"><span data-stu-id="294b7-176">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="294b7-177">Можно переименовать эти столбцы, добавив текучий метод `Property().HasColumnName()`.</span><span class="sxs-lookup"><span data-stu-id="294b7-177">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="294b7-178">В случае, когда свойство `Address` является общедоступным свойством, сопоставление будет выполняться подобным образом:</span><span class="sxs-lookup"><span data-stu-id="294b7-178">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="294b7-179">Метод `OwnsOne` возможно объединять в цепочку для текучего сопоставления.</span><span class="sxs-lookup"><span data-stu-id="294b7-179">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="294b7-180">В следующем гипотетическом примере сущность `OrderDetails` владеет `BillingAddress` и `ShippingAddress`, которые принадлежат к типу `Address`.</span><span class="sxs-lookup"><span data-stu-id="294b7-180">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="294b7-181">А `OrderDetails`, в свою очередь, принадлежит типу `Order`.</span><span class="sxs-lookup"><span data-stu-id="294b7-181">Then `OrderDetails` is owned by the `Order` type.</span></span>

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

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="294b7-182">Дополнительные сведения о принадлежащих типах сущностей</span><span class="sxs-lookup"><span data-stu-id="294b7-182">Additional details on owned entity types</span></span>

- <span data-ttu-id="294b7-183">Принадлежащие типы определяются при настройке свойства навигации конкретного типа с помощью текучего API OwnsOne.</span><span class="sxs-lookup"><span data-stu-id="294b7-183">Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

- <span data-ttu-id="294b7-184">Определение принадлежащего типа в нашей модели метаданных состоит из следующих элементов: тип владельца, свойство навигации и тип среды CLR принадлежащего типа.</span><span class="sxs-lookup"><span data-stu-id="294b7-184">The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

- <span data-ttu-id="294b7-185">Удостоверение (ключ) экземпляра принадлежащего типа в нашем стеке состоит из удостоверения владельца и определения принадлежащего типа.</span><span class="sxs-lookup"><span data-stu-id="294b7-185">The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="294b7-186">Возможности принадлежащих сущностей:</span><span class="sxs-lookup"><span data-stu-id="294b7-186">Owned entities capabilities:</span></span>

- <span data-ttu-id="294b7-187">Принадлежащие типы могут ссылаться на другие сущности, как принадлежащие (вложенные принадлежащие типы), так и не принадлежащие (обычные ссылки свойств навигации на другие сущности).</span><span class="sxs-lookup"><span data-stu-id="294b7-187">Owned types can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

- <span data-ttu-id="294b7-188">Можно сопоставлять одной сущности-владельцу одни и те же типы среды CLR как разные принадлежащие типы с помощью различных свойств навигации.</span><span class="sxs-lookup"><span data-stu-id="294b7-188">You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

- <span data-ttu-id="294b7-189">По соглашению выполняется разделение таблицы, однако можно отказаться от этого и сопоставить принадлежащий тип в другую таблицу, используя метод ToTable.</span><span class="sxs-lookup"><span data-stu-id="294b7-189">Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

- <span data-ttu-id="294b7-190">Безотложная загрузка для принадлежащих типов выполняется автоматически, т. е. нет необходимости вызывать метод Include() в запросе.</span><span class="sxs-lookup"><span data-stu-id="294b7-190">Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

- <span data-ttu-id="294b7-191">Можно настроить с помощью атрибута \[Owned\], как в EF Core 2.1</span><span class="sxs-lookup"><span data-stu-id="294b7-191">Can be configured with attribute \[Owned\], as of EF Core 2.1</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="294b7-192">Ограничения принадлежащих сущностей:</span><span class="sxs-lookup"><span data-stu-id="294b7-192">Owned entities limitations:</span></span>

- <span data-ttu-id="294b7-193">Невозможно создать коллекцию DbSet\<T\> из принадлежащего типа (изначально не предусмотрено).</span><span class="sxs-lookup"><span data-stu-id="294b7-193">You cannot create a DbSet\<T\> of an owned type (by design).</span></span>

- <span data-ttu-id="294b7-194">Невозможно вызвать метод ModelBuilder.Entity\<T\>() в принадлежащих типах (в настоящее время не предусмотрено).</span><span class="sxs-lookup"><span data-stu-id="294b7-194">You cannot call ModelBuilder.Entity\<T\>() on owned types (currently by design).</span></span>

- <span data-ttu-id="294b7-195">Пока не предусмотрены коллекции принадлежащих типов (в EF Core 2.1, но они появятся в версии 2.2).</span><span class="sxs-lookup"><span data-stu-id="294b7-195">No collections of owned types yet (as of EF Core 2.1, but they will be supported in 2.2).</span></span>

- <span data-ttu-id="294b7-196">Не поддерживаются необязательные (т. е. допускающие значение NULL) принадлежащие типы, которые сопоставляются с владельцем в одной таблице (т. е. с помощью разделения таблицы).</span><span class="sxs-lookup"><span data-stu-id="294b7-196">No support for optional (that is, nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="294b7-197">Это обусловлено тем, что сопоставление выполняется для каждого свойства, и у нас нет отдельной граничной метки для комплексного значения Null в целом.</span><span class="sxs-lookup"><span data-stu-id="294b7-197">This is because mapping is done for each property, we don't have a separate sentinel for the null complex value a as whole.</span></span>

- <span data-ttu-id="294b7-198">Не поддерживается наследование сопоставления для принадлежащих типов, но мы можем сопоставить два конечных типа одной иерархии наследования как два различных принадлежащих типа.</span><span class="sxs-lookup"><span data-stu-id="294b7-198">No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="294b7-199">EF Core не будет учитывать тот факт, что они являются частью одной иерархии.</span><span class="sxs-lookup"><span data-stu-id="294b7-199">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="294b7-200">Основные отличия от сложных типов EF6</span><span class="sxs-lookup"><span data-stu-id="294b7-200">Main differences with EF6's complex types</span></span>

- <span data-ttu-id="294b7-201">Разделение таблицы является необязательным, т. е. они также могут быть сопоставлены с отдельной таблицей и по-прежнему быть принадлежащими типами.</span><span class="sxs-lookup"><span data-stu-id="294b7-201">Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

- <span data-ttu-id="294b7-202">Они могут ссылаться на другие сущности (т. е. они могут выступать зависимой стороной в отношениях с другими не принадлежащими типами).</span><span class="sxs-lookup"><span data-stu-id="294b7-202">They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="294b7-203">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="294b7-203">Additional resources</span></span>

- <span data-ttu-id="294b7-204">**Мартин Фоулер (Martin Fowler). Шаблон ValueObject** </span><span class="sxs-lookup"><span data-stu-id="294b7-204">**Martin Fowler. ValueObject pattern** </span></span>\
  <https://martinfowler.com/bliki/ValueObject.html>

- <span data-ttu-id="294b7-205">**Эрик Эванс (Eric Evans). Domain-Driven Design: Tackling Complexity in the Heart of Software**.</span><span class="sxs-lookup"><span data-stu-id="294b7-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="294b7-206">(Книга, в которой рассматриваются объекты значений) </span><span class="sxs-lookup"><span data-stu-id="294b7-206">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="294b7-207">**Вон Вернон (Vaughn Vernon). Реализация проблемно-ориентированного проектирования (DDD).**</span><span class="sxs-lookup"><span data-stu-id="294b7-207">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="294b7-208">(Книга, в которой рассматриваются объекты значений) </span><span class="sxs-lookup"><span data-stu-id="294b7-208">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="294b7-209">**Свойства тени** </span><span class="sxs-lookup"><span data-stu-id="294b7-209">**Shadow Properties** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- <span data-ttu-id="294b7-210">**Сложные типы и (или) объекты значений**.</span><span class="sxs-lookup"><span data-stu-id="294b7-210">**Complex types and/or value objects**.</span></span> <span data-ttu-id="294b7-211">Обсуждение в репозитории сервиса GitHub для EF Core (вкладка "Issues" (Вопросы)) </span><span class="sxs-lookup"><span data-stu-id="294b7-211">Discussion in the EF Core GitHub repo (Issues tab) </span></span>\
  <https://github.com/aspnet/EntityFramework/issues/246>

- <span data-ttu-id="294b7-212">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="294b7-212">**ValueObject.cs.**</span></span> <span data-ttu-id="294b7-213">Базовый класс объекта значений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="294b7-213">Base value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- <span data-ttu-id="294b7-214">**Класс Address.**</span><span class="sxs-lookup"><span data-stu-id="294b7-214">**Address class.**</span></span> <span data-ttu-id="294b7-215">Пример класса объекта значений в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="294b7-215">Sample value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> <span data-ttu-id="294b7-216">[Назад](seedwork-domain-model-base-classes-interfaces.md)
> [Вперед](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="294b7-216">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
