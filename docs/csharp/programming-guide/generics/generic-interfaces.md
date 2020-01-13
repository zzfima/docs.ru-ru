---
title: Руководство по программированию на C#. Универсальные интерфейсы
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 4cce23da7579e30ecff80b3afb92a5a58795c1bd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712212"
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="28e53-102">Универсальные интерфейсы. (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="28e53-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="28e53-103">Часто требуется определить интерфейсы для универсальных классов коллекций или для универсальных классов, представляющих элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="28e53-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="28e53-104">Для универсальных классов предпочтительнее использовать универсальные интерфейсы, такие как <xref:System.IComparable%601>, вместо <xref:System.IComparable>, поскольку это позволяет избежать выполнения операция упаковки-преобразования и распаковки-преобразования для типов значений.</span><span class="sxs-lookup"><span data-stu-id="28e53-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="28e53-105">В библиотеке классов .NET Framework в пространстве имен <xref:System.Collections.Generic> определяется несколько универсальных интерфейсов для работы с классами коллекций.</span><span class="sxs-lookup"><span data-stu-id="28e53-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="28e53-106">Если интерфейс задан в качестве ограничения для параметра типа, можно использовать только типы, реализующие такой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="28e53-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="28e53-107">В следующем примере кода демонстрируется класс `SortedList<T>`, который является производным от класса `GenericList<T>`.</span><span class="sxs-lookup"><span data-stu-id="28e53-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="28e53-108">Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](./index.md).</span><span class="sxs-lookup"><span data-stu-id="28e53-108">For more information, see [Introduction to Generics](./index.md).</span></span> <span data-ttu-id="28e53-109">`SortedList<T>` добавляет ограничение `where T : IComparable<T>`.</span><span class="sxs-lookup"><span data-stu-id="28e53-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="28e53-110">Это позволяет методу `BubbleSort` в `SortedList<T>` использовать универсальный метод <xref:System.IComparable%601.CompareTo%2A> в отношении элементов списка.</span><span class="sxs-lookup"><span data-stu-id="28e53-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="28e53-111">В этом примере элементы списка относятся к простому классу `Person`, который реализует `IComparable<Person>`.</span><span class="sxs-lookup"><span data-stu-id="28e53-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics2.cs#29)]  
  
 <span data-ttu-id="28e53-112">В качестве ограничений для одного типа можно задать несколько интерфейсов, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="28e53-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#30)]  
  
 <span data-ttu-id="28e53-113">Интерфейс может определять несколько параметров типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="28e53-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#31)]  
  
 <span data-ttu-id="28e53-114">Правила наследования, действующие в отношении классов, также применяются к интерфейсам:</span><span class="sxs-lookup"><span data-stu-id="28e53-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#32)]  
  
 <span data-ttu-id="28e53-115">Универсальные интерфейсы могут наследоваться от неуниверсальных интерфейсов, если универсальный интерфейс является контравариантным (то есть использует в качестве возвращаемого значения только свой параметр типа).</span><span class="sxs-lookup"><span data-stu-id="28e53-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contravariant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="28e53-116">В библиотеке классов .NET Framework <xref:System.Collections.Generic.IEnumerable%601> наследуется от <xref:System.Collections.IEnumerable>, поскольку <xref:System.Collections.Generic.IEnumerable%601> использует `T` только в возвращаемом значении <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> и в методе считывания свойства <xref:System.Collections.Generic.IEnumerator%601.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e53-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="28e53-117">Конкретные классы могут реализовывать закрытые сконструированные интерфейсы, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="28e53-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#33)]  
  
 <span data-ttu-id="28e53-118">Универсальные классы могут реализовывать универсальные интерфейсы или закрытые сконструированные интерфейсы при условии, что в списке параметров класса заданы все аргументы, требуемые интерфейсом, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="28e53-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#34)]  
  
 <span data-ttu-id="28e53-119">Правила, управляющие перегрузкой методов, одинаковы для методов с универсальными классами, структурами или интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="28e53-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="28e53-120">Дополнительные сведения см. в разделе [Универсальные методы](./generic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="28e53-120">For more information, see [Generic Methods](./generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e53-121">См. также</span><span class="sxs-lookup"><span data-stu-id="28e53-121">See also</span></span>

- [<span data-ttu-id="28e53-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="28e53-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="28e53-123">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="28e53-123">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="28e53-124">interface</span><span class="sxs-lookup"><span data-stu-id="28e53-124">interface</span></span>](../../language-reference/keywords/interface.md)
- [<span data-ttu-id="28e53-125">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="28e53-125">Generics</span></span>](../../../standard/generics/index.md)
