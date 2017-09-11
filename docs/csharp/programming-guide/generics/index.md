---
title: "Универсальные шаблоны (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
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
ms.sourcegitcommit: 1e548df4de2c07934313311a7ffcfae82be76000
ms.openlocfilehash: de81058173b0985577474e8601aa84d4e83336a5
ms.contentlocale: ru-ru
ms.lasthandoff: 08/29/2017

---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="703f1-102">Универсальные шаблоны (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="703f1-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="703f1-103">Универсальные шаблоны были добавлены в язык C# и общеязыковую среду выполнения (CLR) в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="703f1-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="703f1-104">Универсальные шаблоны вводят на платформе .NET Framework концепцию параметров универсального типа. Благодаря им вы можете создавать классы и методы с типами, спецификация которых отложена до момента объявления и создания экземпляров в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="703f1-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="703f1-105">Как пример, ниже показан класс с параметром T универсального типа. Этот класс может использоваться в другом клиентском коде, не требуя ресурсов и не создавая рисков, связанных с операциями приведения и упаковки-преобразования в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="703f1-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 <span data-ttu-id="703f1-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="703f1-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="generics-overview"></a><span data-ttu-id="703f1-107">Общие сведения об универсальных шаблонах</span><span class="sxs-lookup"><span data-stu-id="703f1-107">Generics Overview</span></span>  
  
-   <span data-ttu-id="703f1-108">Используйте универсальные типы, чтобы получить максимально широкие возможности многократного использования кода, обеспечения безопасности типов и повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="703f1-108">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="703f1-109">Чаще всего универсальные шаблоны используются для создания классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="703f1-109">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="703f1-110">Библиотека классов .NET Framework содержит несколько новых универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="703f1-110">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="703f1-111">Рекомендуется как можно чаще использовать их вместо таких классов, как <xref:System.Collections.ArrayList> в пространстве имен <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="703f1-111">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="703f1-112">Вы можете создавать собственные универсальные интерфейсы, классы, методы, события и делегаты.</span><span class="sxs-lookup"><span data-stu-id="703f1-112">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="703f1-113">Универсальные классы можно ограничить, чтобы они разрешали доступ к методам только для определенных типов данных.</span><span class="sxs-lookup"><span data-stu-id="703f1-113">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="703f1-114">Сведения о типах, используемых в универсальном типе данных, можно получить во время выполнения с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="703f1-114">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="703f1-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="703f1-115">Related Sections</span></span>  
 <span data-ttu-id="703f1-116">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="703f1-116">For more information:</span></span>  
  
-   [<span data-ttu-id="703f1-117">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="703f1-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="703f1-118">Преимущества универсальных шаблонов</span><span class="sxs-lookup"><span data-stu-id="703f1-118">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="703f1-119">Параметры универсального типа</span><span class="sxs-lookup"><span data-stu-id="703f1-119">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="703f1-120">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="703f1-120">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="703f1-121">Универсальные классы</span><span class="sxs-lookup"><span data-stu-id="703f1-121">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="703f1-122">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="703f1-122">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="703f1-123">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="703f1-123">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="703f1-124">Универсальные делегаты</span><span class="sxs-lookup"><span data-stu-id="703f1-124">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="703f1-125">Различия между шаблонами языка C++ и универсальными шаблонами языка C#</span><span class="sxs-lookup"><span data-stu-id="703f1-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="703f1-126">Универсальные типы и отражение</span><span class="sxs-lookup"><span data-stu-id="703f1-126">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="703f1-127">Универсальные типы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="703f1-127">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [<span data-ttu-id="703f1-128">Универсальные шаблоны в библиотеке классов платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="703f1-128">Generics in the .NET Framework Class Library</span></span>](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="703f1-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="703f1-129">C# Language Specification</span></span>  
 <span data-ttu-id="703f1-130">Дополнительные сведения см. в [спецификации языка C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="703f1-130">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703f1-131">См. также</span><span class="sxs-lookup"><span data-stu-id="703f1-131">See Also</span></span>  
 <span data-ttu-id="703f1-132"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="703f1-132"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="703f1-133">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="703f1-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="703f1-134">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="703f1-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="703f1-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span><span class="sxs-lookup"><span data-stu-id="703f1-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span></span>  
 [<span data-ttu-id="703f1-136">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="703f1-136">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)

