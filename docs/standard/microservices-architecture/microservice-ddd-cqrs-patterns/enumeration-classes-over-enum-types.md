---
title: "Использование классов перечисления вместо типов перечисления"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Использование классов перечисления вместо типов перечисления"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a>Использование классов перечисления вместо типов перечисления

[Перечисления](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*перечисления* сокращенно) — это язык тонкой оболочкой целочисленный тип. Может потребоваться ограничить их использование до при сохранении одного значения из закрытых набор значений. Хорошими примерами могут классификации на основе пола (например, Мужской, Женский, неизвестный) или размеров (S, M, L, XL). С помощью перечисления для потока управления или более надежными абстракции может быть [кода Запах](http://deviq.com/code-smells/). Использование этого типа приведет к уязвимости кода с многих операторах потока управления, проверка значений перечисления.

Вместо этого можно создать перечисления классов, обеспечивающих широкие возможности объектно ориентированного языка. Однако это не критична и во многих случаях для простоты можно по-прежнему использовать обычных перечислений в случае предпочтения.

## <a name="implementing-enumeration-classes"></a>Реализация классов перечисления

Упорядочивания микрослужбу в eShopOnContainers предоставляет реализацию базового класса пример перечисления, как показано в следующем примере:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

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

Этот класс можно использовать как тип в любой сущности или значение объекта, как для следующий класс CardType перечисления.

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

-   **Перечисления злонамеренный — обновление**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)

-   **Дэниела Hardman. Порядок перечисления распределения болезни — И как ее исправить**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)

-   **Джимми Богард (Jimmy Bogard). Перечисление классов**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)

-   **Стив Смит. Альтернативные варианты перечислений в C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)

-   **Enumeration.cs.** Базовый класс перечисления в eShopOnContainers [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)

-   **CardType.cs**. Пример перечисления класса в eShopOnContainers.
    [*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
[Предыдущие] (реализация — значение objects.md) [Далее] (домен модели слоя validations.md)
