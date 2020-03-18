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
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="93ea2-102">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="93ea2-102">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="93ea2-103">В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="93ea2-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="93ea2-104">Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="93ea2-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span>

<span data-ttu-id="93ea2-105">Начиная с .NET Framework 4 вариативными являются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="93ea2-105">Starting with .NET Framework 4, the following interfaces are variant:</span></span>

- <span data-ttu-id="93ea2-106"><xref:System.Collections.Generic.IEnumerable%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="93ea2-107"><xref:System.Collections.Generic.IEnumerator%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="93ea2-108"><xref:System.Linq.IQueryable%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="93ea2-109"><xref:System.Linq.IGrouping%602> (`TKey` и `TElement` являются ковариантными)</span><span class="sxs-lookup"><span data-stu-id="93ea2-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="93ea2-110"><xref:System.Collections.Generic.IComparer%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="93ea2-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="93ea2-112"><xref:System.IComparable%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-112"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="93ea2-113">Начиная с .NET Framework 4.5, вариативными являются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="93ea2-113">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <span data-ttu-id="93ea2-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T is covariant)</span></span>

- <span data-ttu-id="93ea2-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="93ea2-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T is covariant)</span></span>

<span data-ttu-id="93ea2-116">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметре универсального типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="93ea2-116">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="93ea2-117">Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable<Object>` и `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-117">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="93ea2-118">Интерфейс `IEnumerable<String>` не наследует интерфейс `IEnumerable<Object>`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-118">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="93ea2-119">При этом тип `String` наследует тип `Object`, и в некоторых случаях может потребоваться назначить объекты этих интерфейсов друг другу.</span><span class="sxs-lookup"><span data-stu-id="93ea2-119">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="93ea2-120">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="93ea2-120">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="93ea2-121">В более ранних версиях .NET Framework этот код приводил к ошибке компиляции в C#, если в Visual Basic было включено `Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-121">In earlier versions of the .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="93ea2-122">Но теперь можно использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку интерфейс <xref:System.Collections.Generic.IEnumerable%601> является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="93ea2-122">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="93ea2-123">Контравариантность позволяет методу иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="93ea2-123">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="93ea2-124">Чтобы продемонстрировать функцию контравариантности, предположим, что создан класса `BaseComparer` для сравнения экземпляров класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-124">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="93ea2-125">Класс `BaseComparer` реализует интерфейс `IEqualityComparer<BaseClass>`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-125">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="93ea2-126">Поскольку теперь интерфейс <xref:System.Collections.Generic.IEqualityComparer%601> является контравариантным, для сравнения экземпляров классов, наследующих класс `BaseComparer`, можно использовать класс `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="93ea2-126">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="93ea2-127">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="93ea2-127">This is shown in the following code example.</span></span>

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

<span data-ttu-id="93ea2-128">Дополнительные примеры см.в разделе [Использование вариативности в интерфейсах для универсальных коллекций (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="93ea2-128">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="93ea2-129">Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="93ea2-129">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="93ea2-130">Типы значений не поддерживают вариативность.</span><span class="sxs-lookup"><span data-stu-id="93ea2-130">Value types do not support variance.</span></span> <span data-ttu-id="93ea2-131">Например, `IEnumerable<int>` нельзя неявно преобразовать в `IEnumerable<object>`, так как типом значения является integer.</span><span class="sxs-lookup"><span data-stu-id="93ea2-131">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="93ea2-132">Кроме того, важно помнить, что классы, которые реализуют вариативные интерфейсы, сами являются инвариантными.</span><span class="sxs-lookup"><span data-stu-id="93ea2-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="93ea2-133">Например, несмотря на то, что <xref:System.Collections.Generic.List%601> реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, неявно преобразовать `List<String>` в `List<Object>` нельзя.</span><span class="sxs-lookup"><span data-stu-id="93ea2-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<String>` to `List<Object>`.</span></span> <span data-ttu-id="93ea2-134">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="93ea2-134">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="93ea2-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93ea2-135">See also</span></span>

- [<span data-ttu-id="93ea2-136">Использование вариативности в интерфейсах для универсальных коллекций (C#)</span><span class="sxs-lookup"><span data-stu-id="93ea2-136">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="93ea2-137">Создание вариантных универсальных интерфейсов (C#)</span><span class="sxs-lookup"><span data-stu-id="93ea2-137">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)
- [<span data-ttu-id="93ea2-138">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="93ea2-138">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="93ea2-139">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="93ea2-139">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
