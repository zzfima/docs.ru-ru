---
title: Использование классов перечисления вместо типов перечисления
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Сведения о том, как можно использовать классы перечисления вместо перечислений для преодоления некоторых ограничений последних.
ms.date: 10/08/2018
ms.openlocfilehash: 82bd80d19b3b73eb2f45ede8cc7ad4593c688277
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628466"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="a96fa-103">Использование классов перечисления вместо типов перечисления</span><span class="sxs-lookup"><span data-stu-id="a96fa-103">Use enumeration classes instead of enum types</span></span>

<span data-ttu-id="a96fa-104">[Перечисления](../../../csharp/language-reference/builtin-types/enum.md) (или *типы перечисления*) — это тонкая языковая оболочка вокруг целочисленного типа.</span><span class="sxs-lookup"><span data-stu-id="a96fa-104">[Enumerations](../../../csharp/language-reference/builtin-types/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="a96fa-105">Лучше всего использовать их при сохранении одного значения из закрытого набора значений.</span><span class="sxs-lookup"><span data-stu-id="a96fa-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="a96fa-106">Хорошим примером является классификация, основанная на размерах (небольшой, средний, большой).</span><span class="sxs-lookup"><span data-stu-id="a96fa-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="a96fa-107">Использование перечислений для потока управления или более устойчивых абстракций может быть [признаком плохого кода](https://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="a96fa-107">Using enums for control flow or more robust abstractions can be a [code smell](https://deviq.com/code-smells/).</span></span> <span data-ttu-id="a96fa-108">При таком использовании код будет недолговечным, поскольку множество операторов потока управления будут проверять значения перечисления.</span><span class="sxs-lookup"><span data-stu-id="a96fa-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="a96fa-109">Вместо этого можно создавать классы перечисления, позволяющие использовать широкие возможности объектно-ориентированного языка.</span><span class="sxs-lookup"><span data-stu-id="a96fa-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="a96fa-110">Как правило, это не критично, и для простоты вы можете по-прежнему использовать обычные [типы перечисления](../../../csharp/language-reference/builtin-types/enum.md), если вам так удобно.</span><span class="sxs-lookup"><span data-stu-id="a96fa-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../csharp/language-reference/builtin-types/enum.md) if that's your preference.</span></span> <span data-ttu-id="a96fa-111">В любом случае использование классов перечисления больше связано с бизнес-концепциями.</span><span class="sxs-lookup"><span data-stu-id="a96fa-111">Anyway, the use of enumeration classes is more related to business-related concepts.</span></span>

## <a name="implement-an-enumeration-base-class"></a><span data-ttu-id="a96fa-112">Применение базового класса перечисления</span><span class="sxs-lookup"><span data-stu-id="a96fa-112">Implement an Enumeration base class</span></span>

<span data-ttu-id="a96fa-113">Микрослужба для заказа в eShopOnContainers содержит образец базового класса перечисления, как показано на следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a96fa-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public |
                                         BindingFlags.Static |
                                         BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;

        if (otherValue == null)
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id);

    // Other utility methods ...
}
```

<span data-ttu-id="a96fa-114">Этот класс можно использовать как тип в любой сущности или любом объекте значения, как в следующем классе `CardType` : `Enumeration`:</span><span class="sxs-lookup"><span data-stu-id="a96fa-114">You can use this class as a type in any entity or value object, as for the following `CardType` : `Enumeration` class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="a96fa-115">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a96fa-115">Additional resources</span></span>

- <span data-ttu-id="a96fa-116">**Джимми Богард (Jimmy Bogard). Классы перечислений** </span><span class="sxs-lookup"><span data-stu-id="a96fa-116">**Jimmy Bogard. Enumeration classes** </span></span>\
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- <span data-ttu-id="a96fa-117">**Стив Смит (Steve Smith). Альтернативы перечислениям в C#**  </span><span class="sxs-lookup"><span data-stu-id="a96fa-117">**Steve Smith. Enum Alternatives in C#** </span></span>\
  <https://ardalis.com/enum-alternatives-in-c>

- <span data-ttu-id="a96fa-118">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="a96fa-118">**Enumeration.cs.**</span></span> <span data-ttu-id="a96fa-119">Базовый класс перечисления в eShopOnContainers </span><span class="sxs-lookup"><span data-stu-id="a96fa-119">Base Enumeration class in eShopOnContainers </span></span>\
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- <span data-ttu-id="a96fa-120">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="a96fa-120">**CardType.cs**.</span></span> <span data-ttu-id="a96fa-121">Пример класса перечисления в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="a96fa-121">Sample Enumeration class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- <span data-ttu-id="a96fa-122">**SmartEnum**.</span><span class="sxs-lookup"><span data-stu-id="a96fa-122">**SmartEnum**.</span></span> <span data-ttu-id="a96fa-123">Ardalis — классы, помогающие создавать более эффективные строго типизированные перечисления в .NET.</span><span class="sxs-lookup"><span data-stu-id="a96fa-123">Ardalis - Classes to help produce strongly typed smarter enums in .NET.</span></span> \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
><span data-ttu-id="a96fa-124">[Назад](implement-value-objects.md)
>[Вперед](domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="a96fa-124">[Previous](implement-value-objects.md)
[Next](domain-model-layer-validations.md)</span></span>
