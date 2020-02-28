---
title: Реализация объектов значений
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Знакомство с возможностями и параметрами для реализации объектов значений с использованием новых функций Entity Framework.
ms.date: 01/30/2020
ms.openlocfilehash: 4ace5c141b1cbd2dcfefb7ea7165a4006b130479
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502513"
---
# <a name="implement-value-objects"></a>Реализация объектов значений

Как отмечалось в предыдущих разделах о сущностях и статистических выражениях, удостоверение — это базовый компонент сущностей. Тем не менее в системе существует множество объектов и элементов данных, не требующих удостоверений и их отслеживания, такие как объекты значений.

Объект значения может ссылаться на другие сущности. Например, в приложении, которое создает маршрут, содержащий сведения о том, как добраться из одной точки в другую, этот маршрут будет являться объектом значения. Это может быть набор точек конкретного маршрута, но такой маршрут не будет иметь удостоверения, несмотря на то, что внутренне он может ссылаться на сущности, такие как город, трасса и т. д.

На рисунке 7-13 изображен объект значения Address (адрес) в статистическом выражении Order (заказ).

![Схема, на которой показан объект значения Address (Адрес) в агрегате Order (Заказ).](./media/implement-value-objects/value-object-within-aggregate.png)

**Рис. 7-13**. Объект значения Address (адрес) в статистическом выражении Order (заказ)

Как показано на рисунке 7-13, сущность обычно состоит из нескольких атрибутов. Например, сущность `Order` можно смоделировать как сущность с удостоверением и внутренне состоящей из набора свойств, таких как OrderId, OrderDate, OrderItems и т. д. Но адрес, который является просто сложным значением, состоящим из страны или региона, улицы, города и т. д. и не имеющим удостоверения в этом домене, необходимо моделировать и рассматривать как объект значения.

## <a name="important-characteristics-of-value-objects"></a>Важные характеристики объектов значений

У объектов значений две основные характеристики:

- У них нет удостоверения.

- Они неизменяемы.

Первая характеристика уже обсуждались. Неизменяемость является важным требованием. После создания объекта значения он должен оставаться неизменяемым. Таким образом, при создании объекта необходимо задать необходимые значения, и они не должны изменяться в течение всего времени существования объекта.

Благодаря своей неизменяемости объекты значений позволяют применять некоторые приемы для повышения производительности. Это особенно справедливо для систем, содержащих тысячи экземпляров объектов значений, многие из которых имеют одинаковые значения. Неизменяемость позволяет использовать их повторно, они могут быть взаимозаменяемыми объектами, поскольку их значения совпадают и они не имеют удостоверений. Такая оптимизация иногда может провести грань между медленным приложением и приложением с высокой производительностью. Конечно, все это зависит от среды приложения и контекста развертывания.

## <a name="value-object-implementation-in-c"></a>Реализация объекта значения в C\#

С точки зрения реализации можно создать базовый класс объекта значения, имеющий основные служебные методы, такие как сравнение, основанное на сравнении всех атрибутов (поскольку объект значения не должен задаваться удостоверением) и других основных характеристик. Следующий пример показывает создание базового класса объекта значения, используемого в микрослужбе заказов из eShopOnContainers.

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

Этот класс можно использовать при реализации реального объекта значения, как это показано на примере объекта значения Address в следующем коде:

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

Вы можете видеть, что у этой реализации объекта значения для Address нет удостоверения, а следовательно, и поля ID, ни в классе Address, ни даже в классе ValueObject.

Отсутствие поля ИД в классе, используемом Entity Framework (EF), было недопустимым до выпуска EF Core 2.0. Эта возможность помогает реализовывать более эффективные объекты значений без ИД. Именно это пояснение используется в следующем разделе.

Можно возразить, что объекты значений, являясь неизменяемыми, должны быть доступны только для чтения (например, свойства, отвечающие только за получение), и это действительно так. Однако объекты значений обычно сериализируются и десериализируются для прохождения очередей сообщений, а наличие доступа только для чтения не позволяет десериализатору назначать значения, поэтому мы просто оставляем их в виде частного набора, доступного только для чтения, чего хватает для практического применения.

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20-and-later"></a>Хранение объектов значений в базе данных в EF Core 2.0 и более поздних версий

Мы узнали, как определить объект значения в модели домена. Но как же сохранить его в базе данных через Entity Framework Core, так как он обычно обращается к сущностям по удостоверению?

