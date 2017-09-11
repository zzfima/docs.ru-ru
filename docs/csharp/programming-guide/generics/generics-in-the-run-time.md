---
title: "Универсальные типы во время выполнения (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 18
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
ms.openlocfilehash: 661dff2d8ec2e12ab6a459660a5378f74e93b9c5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="generics-in-the-run-time-c-programming-guide"></a><span data-ttu-id="3c445-102">Универсальные типы во время выполнения (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="3c445-102">Generics in the Run Time (C# Programming Guide)</span></span>
<span data-ttu-id="3c445-103">Универсальный тип или метод, компилируемый на языке MSIL, будет содержать метаданные, определяющие наличие в нем параметров типа.</span><span class="sxs-lookup"><span data-stu-id="3c445-103">When a generic type or method is compiled into Microsoft intermediate language (MSIL), it contains metadata that identifies it as having type parameters.</span></span> <span data-ttu-id="3c445-104">Способ использования MSIL для универсального типа зависит от того, является ли предоставленный параметр типа ссылочным типом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="3c445-104">How the MSIL for a generic type is used differs based on whether the supplied type parameter is a value type or reference type.</span></span>  
  
 <span data-ttu-id="3c445-105">Если в качестве параметра при первом построении универсального типа использовался тип значения, во время выполнения создается специальный универсальный тип, для которого в соответствующих местах кода MSIL заменяются предоставленные параметры.</span><span class="sxs-lookup"><span data-stu-id="3c445-105">When a generic type is first constructed with a value type as a parameter, the runtime creates a specialized generic type with the supplied parameter or parameters substituted in the appropriate locations in the MSIL.</span></span> <span data-ttu-id="3c445-106">Специальные универсальные типы создаются один раз для каждого уникального типа значения, используемого в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="3c445-106">Specialized generic types are created one time for each unique value type that is used as a parameter.</span></span>  
  
 <span data-ttu-id="3c445-107">Допустим, в коде программы объявляется стек, состоящий из целых чисел:</span><span class="sxs-lookup"><span data-stu-id="3c445-107">For example, suppose your program code declared a stack that is constructed of integers:</span></span>  
  
 <span data-ttu-id="3c445-108">[!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-108">[!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]</span></span>  
  
 <span data-ttu-id="3c445-109">В этой точке среда выполнения создает специальную версию класса <xref:System.Collections.Generic.Stack%601>, параметр которого будет соответствующим образом заменяться целым числом.</span><span class="sxs-lookup"><span data-stu-id="3c445-109">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that has the integer substituted appropriately for its parameter.</span></span> <span data-ttu-id="3c445-110">После этого каждый раз, когда в коде программы используется стек целых чисел, среда выполнения обращается к созданному специальному классу <xref:System.Collections.Generic.Stack%601>.</span><span class="sxs-lookup"><span data-stu-id="3c445-110">Now, whenever your program code uses a stack of integers, the runtime reuses the generated specialized <xref:System.Collections.Generic.Stack%601> class.</span></span> <span data-ttu-id="3c445-111">В следующем примере создаются два экземпляра стека целых чисел, которые совместно используют один экземпляр кода `Stack<int>`:</span><span class="sxs-lookup"><span data-stu-id="3c445-111">In the following example, two instances of a stack of integers are created, and they share a single instance of the `Stack<int>` code:</span></span>  
  
 <span data-ttu-id="3c445-112">[!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-112">[!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]</span></span>  
  
 <span data-ttu-id="3c445-113">Допустим, в другой точке кода создается другой класс <xref:System.Collections.Generic.Stack%601>, в качестве параметра которого используется другой тип значения, например `long`, или определяемая пользователем структура.</span><span class="sxs-lookup"><span data-stu-id="3c445-113">However, suppose that another <xref:System.Collections.Generic.Stack%601> class with a different value type such as a `long` or a user-defined structure as its parameter is created at another point in your code.</span></span> <span data-ttu-id="3c445-114">В результате среда выполнения создает другую версию универсального типа и заменяет `long` в соответствующих местах кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="3c445-114">As a result, the runtime generates another version of the generic type and substitutes a `long` in the appropriate locations in MSIL.</span></span> <span data-ttu-id="3c445-115">Преобразования больше не требуются, поскольку каждый специальный универсальный класс содержит собственный тип значения.</span><span class="sxs-lookup"><span data-stu-id="3c445-115">Conversions are no longer necessary because each specialized generic class natively contains the value type.</span></span>  
  
 <span data-ttu-id="3c445-116">Для ссылочных типов универсальные шаблоны применяются несколько иным образом.</span><span class="sxs-lookup"><span data-stu-id="3c445-116">Generics work somewhat differently for reference types.</span></span> <span data-ttu-id="3c445-117">При первом создании универсального типа с любым ссылочным типом среда выполнения создает в коде MSIL специальный универсальный тип, параметры которого заменяются ссылками на объекты.</span><span class="sxs-lookup"><span data-stu-id="3c445-117">The first time a generic type is constructed with any reference type, the runtime creates a specialized generic type with object references substituted for the parameters in the MSIL.</span></span> <span data-ttu-id="3c445-118">После этого каждый раз при создании экземпляра такого сконструированного типа с использованием в качестве параметра ссылочного типа (независимо от того, какой это тип) среда выполнения использует ранее созданную специальную версию универсального типа.</span><span class="sxs-lookup"><span data-stu-id="3c445-118">Then, every time that a constructed type is instantiated with a reference type as its parameter, regardless of what type it is, the runtime reuses the previously created specialized version of the generic type.</span></span> <span data-ttu-id="3c445-119">Это возможно, поскольку все ссылки имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="3c445-119">This is possible because all references are the same size.</span></span>  
  
 <span data-ttu-id="3c445-120">Допустим, у вас есть два ссылочных типа (классы `Customer` и `Order`) и вы создаете стек типов `Customer`:</span><span class="sxs-lookup"><span data-stu-id="3c445-120">For example, suppose you had two reference types, a `Customer` class and an `Order` class, and also suppose that you created a stack of `Customer` types:</span></span>  
  
 <span data-ttu-id="3c445-121">[!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-121">[!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]</span></span>  
  
 <span data-ttu-id="3c445-122">[!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-122">[!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]</span></span>  
  
 <span data-ttu-id="3c445-123">В этой точке среда выполнения создает специальную версию класса <xref:System.Collections.Generic.Stack%601>, содержащую ссылки на объекты, которые не хранят данные и будут заполнены позднее.</span><span class="sxs-lookup"><span data-stu-id="3c445-123">At this point, the runtime generates a specialized version of the <xref:System.Collections.Generic.Stack%601> class that stores object references that will be filled in later instead of storing data.</span></span> <span data-ttu-id="3c445-124">Допустим, в следующей строке кода создается стек другого ссылочного типа с именем `Order`:</span><span class="sxs-lookup"><span data-stu-id="3c445-124">Suppose the next line of code creates a stack of another reference type, which is named `Order`:</span></span>  
  
 <span data-ttu-id="3c445-125">[!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-125">[!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]</span></span>  
  
 <span data-ttu-id="3c445-126">В отличие от типов значений, в этом случае не создается другая специальная версия класса <xref:System.Collections.Generic.Stack%601> для типа `Order`.</span><span class="sxs-lookup"><span data-stu-id="3c445-126">Unlike with value types, another specialized version of the <xref:System.Collections.Generic.Stack%601> class is not created for the `Order` type.</span></span> <span data-ttu-id="3c445-127">Вместо этого создается экземпляр специальной версии класса <xref:System.Collections.Generic.Stack%601> и задается переменная `orders`, ссылающаяся на него.</span><span class="sxs-lookup"><span data-stu-id="3c445-127">Instead, an instance of the specialized version of the <xref:System.Collections.Generic.Stack%601> class is created and the `orders` variable is set to reference it.</span></span> <span data-ttu-id="3c445-128">Предположим, далее встречается строка кода, в которой создается стек типа `Customer`:</span><span class="sxs-lookup"><span data-stu-id="3c445-128">Suppose that you then encountered a line of code to create a stack of a `Customer` type:</span></span>  
  
 <span data-ttu-id="3c445-129">[!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="3c445-129">[!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]</span></span>  
  
 <span data-ttu-id="3c445-130">Как и в случае предшествующего использования класса <xref:System.Collections.Generic.Stack%601>, созданного с помощью типа `Order`, создается другой специальный экземпляр класса <xref:System.Collections.Generic.Stack%601>.</span><span class="sxs-lookup"><span data-stu-id="3c445-130">As with the previous use of the <xref:System.Collections.Generic.Stack%601> class created by using the `Order` type, another instance of the specialized <xref:System.Collections.Generic.Stack%601> class is created.</span></span> <span data-ttu-id="3c445-131">Содержащиеся в нем указатели будут ссылаться на область памяти с размером типа `Customer`.</span><span class="sxs-lookup"><span data-stu-id="3c445-131">The pointers that are contained therein are set to reference an area of memory the size of a `Customer` type.</span></span> <span data-ttu-id="3c445-132">Поскольку число ссылок в разных программах может значительно различаться, реализация C# на основе универсальных шаблонов позволяет значительно сократить объем кода за счет того, что компилятор создает для универсальных классов ссылочных типов только один специальный класс.</span><span class="sxs-lookup"><span data-stu-id="3c445-132">Because the number of reference types can vary wildly from program to program, the C# implementation of generics greatly reduces the amount of code by reducing to one the number of specialized classes created by the compiler for generic classes of reference types.</span></span>  
  
 <span data-ttu-id="3c445-133">Кроме того, при создании экземпляра универсального класса C# с использованием параметра типа значения или ссылочного типа копия может выполнять запросы к нему во время выполнения, и при этом могут быть установлены его фактический тип и параметр типа.</span><span class="sxs-lookup"><span data-stu-id="3c445-133">Moreover, when a generic C# class is instantiated by using a value type or reference type parameter, reflection can query it at runtime and both its actual type and its type parameter can be ascertained.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c445-134">См. также</span><span class="sxs-lookup"><span data-stu-id="3c445-134">See Also</span></span>  
 <span data-ttu-id="3c445-135"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="3c445-135"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="3c445-136">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c445-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3c445-137">[Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="3c445-137">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="3c445-138">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="3c445-138">Generics</span></span>](~/docs/standard/generics/index.md)

