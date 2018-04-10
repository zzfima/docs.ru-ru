---
title: where (ограничение универсального типа) (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="fbad9-102">where (ограничение универсального типа) (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="fbad9-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="fbad9-103">В определении универсального типа предложение `where` позволяет задать ограничения для типов, которые можно использовать как аргументы для параметра типа, определенных в универсальном объявлении.</span><span class="sxs-lookup"><span data-stu-id="fbad9-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="fbad9-104">Например, можно объявить универсальный класс `MyGenericClass` так, чтобы параметр типа `T` реализовывал интерфейс <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="fbad9-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbad9-105">Дополнительные сведения о предложении where в выражении запроса см. в разделе [Предложение where](../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fbad9-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="fbad9-106">Наряду с ограничениями интерфейса предложение `where` может включать ограничение базового класса, согласно которому тип должен иметь указанный класс как базовый (либо быть таким классом) — только в этом случае его можно будет использовать как аргумент типа для соответствующего универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fbad9-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="fbad9-107">Если такое ограничение используется, оно должно быть указано перед любыми другими ограничениями данного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="fbad9-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 <span data-ttu-id="fbad9-108">Предложение `where` также может включать ограничение конструктора.</span><span class="sxs-lookup"><span data-stu-id="fbad9-108">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="fbad9-109">С помощью оператора new можно создать экземпляр параметра типа, однако для этого параметр типа должен ограничиваться ограничением конструктора `new()`.</span><span class="sxs-lookup"><span data-stu-id="fbad9-109">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="fbad9-110">[Ограничение new()](../../../csharp/language-reference/keywords/new-constraint.md) сообщает компилятору о том, что все предоставленные аргументы типа должны иметь доступный конструктор без параметров (или конструктор по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fbad9-110">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="fbad9-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="fbad9-111">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 <span data-ttu-id="fbad9-112">Ограничение `new()` отображается в предложении `where` последним.</span><span class="sxs-lookup"><span data-stu-id="fbad9-112">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="fbad9-113">Если параметров типа несколько, для каждого из них необходимо использовать по одному предложению `where`, например:</span><span class="sxs-lookup"><span data-stu-id="fbad9-113">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 <span data-ttu-id="fbad9-114">Кроме того, ограничения можно присоединять к параметрам типа универсальных методов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fbad9-114">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="fbad9-115">Обратите внимание на то, что ограничения параметров типа для делегатов имеют такой же синтаксис, как и методы:</span><span class="sxs-lookup"><span data-stu-id="fbad9-115">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="fbad9-116">Дополнительные сведения об универсальных делегатах см. в разделе [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fbad9-116">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="fbad9-117">Дополнительные сведения о синтаксисе и применении ограничений см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fbad9-117">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fbad9-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fbad9-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbad9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fbad9-119">See Also</span></span>  
 [<span data-ttu-id="fbad9-120">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="fbad9-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fbad9-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fbad9-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fbad9-122">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="fbad9-122">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="fbad9-123">Ограничение new</span><span class="sxs-lookup"><span data-stu-id="fbad9-123">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
 [<span data-ttu-id="fbad9-124">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="fbad9-124">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