### <a name="background-and-older-approaches-using-ef-core-11"></a>Общие сведения и устаревший подход с использованием EF Core 1.1

Для справки: при использовании EF Core 1.0 и 1.1 было невозможно использовать [сложные типы](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) в том виде, в котором они были определены в EF 6.x в традиционном решении .NET Framework. Таким образом, при использовании EF Core 1.0 и 1.1 необходимо хранить объект значения в виде сущности EF с полем ID. Затем, чтобы сущность больше походила на объект значения, нужно скрыть поле ID, дав понять таким образом, что удостоверение объекта значения не важно в данной модели домена. Можно скрыть поле ID при помощи [затемнения свойства](https://docs.microsoft.com/ef/core/modeling/shadow-properties ). Так как такой вариант скрытия удостоверения в модели задается на уровне инфраструктуры EF, это будет в каком-то смысле прозрачно для модели домена.

В первоначальной версии eShopOnContainers (.NET Core 1.1) скрытие поля ID, необходимое для инфраструктуры EF Core, было реализовано на уровне DbContext при помощи текучего API в инфраструктуре проекта следующим образом. Таким образом, удостоверение было скрыто с точки зрения модели домена, но все еще присутствует в инфраструктуре.

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

Тем не менее сохраняемость этого объекта значения в базе данных обеспечивалась так же, как и обычной сущности в любой другой таблице.

В EF Core 2.0 и более поздних версиях появились новые и лучшие способы хранения объектов значений.

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20-and-later"></a>Хранение объектов значений в виде принадлежащих типов сущностей в EF Core 2.0 и более поздних версиях

Даже при некоторых преимуществах канонического шаблона объекта значения в предметно-ориентированном проектировании (DDD) перед принадлежащим типом сущности EF Core сейчас это является наилучшим способом хранения объектов значений в EF Core 2.0 и более поздних версий. Существующие ограничения приведены в конце этого раздела.

Возможность использования принадлежащих типов сущностей была добавлена в EF Core начиная с версии 2.0.

Принадлежащий тип сущности позволяет сопоставить типы, которые не имеют своего удостоверения, определены явным образом в модели домена и используются в качестве свойств, таких как объект значения, в любой сущности. Принадлежащий тип сущности предоставляет другому типу сущности тот же тип среды CLR (в данном случае это просто обычный класс). Сущность, содержащая определяющую навигацию, является сущностью-владельцем. При запросе владельца по умолчанию включаются принадлежащие типы.

При взгляде на модель домена принадлежащий тип выглядит так, как будто он не имеет удостоверения. На самом деле принадлежащие типы имеют удостоверения, но свойство навигации владельца является частью этого удостоверения.

Удостоверение экземпляров принадлежащих типов не является полностью их собственным. Оно состоит из трех компонентов:

- Удостоверение владельца

- Указывающее на него свойство навигации

- В случае с коллекциями принадлежащих типов — независимый компонент (поддерживается в EF Core 2.2 и более поздних версиях).

Например, в модели домена Ordering в eShopOnContainers объект значения Address, являющийся частью сущности Order, реализован как принадлежащий тип сущности в рамках сущности-владельца, которой является сущность Order. Адрес — это тип, не имеющий определенного в модели домена свойства-удостоверения. Он используется как свойство сущности Order для указания адреса доставки конкретного заказа.

По соглашению для принадлежащего типа создается теневой первичный ключ, и этот тип сопоставляется с той же таблицей, что и владелец, с помощью разбиения таблицы. Это позволяет использовать принадлежащие типы аналогично сложным типам в EF6 в традиционном .NET Framework.

Важно отметить, что по соглашению принадлежащие типы никогда не обнаруживаются EF Core, поэтому их необходимо объявлять явно.

В eShopOnContainers, в файле OrderingContext.cs, в методе OnModelCreating() применяется несколько конфигураций инфраструктуры. Одна из них относится к сущности Order.

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

В следующем коде инфраструктура сохраняемости определяется для сущности Order:

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

В приведенном выше коде метод `orderConfiguration.OwnsOne(o => o.Address)` указывает, что свойство `Address` принадлежит сущности типа `Order`.

По умолчанию соглашения EF Core именуют столбцы базы данных для свойств принадлежащего типа сущностей следующим образом: `EntityProperty_OwnedEntityProperty`. Следовательно, внутренние свойства типа `Address` будут отображаться в таблице `Orders` с именами `Address_Street`, `Address_City` (и так далее для свойств `State`, `Country` и `ZipCode`).

Можно переименовать эти столбцы, добавив текучий метод `Property().HasColumnName()`. В случае, когда свойство `Address` является общедоступным свойством, сопоставление будет выполняться подобным образом:

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

Метод `OwnsOne` возможно объединять в цепочку для текущего сопоставления. В следующем гипотетическом примере сущность `OrderDetails` владеет `BillingAddress` и `ShippingAddress`, которые принадлежат к типу `Address`. А `OrderDetails`, в свою очередь, принадлежит типу `Order`.

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

### <a name="additional-details-on-owned-entity-types"></a>Дополнительные сведения о принадлежащих типах сущностей

- Принадлежащие типы определяются при настройке свойства навигации конкретного типа с помощью текучего API OwnsOne.

- Определение принадлежащего типа в нашей модели метаданных состоит из следующих элементов: тип владельца, свойство навигации и тип среды CLR принадлежащего типа.

- Удостоверение (ключ) экземпляра принадлежащего типа в нашем стеке состоит из удостоверения владельца и определения принадлежащего типа.

#### <a name="owned-entities-capabilities"></a>Возможности принадлежащих сущностей

- Принадлежащие типы могут ссылаться на другие сущности, как принадлежащие (вложенные принадлежащие типы), так и не принадлежащие (обычные ссылки свойств навигации на другие сущности).

- Можно сопоставлять одной сущности-владельцу одни и те же типы среды CLR как разные принадлежащие типы с помощью различных свойств навигации.

- По соглашению выполняется разделение таблицы, однако можно отказаться от этого и сопоставить принадлежащий тип в другую таблицу, используя метод ToTable.

- Безотложная загрузка для принадлежащих типов выполняется автоматически, т. е. в запросе не нужно вызывать `.Include()`.

- Можно настроить с помощью атрибута `[Owned]`, используя EF Core 2.1 или более поздней версии.

- Может выполнять обработку коллекций принадлежащих типов (при использовании версии 2.2 и более поздних).

#### <a name="owned-entities-limitations"></a>Ограничения принадлежащих сущностей

- `DbSet<T>` нельзя создать из принадлежащих типов (изначально не предусмотрено).

- Нельзя вызвать `ModelBuilder.Entity<T>()` для собственных типов (в настоящее время намеренно).

- Не поддерживаются необязательные (т. е. допускающие значение NULL) принадлежащие типы, которые сопоставляются с владельцем в одной таблице (т. е. с помощью разделения таблицы). Это обусловлено тем, что сопоставление выполняется для каждого свойства, и у нас нет отдельной граничной метки для комплексного значения Null в целом.

- Не поддерживается наследование сопоставления для принадлежащих типов, но мы можем сопоставить два конечных типа одной иерархии наследования как два различных принадлежащих типа. EF Core не будет учитывать тот факт, что они являются частью одной иерархии.

#### <a name="main-differences-with-ef6s-complex-types"></a>Основные отличия от сложных типов EF6

- Разделение таблицы является необязательным, т. е. они также могут быть сопоставлены с отдельной таблицей и по-прежнему быть принадлежащими типами.

- Они могут ссылаться на другие сущности (т. е. они могут выступать зависимой стороной в отношениях с другими не принадлежащими типами).

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Мартин Фоулер (Martin Fowler). Шаблон ValueObject** \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Эрик Эванс (Eric Evans). Domain-Driven Design: Tackling Complexity in the Heart of Software**. (Книга, в которой рассматриваются объекты значений) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Вон Вернон (Vaughn Vernon). Реализация проблемно-ориентированного проектирования (DDD).** (Книга, в которой рассматриваются объекты значений) \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Принадлежащие типы сущностей** \
  <https://docs.microsoft.com/ef/core/modeling/owned-entities>

- **Свойства тени** \
  <https://docs.microsoft.com/ef/core/modeling/shadow-properties>

- **Сложные типы и (или) объекты значений**. Обсуждение в репозитории сервиса GitHub для EF Core (вкладка "Issues" (Вопросы)) \
  <https://github.com/dotnet/efcore/issues/246>

- **ValueObject.cs.** Базовый класс объекта значений в eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- **Класс Address.** Пример класса объекта значений в eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> [Назад](seedwork-domain-model-base-classes-interfaces.md)
> [Вперед](enumeration-classes-over-enum-types.md)
