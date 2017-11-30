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
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="bde62-104">Использование классов перечисления вместо типов перечисления</span><span class="sxs-lookup"><span data-stu-id="bde62-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="bde62-105">[Перечисления](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*перечисления* сокращенно) — это язык тонкой оболочкой целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="bde62-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="bde62-106">Может потребоваться ограничить их использование до при сохранении одного значения из закрытых набор значений.</span><span class="sxs-lookup"><span data-stu-id="bde62-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="bde62-107">Хорошими примерами могут классификации на основе пола (например, Мужской, Женский, неизвестный) или размеров (S, M, L, XL).</span><span class="sxs-lookup"><span data-stu-id="bde62-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="bde62-108">С помощью перечисления для потока управления или более надежными абстракции может быть [кода Запах](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="bde62-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="bde62-109">Использование этого типа приведет к уязвимости кода с многих операторах потока управления, проверка значений перечисления.</span><span class="sxs-lookup"><span data-stu-id="bde62-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="bde62-110">Вместо этого можно создать перечисления классов, обеспечивающих широкие возможности объектно ориентированного языка.</span><span class="sxs-lookup"><span data-stu-id="bde62-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="bde62-111">Однако это не критична и во многих случаях для простоты можно по-прежнему использовать обычных перечислений в случае предпочтения.</span><span class="sxs-lookup"><span data-stu-id="bde62-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="bde62-112">Реализация классов перечисления</span><span class="sxs-lookup"><span data-stu-id="bde62-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="bde62-113">Упорядочивания микрослужбу в eShopOnContainers предоставляет реализацию базового класса пример перечисления, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="bde62-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="bde62-114">Этот класс можно использовать как тип в любой сущности или значение объекта, как для следующий класс CardType перечисления.</span><span class="sxs-lookup"><span data-stu-id="bde62-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="bde62-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="bde62-115">Additional resources</span></span>

-   <span data-ttu-id="bde62-116">**Перечисления злонамеренный — обновление**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="bde62-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="bde62-117">**Дэниела Hardman. Порядок перечисления распределения болезни — И как ее исправить**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="bde62-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="bde62-118">**Джимми Богард (Jimmy Bogard). Перечисление классов**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="bde62-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="bde62-119">**Стив Смит. Альтернативные варианты перечислений в C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="bde62-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="bde62-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="bde62-120">**Enumeration.cs.**</span></span> <span data-ttu-id="bde62-121">Базовый класс перечисления в eShopOnContainers [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="bde62-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="bde62-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="bde62-122">**CardType.cs**.</span></span> <span data-ttu-id="bde62-123">Пример перечисления класса в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="bde62-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="bde62-124">*https://github.com/DotNet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="bde62-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="bde62-125">[Предыдущие] (реализация — значение objects.md) [Далее] (домен модели слоя validations.md)</span><span class="sxs-lookup"><span data-stu-id="bde62-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
