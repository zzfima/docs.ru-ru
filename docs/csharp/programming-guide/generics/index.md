---
title: Руководство по программированию на C#. Универсальные шаблоны
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423397"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="f27cb-102">Универсальные шаблоны (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f27cb-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="f27cb-103">Универсальные шаблоны были добавлены в язык C# и общеязыковую среду выполнения (CLR) в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f27cb-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="f27cb-104">Универсальные шаблоны вводят на платформе .NET Framework концепцию параметров универсального типа. Благодаря им вы можете создавать классы и методы с типами, спецификация которых отложена до момента объявления и создания экземпляров в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="f27cb-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="f27cb-105">Как пример, ниже показан класс с параметром T универсального типа. Этот класс может использоваться в другом клиентском коде, не требуя ресурсов и не создавая рисков, связанных с операциями приведения и упаковки-преобразования в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="f27cb-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="f27cb-106">Универсальные классы и методы сочетают такие характеристики, как возможность многократного использования, типобезопасность и эффективность, которые не обеспечивают их неуниверсальные аналоги.</span><span class="sxs-lookup"><span data-stu-id="f27cb-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="f27cb-107">Универсальные типы наиболее часто используются с коллекциями и методами, которые выполняют с ними операции.</span><span class="sxs-lookup"><span data-stu-id="f27cb-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="f27cb-108">Библиотека классов на платформе .NET Framework 2.0 предоставляет новое пространство имен <xref:System.Collections.Generic>, которое содержит несколько новых универсальных классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="f27cb-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="f27cb-109">Во всех приложениях, предназначенных для .NET Framework 2.0 и более поздних версий, рекомендуем использовать новые универсальные классы коллекций вместо старых неуниверсальных аналогов, например <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="f27cb-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="f27cb-110">Дополнительные сведения см. в статье об [универсальных шаблонах в .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="f27cb-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="f27cb-111">Очевидно, вы можете создавать собственные универсальные типы и методы для предоставления собственных типобезопасных и эффективных обобщенных решений и шаблонов разработки.</span><span class="sxs-lookup"><span data-stu-id="f27cb-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="f27cb-112">В следующем примере кода показан простой универсальный класс связанного списка для демонстрационных целей.</span><span class="sxs-lookup"><span data-stu-id="f27cb-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="f27cb-113">(В большинстве случаев следует использовать класс <xref:System.Collections.Generic.List%601>, предоставляемый библиотекой классов .NET Framework, вместо создания собственного.) Параметр типа `T` используется в нескольких расположениях, где обычно используется конкретный тип для указания типа элемента, хранящегося в списке.</span><span class="sxs-lookup"><span data-stu-id="f27cb-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="f27cb-114">Он используется в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f27cb-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="f27cb-115">в качестве типа параметра метода в методе `AddHead`;</span><span class="sxs-lookup"><span data-stu-id="f27cb-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="f27cb-116">в качестве типа возвращаемого значения свойства `Data` во вложенном классе `Node`;</span><span class="sxs-lookup"><span data-stu-id="f27cb-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="f27cb-117">в качестве типа закрытого члена `data` во вложенном классе.</span><span class="sxs-lookup"><span data-stu-id="f27cb-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="f27cb-118">Обратите внимание, что T доступен для вложенного класса `Node`.</span><span class="sxs-lookup"><span data-stu-id="f27cb-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="f27cb-119">Когда экземпляр `GenericList<T>` создается с конкретным типом, например `GenericList<int>`, каждое вхождение `T` будет заменено `int`.</span><span class="sxs-lookup"><span data-stu-id="f27cb-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="f27cb-120">В следующем примере кода показано, как клиентский код использует универсальный класс `GenericList<T>` для создания списка целых чисел.</span><span class="sxs-lookup"><span data-stu-id="f27cb-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="f27cb-121">Просто изменяя тип аргумента, следующий код можно легко изменить для создания списков строк или любого другого пользовательского типа:</span><span class="sxs-lookup"><span data-stu-id="f27cb-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="f27cb-122">Общие сведения об универсальных шаблонах</span><span class="sxs-lookup"><span data-stu-id="f27cb-122">Generics Overview</span></span>  
  
- <span data-ttu-id="f27cb-123">Используйте универсальные типы, чтобы получить максимально широкие возможности многократного использования кода, обеспечения безопасности типов и повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="f27cb-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="f27cb-124">Чаще всего универсальные шаблоны используются для создания классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="f27cb-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="f27cb-125">Библиотека классов .NET Framework содержит несколько новых универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="f27cb-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="f27cb-126">Рекомендуется как можно чаще использовать их вместо таких классов, как <xref:System.Collections.ArrayList> в пространстве имен <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="f27cb-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="f27cb-127">Вы можете создавать собственные универсальные интерфейсы, классы, методы, события и делегаты.</span><span class="sxs-lookup"><span data-stu-id="f27cb-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="f27cb-128">Универсальные классы можно ограничить, чтобы они разрешали доступ к методам только для определенных типов данных.</span><span class="sxs-lookup"><span data-stu-id="f27cb-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="f27cb-129">Сведения о типах, используемых в универсальном типе данных, можно получить во время выполнения с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="f27cb-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f27cb-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f27cb-130">Related Sections</span></span>  
 <span data-ttu-id="f27cb-131">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f27cb-131">For more information:</span></span>  
  
- [<span data-ttu-id="f27cb-132">Параметры универсального типа</span><span class="sxs-lookup"><span data-stu-id="f27cb-132">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [<span data-ttu-id="f27cb-133">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="f27cb-133">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="f27cb-134">Универсальные классы</span><span class="sxs-lookup"><span data-stu-id="f27cb-134">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [<span data-ttu-id="f27cb-135">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f27cb-135">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [<span data-ttu-id="f27cb-136">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="f27cb-136">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [<span data-ttu-id="f27cb-137">Универсальные делегаты</span><span class="sxs-lookup"><span data-stu-id="f27cb-137">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [<span data-ttu-id="f27cb-138">Различия между шаблонами языка C++ и универсальными шаблонами языка C#</span><span class="sxs-lookup"><span data-stu-id="f27cb-138">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="f27cb-139">Универсальные типы и отражение</span><span class="sxs-lookup"><span data-stu-id="f27cb-139">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [<span data-ttu-id="f27cb-140">Универсальные типы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f27cb-140">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f27cb-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f27cb-141">C# Language Specification</span></span>  
 <span data-ttu-id="f27cb-142">Дополнительные сведения см. в [спецификации языка C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="f27cb-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27cb-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f27cb-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="f27cb-144">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f27cb-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f27cb-145">Типы</span><span class="sxs-lookup"><span data-stu-id="f27cb-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="f27cb-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="f27cb-146">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="f27cb-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="f27cb-147">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="f27cb-148">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="f27cb-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
