---
title: Использование классов перечисления вместо типов перечисления
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Использование классов перечисления вместо типов перечисления
keywords: Docker, микрослужбы, ASP.NET, контейнер
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9df8dc3373930d38bf9f53e9c3a9e986156d3d89
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a>Использование классов перечисления вместо типов перечисления

[Перечисления](../../../../docs/csharp/language-reference/keywords/enum.md) (или *типы перечисления*) — это тонкая языковая оболочка вокруг целочисленного типа. Лучше всего использовать их при сохранении одного значения из закрытого набора значений. Хорошим примером является классификация по полу (например, мужской, женский, неизвестно) или размеру (малый, средний, большой). Использование перечислений для потока управления или более устойчивых абстракций может быть [признаком плохого кода](http://deviq.com/code-smells/). При таком использовании код будет недолговечным, поскольку множество операторов потока управления будут проверять значения перечисления.

Вместо этого можно создавать классы перечисления, позволяющие использовать широкие возможности объектно-ориентированного языка.

Как правило, это не критично, и для простоты вы можете по-прежнему использовать обычные [типы перечисления](../../../../docs/csharp/language-reference/keywords/enum.md), если вам так удобно.

## <a name="implementing-an-enumeration-base-class"></a>Применение базового класса перечисления

Микрослужба для заказа в eShopOnContainers содержит образец базового класса перечисления, как показано на следующем примере:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

Этот класс можно использовать как тип в любой сущности или объекте значения, как в следующем классе перечисления CardType:

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }

    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Перечисления нам не друзья (обновление)**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)

-   **Дэниэл Хардман (Daniel Hardman). Какие болезни переносят перечисления и как их вылечить**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

-   **Джимми Богард (Jimmy Bogard). Классы перечислений**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

-   **Стив Смит (Steve Smith). Альтернативы перечислениям в C#**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)

-   **Enumeration.cs.** Базовый класс перечисления в eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

-   **CardType.cs**. Пример класса перечисления в eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[Назад] (implement-value-objects.md) [Далее] (domain-model-layer-validations.md)
