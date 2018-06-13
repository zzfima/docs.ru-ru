---
title: Универсальные методы (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
ms.openlocfilehash: 04bc59d41eb7883e08138382b396bc737c7f11bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329872"
---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="b0f9b-102">Универсальные методы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b0f9b-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="b0f9b-103">Универсальным называется метод, объявленный с использованием параметров типа, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="b0f9b-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]  
  
 <span data-ttu-id="b0f9b-104">В следующем примере кода показан один из способов вызова метода с использованием `int` в качестве аргумента типа:</span><span class="sxs-lookup"><span data-stu-id="b0f9b-104">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]  
  
 <span data-ttu-id="b0f9b-105">Если опустить аргумент типа, компилятор определит его.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-105">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="b0f9b-106">Следующий вызов `Swap` эквивалентен предыдущему:</span><span class="sxs-lookup"><span data-stu-id="b0f9b-106">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]  
  
 <span data-ttu-id="b0f9b-107">Для статических методов и методов экземпляра применяются одинаковые правила определения типа.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-107">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="b0f9b-108">Компилятор может определить параметры типа на основе переданных ему аргументов метода. Определение параметров типа невозможно только для ограничения или возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-108">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="b0f9b-109">Соответственно, механизм определения типа не работает с методами, не имеющими параметров.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-109">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="b0f9b-110">Определение типа происходит во время компиляции до того, как компилятор попытается разрешить сигнатуры перегруженных методов.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-110">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="b0f9b-111">Компилятор применяет логику определения типа ко всем универсальным методам с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-111">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="b0f9b-112">На этапе разрешения перегрузки компилятор включает только те универсальные методы, для которых был успешно определен тип.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-112">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="b0f9b-113">В универсальном классе методы, не являющиеся универсальными, могут получать доступ к параметрам типа на уровне класса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b0f9b-113">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]  
  
 <span data-ttu-id="b0f9b-114">Если определить универсальный метод, принимающий те же параметры типа, что и содержащий класс, возникнет предупреждение компилятора CS0693, поскольку в области действия метода предоставленный для внутреннего типа `T` аргумент скрывает аргумент, предоставленный для внешнего типа `T`.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-114">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="b0f9b-115">Для большей гибкости можно вызывать метод универсального класса с использованием аргументов типа, отличающихся от предоставленных при создании экземпляра класса. В этом случае следует предоставить другой идентификатор для параметра типа метода, как показано в `GenericList2<T>` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-115">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]  
  
 <span data-ttu-id="b0f9b-116">С помощью ограничений можно реализовать специализированные операции в отношении параметров типа в методах.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-116">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="b0f9b-117">Эта версия `Swap<T>` теперь называется `SwapIfGreater<T>` и может использоваться только с типами, реализующими <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-117">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]  
  
 <span data-ttu-id="b0f9b-118">Универсальные методы могут быть перегружены в нескольких параметрах типа.</span><span class="sxs-lookup"><span data-stu-id="b0f9b-118">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="b0f9b-119">Например, все представленные ниже методы могут располагаться в одном классе:</span><span class="sxs-lookup"><span data-stu-id="b0f9b-119">For example, the following methods can all be located in the same class:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b0f9b-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b0f9b-120">C# Language Specification</span></span>  
 <span data-ttu-id="b0f9b-121">Дополнительные сведения см. в [спецификации языка C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b0f9b-121">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f9b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b0f9b-122">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="b0f9b-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b0f9b-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0f9b-124">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="b0f9b-124">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="b0f9b-125">Методы</span><span class="sxs-lookup"><span data-stu-id="b0f9b-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
