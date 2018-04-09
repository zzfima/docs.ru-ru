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
ms.openlocfilehash: 57ff60ea01421f1a2a0466b7de9716b72b02d2c1
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="79f37-104">Использование классов перечисления вместо типов перечисления</span><span class="sxs-lookup"><span data-stu-id="79f37-104">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="79f37-105">[Перечисления](../../../../docs/csharp/language-reference/keywords/enum.md) (или *типы перечисления*) — это тонкая языковая оболочка вокруг целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="79f37-105">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="79f37-106">Лучше всего использовать их при сохранении одного значения из закрытого набора значений.</span><span class="sxs-lookup"><span data-stu-id="79f37-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="79f37-107">Хорошим примером является классификация по полу (например, мужской, женский, неизвестно) или размеру (малый, средний, большой).</span><span class="sxs-lookup"><span data-stu-id="79f37-107">Classification based on gender (for example, male, female, unknown) or sizes (small, medium, large) are good examples.</span></span> <span data-ttu-id="79f37-108">Использование перечислений для потока управления или более устойчивых абстракций может быть [признаком плохого кода](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="79f37-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="79f37-109">При таком использовании код будет недолговечным, поскольку множество операторов потока управления будут проверять значения перечисления.</span><span class="sxs-lookup"><span data-stu-id="79f37-109">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="79f37-110">Вместо этого можно создавать классы перечисления, позволяющие использовать широкие возможности объектно-ориентированного языка.</span><span class="sxs-lookup"><span data-stu-id="79f37-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="79f37-111">Как правило, это не критично, и для простоты вы можете по-прежнему использовать обычные [типы перечисления](../../../../docs/csharp/language-reference/keywords/enum.md), если вам так удобно.</span><span class="sxs-lookup"><span data-stu-id="79f37-111">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="79f37-112">Применение базового класса перечисления</span><span class="sxs-lookup"><span data-stu-id="79f37-112">Implementing an Enumeration base class</span></span>

<span data-ttu-id="79f37-113">Микрослужба для заказа в eShopOnContainers содержит образец базового класса перечисления, как показано на следующем примере:</span><span class="sxs-lookup"><span data-stu-id="79f37-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

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

<span data-ttu-id="79f37-114">Этот класс можно использовать как тип в любой сущности или объекте значения, как в следующем классе перечисления CardType:</span><span class="sxs-lookup"><span data-stu-id="79f37-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="79f37-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="79f37-115">Additional resources</span></span>

-   <span data-ttu-id="79f37-116">**Перечисления нам не друзья (обновление)**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="79f37-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="79f37-117">**Дэниэл Хардман (Daniel Hardman). Какие болезни переносят перечисления и как их вылечить**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="79f37-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="79f37-118">**Джимми Богард (Jimmy Bogard). Классы перечислений**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="79f37-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="79f37-119">**Стив Смит (Steve Smith). Альтернативы перечислениям в C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="79f37-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="79f37-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="79f37-120">**Enumeration.cs.**</span></span> <span data-ttu-id="79f37-121">Базовый класс перечисления в eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="79f37-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="79f37-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="79f37-122">**CardType.cs**.</span></span> <span data-ttu-id="79f37-123">Пример класса перечисления в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="79f37-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="79f37-124">[Назад] (implement-value-objects.md) [Далее] (domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="79f37-124">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
