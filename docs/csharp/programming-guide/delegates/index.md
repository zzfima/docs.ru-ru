---
title: Делегаты (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: 9711b3c52f6d28d37e0b0d4d4de2f1be6bb46283
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499542"
---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="91afd-102">Делегаты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="91afd-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="91afd-103">[Делегат](../../../csharp/language-reference/keywords/delegate.md) — это тип, который представляет ссылки на методы с определенным списком параметров и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="91afd-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="91afd-104">При создании экземпляра делегата этот экземпляр можно связать с любым методом с совместимой сигнатурой и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="91afd-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="91afd-105">Метод можно вызвать (активировать) с помощью экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="91afd-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="91afd-106">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="91afd-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="91afd-107">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="91afd-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="91afd-108">При создании пользовательского метода класс (например, элемент управления Windows) может вызывать этот метод при появлении определенного события.</span><span class="sxs-lookup"><span data-stu-id="91afd-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="91afd-109">В следующем примере показано объявление делегата:</span><span class="sxs-lookup"><span data-stu-id="91afd-109">The following example shows a delegate declaration:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="91afd-110">Делегату можно назначить любой метод из любого доступного класса или структуры, соответствующей типу делегата.</span><span class="sxs-lookup"><span data-stu-id="91afd-110">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="91afd-111">Этот метод должен быть статическим методом или методом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91afd-111">The method can be either static or an instance method.</span></span> <span data-ttu-id="91afd-112">Это позволяет программно изменять вызовы метода, а также включать новый код в существующие классы.</span><span class="sxs-lookup"><span data-stu-id="91afd-112">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91afd-113">В контексте перегрузки метода его сигнатура не содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="91afd-113">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="91afd-114">Однако в контексте делегатов сигнатура метода содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="91afd-114">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="91afd-115">Другими словами, метод должен иметь тот же возвращаемый тип, что и делегат.</span><span class="sxs-lookup"><span data-stu-id="91afd-115">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="91afd-116">Благодаря возможности ссылаться на метод как на параметр делегаты идеально подходят для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="91afd-116">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="91afd-117">Например, ссылка на метод, сравнивающий два объекта, может быть передана в качестве аргумента алгоритму сортировки.</span><span class="sxs-lookup"><span data-stu-id="91afd-117">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="91afd-118">Поскольку код сравнения находится в отдельной процедуре, алгоритм сортировки может быть написан более общим способом.</span><span class="sxs-lookup"><span data-stu-id="91afd-118">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="91afd-119">Общие сведения о делегатах</span><span class="sxs-lookup"><span data-stu-id="91afd-119">Delegates Overview</span></span>  
 <span data-ttu-id="91afd-120">Делегаты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="91afd-120">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="91afd-121">Делегаты похожи на указатели функций в C++, но являются типобезопасными.</span><span class="sxs-lookup"><span data-stu-id="91afd-121">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="91afd-122">Делегаты допускают передачу методов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="91afd-122">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="91afd-123">Делегаты можно использовать для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="91afd-123">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="91afd-124">Делегаты можно связывать друг с другом; например, при появлении одного события можно вызывать несколько методов.</span><span class="sxs-lookup"><span data-stu-id="91afd-124">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="91afd-125">Точное соответствие методов типу делегата не требуется.</span><span class="sxs-lookup"><span data-stu-id="91afd-125">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="91afd-126">Дополнительные сведения см. в разделе [Использование вариативности в делегатах](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="91afd-126">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="91afd-127">В C# версии 2.0 введена концепция [анонимных методов](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), которые позволяют передавать блоки кода в виде параметров вместо использования отдельно определенного метода.</span><span class="sxs-lookup"><span data-stu-id="91afd-127">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="91afd-128">В C# 3.0 для краткой записи встроенных блоков кода введены лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="91afd-128">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="91afd-129">В результате компиляции как анонимных методов, так и лямбда-выражений (в определенном контексте) получаются типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="91afd-129">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="91afd-130">В настоящее время эти возможности называются анонимными возможностями.</span><span class="sxs-lookup"><span data-stu-id="91afd-130">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="91afd-131">Дополнительные сведения о лямбда-выражениях см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="91afd-131">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91afd-132">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="91afd-132">In This Section</span></span>  
  
-   [<span data-ttu-id="91afd-133">Использование делегатов</span><span class="sxs-lookup"><span data-stu-id="91afd-133">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="91afd-134">Использование делегатов вместо интерфейсов (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="91afd-134">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](https://msdn.microsoft.com/library/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="91afd-135">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="91afd-135">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="91afd-136">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="91afd-136">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="91afd-137">Использование расхождения в делегатах</span><span class="sxs-lookup"><span data-stu-id="91afd-137">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="91afd-138">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="91afd-138">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="91afd-139">Практическое руководство. Объявление, создание и использование делегата</span><span class="sxs-lookup"><span data-stu-id="91afd-139">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="91afd-140">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="91afd-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="91afd-141">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="91afd-141">Featured Book Chapters</span></span>  
 <span data-ttu-id="91afd-142">[Делегаты, события и лямбда-выражения](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="91afd-142">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="91afd-143">[Делегаты и события](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) в статье [Изучение C# 3.0: овладение основными понятиями C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="91afd-143">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91afd-144">См. также</span><span class="sxs-lookup"><span data-stu-id="91afd-144">See Also</span></span>  
 <xref:System.Delegate>  
 [<span data-ttu-id="91afd-145">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="91afd-145">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="91afd-146">События</span><span class="sxs-lookup"><span data-stu-id="91afd-146">Events</span></span>](../../../csharp/programming-guide/events/index.md)
