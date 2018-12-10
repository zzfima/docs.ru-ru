---
title: Универсальные шаблоны (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 9aa57fd31b8d969bbbbf4329a028007f42d3e097
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129835"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="f1a1c-102">Универсальные шаблоны (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f1a1c-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="f1a1c-103">Универсальные шаблоны были добавлены в язык C# и общеязыковую среду выполнения (CLR) в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="f1a1c-104">Универсальные шаблоны вводят на платформе .NET Framework концепцию параметров универсального типа. Благодаря им вы можете создавать классы и методы с типами, спецификация которых отложена до момента объявления и создания экземпляров в клиентском коде.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="f1a1c-105">Как пример, ниже показан класс с параметром T универсального типа. Этот класс может использоваться в другом клиентском коде, не требуя ресурсов и не создавая рисков, связанных с операциями приведения и упаковки-преобразования в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## <a name="generics-overview"></a><span data-ttu-id="f1a1c-106">Общие сведения об универсальных шаблонах</span><span class="sxs-lookup"><span data-stu-id="f1a1c-106">Generics Overview</span></span>  
  
-   <span data-ttu-id="f1a1c-107">Используйте универсальные типы, чтобы получить максимально широкие возможности многократного использования кода, обеспечения безопасности типов и повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-107">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="f1a1c-108">Чаще всего универсальные шаблоны используются для создания классов коллекций.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-108">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="f1a1c-109">Библиотека классов .NET Framework содержит несколько новых универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-109">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="f1a1c-110">Рекомендуется как можно чаще использовать их вместо таких классов, как <xref:System.Collections.ArrayList> в пространстве имен <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-110">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="f1a1c-111">Вы можете создавать собственные универсальные интерфейсы, классы, методы, события и делегаты.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-111">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="f1a1c-112">Универсальные классы можно ограничить, чтобы они разрешали доступ к методам только для определенных типов данных.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-112">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="f1a1c-113">Сведения о типах, используемых в универсальном типе данных, можно получить во время выполнения с помощью отражения.</span><span class="sxs-lookup"><span data-stu-id="f1a1c-113">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f1a1c-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f1a1c-114">Related Sections</span></span>  
 <span data-ttu-id="f1a1c-115">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="f1a1c-115">For more information:</span></span>  
  
-   [<span data-ttu-id="f1a1c-116">Введение в универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="f1a1c-116">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="f1a1c-117">Преимущества универсальных шаблонов</span><span class="sxs-lookup"><span data-stu-id="f1a1c-117">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="f1a1c-118">Параметры универсального типа</span><span class="sxs-lookup"><span data-stu-id="f1a1c-118">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="f1a1c-119">Ограничения параметров типа</span><span class="sxs-lookup"><span data-stu-id="f1a1c-119">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="f1a1c-120">Универсальные классы</span><span class="sxs-lookup"><span data-stu-id="f1a1c-120">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="f1a1c-121">Универсальные интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f1a1c-121">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="f1a1c-122">Универсальные методы</span><span class="sxs-lookup"><span data-stu-id="f1a1c-122">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="f1a1c-123">Универсальные делегаты</span><span class="sxs-lookup"><span data-stu-id="f1a1c-123">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="f1a1c-124">Различия между шаблонами языка C++ и универсальными шаблонами языка C#</span><span class="sxs-lookup"><span data-stu-id="f1a1c-124">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="f1a1c-125">Универсальные типы и отражение</span><span class="sxs-lookup"><span data-stu-id="f1a1c-125">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="f1a1c-126">Универсальные типы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f1a1c-126">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f1a1c-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f1a1c-127">C# Language Specification</span></span>  
 <span data-ttu-id="f1a1c-128">Дополнительные сведения см. в [спецификации языка C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="f1a1c-128">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a1c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a1c-129">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="f1a1c-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f1a1c-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f1a1c-131">Типы</span><span class="sxs-lookup"><span data-stu-id="f1a1c-131">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
- [<span data-ttu-id="f1a1c-132">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="f1a1c-132">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)  
- [<span data-ttu-id="f1a1c-133">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="f1a1c-133">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)  
- [<span data-ttu-id="f1a1c-134">Универсальные шаблоны в .NET</span><span class="sxs-lookup"><span data-stu-id="f1a1c-134">Generics in .NET</span></span>](../../../standard/generics/index.md)  