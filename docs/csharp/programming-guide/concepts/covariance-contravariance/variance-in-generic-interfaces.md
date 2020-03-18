---
title: Вариативность в универсальных интерфейсах (C#)
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: 2020ea54734724de775192a1a438413a73003d17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169666"
---
# <a name="variance-in-generic-interfaces-c"></a>Вариативность в универсальных интерфейсах (C#)

В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы.

Начиная с .NET Framework 4 вариативными являются следующие интерфейсы:

- <xref:System.Collections.Generic.IEnumerable%601> (T является ковариантным)

- <xref:System.Collections.Generic.IEnumerator%601> (T является ковариантным)

- <xref:System.Linq.IQueryable%601> (T является ковариантным)

- <xref:System.Linq.IGrouping%602> (`TKey` и `TElement` являются ковариантными)

- <xref:System.Collections.Generic.IComparer%601> (T является контравариантным)

- <xref:System.Collections.Generic.IEqualityComparer%601> (T является контравариантным)

- <xref:System.IComparable%601> (T является контравариантным)

Начиная с .NET Framework 4.5, вариативными являются следующие интерфейсы:

- <xref:System.Collections.Generic.IReadOnlyList%601> (T является ковариантным)

- <xref:System.Collections.Generic.IReadOnlyCollection%601> (T является ковариантным)

Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable<Object>` и `IEnumerable<String>`. Интерфейс `IEnumerable<String>` не наследует интерфейс `IEnumerable<Object>`. При этом тип `String` наследует тип `Object`, и в некоторых случаях может потребоваться назначить объекты этих интерфейсов друг другу. Это показано в следующем примере кода.

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

В более ранних версиях .NET Framework этот код приводил к ошибке компиляции в C#, если в Visual Basic было включено `Option Strict`. Но теперь можно использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку интерфейс <xref:System.Collections.Generic.IEnumerable%601> является ковариантным.

Контравариантность позволяет методу иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа интерфейса. Чтобы продемонстрировать функцию контравариантности, предположим, что создан класса `BaseComparer` для сравнения экземпляров класса `BaseClass`. Класс `BaseComparer` реализует интерфейс `IEqualityComparer<BaseClass>`. Поскольку теперь интерфейс <xref:System.Collections.Generic.IEqualityComparer%601> является контравариантным, для сравнения экземпляров классов, наследующих класс `BaseComparer`, можно использовать класс `BaseClass`. Это показано в следующем примере кода.

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

Дополнительные примеры см.в разделе [Использование вариативности в интерфейсах для универсальных коллекций (C#)](./using-variance-in-interfaces-for-generic-collections.md).

Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов. Типы значений не поддерживают вариативность. Например, `IEnumerable<int>` нельзя неявно преобразовать в `IEnumerable<object>`, так как типом значения является integer.

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

Кроме того, важно помнить, что классы, которые реализуют вариативные интерфейсы, сами являются инвариантными. Например, несмотря на то, что <xref:System.Collections.Generic.List%601> реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, неявно преобразовать `List<String>` в `List<Object>` нельзя. Это показано в следующем примере кода.

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a>См. также раздел

- [Использование вариативности в интерфейсах для универсальных коллекций (C#)](./using-variance-in-interfaces-for-generic-collections.md)
- [Создание вариантных универсальных интерфейсов (C#)](./creating-variant-generic-interfaces.md)
- [Универсальные интерфейсы](../../../../standard/generics/interfaces.md)
- [Вариативность в делегатах (C#)](./variance-in-delegates.md)
