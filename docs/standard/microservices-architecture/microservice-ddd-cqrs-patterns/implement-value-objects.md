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
# <a name="implementing-value-objects"></a>Реализации объектов значение

Как отмечалось в предыдущих разделах о сущностях и статистические выражения, удостоверения — это основа для сущностей. Тем не менее существует множество объектов и элементов данных в системе, не требующих идентификацию и отслеживание, такие как значение объектов.

Объект значения можно ссылаться на другие сущности. Например, в приложении, которое создает маршрут, который содержит сведения о получении из одной точки в другую этот маршрут будет объект значения. Было бы моментальный снимок точек на конкретный маршрут, но предлагаемый маршрута не будет удостоверение, несмотря на то, что внутренне оно может ссылаться на сущности, такие как город, дорожный, и т. д.

Рис. 9-13 показано значение адреса объекта в статистическое выражение Order.

![](./media/image14.png)

**Рис. 9-13**. Значение объекта в порядке статистическое выражение адреса

Как показано на рисунке 9-13, сущность обычно состоит из нескольких атрибутов. Например заказ может моделируется как сущность с использованием идентификатора и внутренне состоит из набора атрибутов, таких как OrderId OrderDate, OrderItems, и т. д. Однако адрес, который является просто сложное значение, состоящие из страны, улица, Город, т. д. должны быть смоделированы и рассматривается в качестве значения объекта.

## <a name="important-characteristics-of-value-objects"></a>Важные характеристики объектов значение

Существует два основных характеристик для объектов значение:

-   Они имеют не идентификатор.

-   Они являются неизменяемыми.

Первая характеристика уже обсуждались. Неизменность является важным требованием. Значения объекта значения должны быть неизменяемыми после создания объекта. Таким образом при создании объекта необходимо указать необходимые значения, но не должно допускать их можно изменять во время существования объекта.

Значение объектов позволяют выполнять некоторые рекомендации для производительности благодаря своей природе неизменяемыми. Это особенно важно в системах которых может быть тысячи значение экземпляры объектов, многие из которых имеют одинаковые значения. Неизменяемый характера позволяет им для повторного использования; они могут быть взаимозаменяемыми объектами, поскольку их значения совпадают, и они не имеют ни одна учетная запись. Этот тип оптимизации иногда можно провести различие между медленного выполнения и программ с высокой производительностью. Конечно всех этих случаях зависят от среды приложения и контекст развертывания.

## <a name="value-object-implementation-in-c"></a>Реализация объекта значение в C\#

С точки зрения реализации может иметь значение объекта базовый класс, имеющий основные служебные методы как на основе сравнения между атрибутами (так как объект значения не должен быть основан на удостоверении) и другие основные характеристики равенства. Следующий пример показывает значение объекта базовый класс, используемый в упорядочивания микрослужбу из eShopOnContainers.

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

Этот класс можно использовать при реализации фактическое значение объекта, как и в объект значения адреса, показано в следующем примере:

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

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>Скрытие характеристика идентификаторов при использовании EF ядра для сохранения объектов значение

Ограничения при использовании EF ядра, что в текущей версии (EF Core 1.1) нельзя использовать [сложных типов](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) , определенный в EF 6.x. Таким образом как сущность EF необходимо хранить значение объекта. Тем не менее можно скрыть его идентификатор, станет ясно удостоверение не важно в модели, объект значения. Скрыть идентификатор, используя идентификатор как свойство тени. Поскольку, скрытия идентификатор модели настройки на уровне инфраструктуры, он будет прозрачным для модели домена и его реализации инфраструктуры может измениться в будущем.

В eShopOnContainers скрытый идентификатор Затребован EF базовой инфраструктуры реализуется на уровне DbContext следующим образом с помощью плавного API в проект инфраструктуры.

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

Таким образом идентификатор скрыта от домена модели точки зрения, и в будущем, в инфраструктуре значение объекта может также быть реализован как сложный тип или другим способом.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Мартин Фоулер (Martin Fowler). Шаблон ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Эрик Эванс (Eric Evans). Проектирование на основе домена: Выполняемой сложность лежит в основе программного обеспечения.** (Книга; включает в себя обсуждение значение объектов) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Вон Вернон (Vaughn Vernon). Реализация разработки на основе домена.** (Книга; включает в себя обсуждение значение объектов) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Скрывать свойства**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **Сложные типы или объектов, значение**. Обсуждение в репозитории EF Core GitHub (вкладка «проблемы») [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs.** Базовое значение класса объекта в eShopOnContainers.
    [*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **Адрес класса.** Пример класса значения объекта в eShopOnContainers.
    [*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[Предыдущие] (seedwork-domain-model-base-classes-interfaces.md) [Далее] (перечисление классы over-enum-types.md)
