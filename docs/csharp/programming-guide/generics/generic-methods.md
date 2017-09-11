---
title: "Универсальные методы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="7bd68-102">Универсальные методы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7bd68-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="7bd68-103">Универсальным называется метод, объявленный с использованием параметров типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="7bd68-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 <span data-ttu-id="7bd68-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-105">В следующем примере кода показан один из способов вызова метода с использованием `int` в качестве аргумента типа:</span><span class="sxs-lookup"><span data-stu-id="7bd68-105">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 <span data-ttu-id="7bd68-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-107">Если опустить аргумент типа, компилятор определит его.</span><span class="sxs-lookup"><span data-stu-id="7bd68-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="7bd68-108">Следующий вызов `Swap` эквивалентен предыдущему:</span><span class="sxs-lookup"><span data-stu-id="7bd68-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 <span data-ttu-id="7bd68-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-110">Для статических методов и методов экземпляра применяются одинаковые правила определения типа.</span><span class="sxs-lookup"><span data-stu-id="7bd68-110">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="7bd68-111">Компилятор может определить параметры типа на основе переданных ему аргументов метода. Определение параметров типа невозможно только для ограничения или возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="7bd68-111">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="7bd68-112">Соответственно, механизм определения типа не работает с методами, не имеющими параметров.</span><span class="sxs-lookup"><span data-stu-id="7bd68-112">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="7bd68-113">Определение типа происходит во время компиляции до того, как компилятор попытается разрешить сигнатуры перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="7bd68-113">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="7bd68-114">Компилятор применяет логику определения типа ко всем универсальным методам с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="7bd68-114">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="7bd68-115">На этапе разрешения перегрузки компилятор включает только те универсальные методы, для которых был успешно определен тип.</span><span class="sxs-lookup"><span data-stu-id="7bd68-115">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="7bd68-116">В универсальном классе методы, не являющиеся универсальными, могут получать доступ к параметрам типа на уровне класса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7bd68-116">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 <span data-ttu-id="7bd68-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-118">Если определить универсальный метод, принимающий те же параметры типа, что и содержащий класс, возникнет предупреждение компилятора CS0693, поскольку в области действия метода предоставленный для внутреннего типа `T` аргумент скрывает аргумент, предоставленный для внешнего типа `T`.</span><span class="sxs-lookup"><span data-stu-id="7bd68-118">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="7bd68-119">Для большей гибкости можно вызывать метод универсального класса с использованием аргументов типа, отличающихся от предоставленных при создании экземпляра класса. В этом случае следует предоставить другой идентификатор для параметра типа метода, как показано в `GenericList2<T>` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7bd68-119">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 <span data-ttu-id="7bd68-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-121">С помощью ограничений можно реализовать специализированные операции в отношении параметров типа в методах.</span><span class="sxs-lookup"><span data-stu-id="7bd68-121">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="7bd68-122">Эта версия `Swap<T>` теперь называется `SwapIfGreater<T>` и может использоваться только с типами, реализующими <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="7bd68-122">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 <span data-ttu-id="7bd68-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span></span>  
  
 <span data-ttu-id="7bd68-124">Универсальные методы могут быть перегружены в нескольких параметрах типа.</span><span class="sxs-lookup"><span data-stu-id="7bd68-124">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="7bd68-125">Например, все представленные ниже методы могут располагаться в одном классе:</span><span class="sxs-lookup"><span data-stu-id="7bd68-125">For example, the following methods can all be located in the same class:</span></span>  
  
 <span data-ttu-id="7bd68-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bd68-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7bd68-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7bd68-127">C# Language Specification</span></span>  
 <span data-ttu-id="7bd68-128">Дополнительные сведения см. в [спецификации языка C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="7bd68-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd68-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7bd68-129">See Also</span></span>  
 <span data-ttu-id="7bd68-130"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="7bd68-130"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="7bd68-131">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7bd68-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7bd68-132">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="7bd68-132">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="7bd68-133">Методы</span><span class="sxs-lookup"><span data-stu-id="7bd68-133">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

