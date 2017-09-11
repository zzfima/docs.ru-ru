---
title: "where (ограничение универсального типа) (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="1172d-102">where (ограничение универсального типа) (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1172d-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="1172d-103">В определении универсального типа предложение `where` позволяет задать ограничения для типов, которые можно использовать как аргументы для параметра типа, определенных в универсальном объявлении.</span><span class="sxs-lookup"><span data-stu-id="1172d-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="1172d-104">Например, можно объявить универсальный класс `MyGenericClass` так, чтобы параметр типа `T` реализовывал интерфейс <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="1172d-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="1172d-105">Дополнительные сведения о предложении where в выражении запроса см. в разделе [Предложение where](../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="1172d-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="1172d-106">Наряду с ограничениями интерфейса предложение `where` может включать ограничение базового класса, согласно которому тип должен иметь указанный класс как базовый (либо быть таким классом) — только в этом случае его можно будет использовать как аргумент типа для соответствующего универсального типа.</span><span class="sxs-lookup"><span data-stu-id="1172d-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="1172d-107">Если такое ограничение используется, оно должно быть указано перед любыми другими ограничениями данного параметра типа.</span><span class="sxs-lookup"><span data-stu-id="1172d-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 <span data-ttu-id="1172d-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1172d-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span></span>  
  
 <span data-ttu-id="1172d-109">Предложение `where` также может включать ограничение конструктора.</span><span class="sxs-lookup"><span data-stu-id="1172d-109">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="1172d-110">С помощью оператора new можно создать экземпляр параметра типа, однако для этого параметр типа должен ограничиваться ограничением конструктора `new()`.</span><span class="sxs-lookup"><span data-stu-id="1172d-110">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="1172d-111">[Ограничение new()](../../../csharp/language-reference/keywords/new-constraint.md) сообщает компилятору о том, что все предоставленные аргументы типа должны иметь доступный конструктор без параметров (или конструктор по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1172d-111">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="1172d-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="1172d-112">For example:</span></span>  
  
 <span data-ttu-id="1172d-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1172d-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="1172d-114">Ограничение `new()` отображается в предложении `where` последним.</span><span class="sxs-lookup"><span data-stu-id="1172d-114">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="1172d-115">Если параметров типа несколько, для каждого из них необходимо использовать по одному предложению `where`, например:</span><span class="sxs-lookup"><span data-stu-id="1172d-115">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 <span data-ttu-id="1172d-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1172d-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span></span>  
  
 <span data-ttu-id="1172d-117">Кроме того, ограничения можно присоединять к параметрам типа универсальных методов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1172d-117">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="1172d-118">Обратите внимание на то, что ограничения параметров типа для делегатов имеют такой же синтаксис, как и методы:</span><span class="sxs-lookup"><span data-stu-id="1172d-118">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="1172d-119">Дополнительные сведения об универсальных делегатах см. в разделе [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="1172d-119">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="1172d-120">Дополнительные сведения о синтаксисе и применении ограничений см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1172d-120">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1172d-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1172d-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1172d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1172d-122">See Also</span></span>  
 <span data-ttu-id="1172d-123">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1172d-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1172d-124">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1172d-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1172d-125">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="1172d-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="1172d-126">[Ограничение new](../../../csharp/language-reference/keywords/new-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="1172d-126">[new Constraint](../../../csharp/language-reference/keywords/new-constraint.md) </span></span>  
 [<span data-ttu-id="1172d-127">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="1172d-127">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

