---
title: "Вариативность в универсальных интерфейсах (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40daaa3d008a93ab48d0d74894f60f0baca1d12b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="1fdad-102">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="1fdad-102">Variance in Generic Interfaces (C#)</span></span>
<span data-ttu-id="1fdad-103">В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="1fdad-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="1fdad-104">Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1fdad-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="1fdad-105">Сейчас вариативными являются следующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="1fdad-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="1fdad-106"><xref:System.Collections.Generic.IEnumerable%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="1fdad-107"><xref:System.Collections.Generic.IEnumerator%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="1fdad-108"><xref:System.Linq.IQueryable%601> (T является ковариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="1fdad-109"><xref:System.Linq.IGrouping%602> (`TKey` и `TElement` являются ковариантными)</span><span class="sxs-lookup"><span data-stu-id="1fdad-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="1fdad-110"><xref:System.Collections.Generic.IComparer%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="1fdad-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="1fdad-112"><xref:System.IComparable%601> (T является контравариантным)</span><span class="sxs-lookup"><span data-stu-id="1fdad-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="1fdad-113">Ковариация позволяет методу иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметре универсального типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1fdad-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="1fdad-114">Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable<Object>` и `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="1fdad-115">Интерфейс `IEnumerable<String>` не наследует интерфейс `IEnumerable<Object>`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-115">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="1fdad-116">При этом тип `String` наследует тип `Object`, и в некоторых случаях может потребоваться назначить объекты этих интерфейсов друг другу.</span><span class="sxs-lookup"><span data-stu-id="1fdad-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="1fdad-117">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1fdad-117">This is shown in the following code example.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="1fdad-118">В более ранних версиях .NET Framework этот код приводит к ошибке компиляции в C# в `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-118">In earlier versions of the .NET Framework, this code causes a compilation error in C# with `Option Strict On`.</span></span> <span data-ttu-id="1fdad-119">Но теперь можно использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку интерфейс <xref:System.Collections.Generic.IEnumerable%601> является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="1fdad-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="1fdad-120">Контравариантность позволяет методу иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1fdad-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="1fdad-121">Чтобы продемонстрировать функцию контравариантности, предположим, что создан класса `BaseComparer` для сравнения экземпляров класса `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="1fdad-122">Класс `BaseComparer` реализует интерфейс `IEqualityComparer<BaseClass>`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-122">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="1fdad-123">Поскольку теперь интерфейс <xref:System.Collections.Generic.IEqualityComparer%601> является контравариантным, для сравнения экземпляров классов, наследующих класс `BaseClass`, можно использовать класс `BaseComparer`.</span><span class="sxs-lookup"><span data-stu-id="1fdad-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="1fdad-124">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1fdad-124">This is shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="1fdad-125">Дополнительные примеры см.в разделе [Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="1fdad-125">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="1fdad-126">Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="1fdad-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="1fdad-127">Типы значений не поддерживают вариативность.</span><span class="sxs-lookup"><span data-stu-id="1fdad-127">Value types do not support variance.</span></span> <span data-ttu-id="1fdad-128">Например, `IEnumerable<int>` нельзя неявно преобразовать в `IEnumerable<object>`, так как типом значения является integer.</span><span class="sxs-lookup"><span data-stu-id="1fdad-128">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 <span data-ttu-id="1fdad-129">Кроме того, важно помнить, что классы, которые реализуют вариативные интерфейсы, сами являются инвариантными.</span><span class="sxs-lookup"><span data-stu-id="1fdad-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="1fdad-130">Например, несмотря на то, что <xref:System.Collections.Generic.List%601> реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, неявно преобразовать `List<Object>` в `List<String>` нельзя.</span><span class="sxs-lookup"><span data-stu-id="1fdad-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="1fdad-131">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="1fdad-131">This is illustrated in the following code example.</span></span>  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fdad-132">См. также</span><span class="sxs-lookup"><span data-stu-id="1fdad-132">See Also</span></span>  
 <span data-ttu-id="1fdad-133">[Использование вариативности в интерфейсах для универсальных коллекций (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="1fdad-133">[Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
 <span data-ttu-id="1fdad-134">[Создание вариативных универсальных интерфейсов (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="1fdad-134">[Creating Variant Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
 <span data-ttu-id="1fdad-135">[Универсальные интерфейсы](../../../../standard/generics/interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="1fdad-135">[Generic Interfaces](../../../../standard/generics/interfaces.md) </span></span>  
 [<span data-ttu-id="1fdad-136">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="1fdad-136">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)

