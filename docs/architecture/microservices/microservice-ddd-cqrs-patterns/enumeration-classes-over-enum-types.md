---
title: Использование классов перечисления вместо типов перечисления
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Сведения о том, как можно использовать классы перечисления вместо перечислений для преодоления некоторых ограничений последних.
ms.date: 10/08/2018
ms.openlocfilehash: 6752adb28b1bd0982c66fa2d021b04b999447c6e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337679"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a>Использование классов перечисления вместо типов перечисления

[Перечисления](../../../csharp/language-reference/builtin-types/enum.md) (или *типы перечисления*) — это тонкая языковая оболочка вокруг целочисленного типа. Лучше всего использовать их при сохранении одного значения из закрытого набора значений. Хорошим примером является классификация, основанная на размерах (небольшой, средний, большой). Использование перечислений для потока управления или более устойчивых абстракций может быть [признаком плохого кода](https://deviq.com/code-smells/). При таком использовании код будет недолговечным, поскольку множество операторов потока управления будут проверять значения перечисления.

Вместо этого можно создавать классы перечисления, позволяющие использовать широкие возможности объектно-ориентированного языка.

Как правило, это не критично, и для простоты вы можете по-прежнему использовать обычные [типы перечисления](../../../csharp/language-reference/builtin-types/enum.md), если вам так удобно. В любом случае использование классов перечисления больше связано с бизнес-концепциями.

## <a name="implement-an-enumeration-base-class"></a>Применение базового класса перечисления

Микрослужба для заказа в eShopOnContainers содержит образец базового класса перечисления, как показано на следующем примере:

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

Этот класс можно использовать как тип в любой сущности или любом объекте значения, как в следующем классе `CardType` : `Enumeration`:

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

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Перечисления нам не друзья (обновление)**  \
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- **Дэниэл Хардман (Daniel Hardman). Какие болезни переносят перечисления и как их вылечить** \
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- **Джимми Богард (Jimmy Bogard). Классы перечислений** \
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- **Стив Смит (Steve Smith). Альтернативы перечислениям в C#**  \
  <https://ardalis.com/enum-alternatives-in-c>

- **Enumeration.cs.** Базовый класс перечисления в eShopOnContainers \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- **CardType.cs**. Пример класса перечисления в eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- **SmartEnum**. Ardalis — классы, помогающие создавать более эффективные строго типизированные перечисления в .NET. \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
>[Назад](implement-value-objects.md)
>[Вперед](domain-model-layer-validations.md)
