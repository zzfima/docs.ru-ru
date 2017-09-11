---
title: "Делегаты (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
caps.latest.revision: 30
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
ms.openlocfilehash: 1d3dc2252b086f9df9e64a059a53ec8792e11b45
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-c-programming-guide"></a><span data-ttu-id="30799-102">Делегаты (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="30799-102">Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="30799-103">[Делегат](../../../csharp/language-reference/keywords/delegate.md) — это тип, который представляет ссылки на методы с определенным списком параметров и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="30799-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) is a type that represents references to methods with a particular parameter list and return type.</span></span> <span data-ttu-id="30799-104">При создании экземпляра делегата этот экземпляр можно связать с любым методом с совместимой сигнатурой и типом возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="30799-104">When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type.</span></span> <span data-ttu-id="30799-105">Метод можно вызвать (активировать) с помощью экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="30799-105">You can invoke (or call) the method through the delegate instance.</span></span>  
  
 <span data-ttu-id="30799-106">Делегаты используются для передачи методов в качестве аргументов к другим методам.</span><span class="sxs-lookup"><span data-stu-id="30799-106">Delegates are used to pass methods as arguments to other methods.</span></span> <span data-ttu-id="30799-107">Обработчики событий — это ничто иное, как методы, вызываемые с помощью делегатов.</span><span class="sxs-lookup"><span data-stu-id="30799-107">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="30799-108">При создании пользовательского метода класс (например, элемент управления Windows) может вызывать этот метод при появлении определенного события.</span><span class="sxs-lookup"><span data-stu-id="30799-108">You create a custom method, and a class such as a windows control can call your method when a certain event occurs.</span></span> <span data-ttu-id="30799-109">В следующем примере показано объявление делегата:</span><span class="sxs-lookup"><span data-stu-id="30799-109">The following example shows a delegate declaration:</span></span>  
  
 <span data-ttu-id="30799-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="30799-110">[!code-cs[csProgGuideDelegates#20](../../../csharp/programming-guide/delegates/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="30799-111">Делегату можно назначить любой метод из любого доступного класса или структуры, соответствующей типу делегата.</span><span class="sxs-lookup"><span data-stu-id="30799-111">Any method from any accessible class or struct that matches the delegate type can be assigned to the delegate.</span></span> <span data-ttu-id="30799-112">Этот метод должен быть статическим методом или методом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="30799-112">The method can be either static or an instance method.</span></span> <span data-ttu-id="30799-113">Это позволяет программно изменять вызовы метода, а также включать новый код в существующие классы.</span><span class="sxs-lookup"><span data-stu-id="30799-113">This makes it possible to programmatically change method calls, and also plug new code into existing classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30799-114">В контексте перегрузки метода его сигнатура не содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="30799-114">In the context of method overloading, the signature of a method does not include the return value.</span></span> <span data-ttu-id="30799-115">Однако в контексте делегатов сигнатура метода содержит возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="30799-115">But in the context of delegates, the signature does include the return value.</span></span> <span data-ttu-id="30799-116">Другими словами, метод должен иметь тот же возвращаемый тип, что и делегат.</span><span class="sxs-lookup"><span data-stu-id="30799-116">In other words, a method must have the same return type as the delegate.</span></span>  
  
 <span data-ttu-id="30799-117">Благодаря возможности ссылаться на метод как на параметр делегаты идеально подходят для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="30799-117">This ability to refer to a method as a parameter makes delegates ideal for defining callback methods.</span></span> <span data-ttu-id="30799-118">Например, ссылка на метод, сравнивающий два объекта, может быть передана в качестве аргумента алгоритму сортировки.</span><span class="sxs-lookup"><span data-stu-id="30799-118">For example, a reference to a method that compares two objects could be passed as an argument to a sort algorithm.</span></span> <span data-ttu-id="30799-119">Поскольку код сравнения находится в отдельной процедуре, алгоритм сортировки может быть написан более общим способом.</span><span class="sxs-lookup"><span data-stu-id="30799-119">Because the comparison code is in a separate procedure, the sort algorithm can be written in a more general way.</span></span>  
  
## <a name="delegates-overview"></a><span data-ttu-id="30799-120">Общие сведения о делегатах</span><span class="sxs-lookup"><span data-stu-id="30799-120">Delegates Overview</span></span>  
 <span data-ttu-id="30799-121">Делегаты имеют следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="30799-121">Delegates have the following properties:</span></span>  
  
-   <span data-ttu-id="30799-122">Делегаты похожи на указатели функций в C++, но являются типобезопасными.</span><span class="sxs-lookup"><span data-stu-id="30799-122">Delegates are like C++ function pointers but are type safe.</span></span>  
  
-   <span data-ttu-id="30799-123">Делегаты допускают передачу методов в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="30799-123">Delegates allow methods to be passed as parameters.</span></span>  
  
-   <span data-ttu-id="30799-124">Делегаты можно использовать для определения методов обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="30799-124">Delegates can be used to define callback methods.</span></span>  
  
-   <span data-ttu-id="30799-125">Делегаты можно связывать друг с другом; например, при появлении одного события можно вызывать несколько методов.</span><span class="sxs-lookup"><span data-stu-id="30799-125">Delegates can be chained together; for example, multiple methods can be called on a single event.</span></span>  
  
-   <span data-ttu-id="30799-126">Точное соответствие методов типу делегата не требуется.</span><span class="sxs-lookup"><span data-stu-id="30799-126">Methods do not have to match the delegate type exactly.</span></span> <span data-ttu-id="30799-127">Дополнительные сведения см. в разделе [Использование вариативности в делегатах](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="30799-127">For more information, see [Using Variance in Delegates](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
-   <span data-ttu-id="30799-128">В C# версии 2.0 введена концепция [анонимных методов](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), которые позволяют передавать блоки кода в виде параметров вместо использования отдельно определенного метода.</span><span class="sxs-lookup"><span data-stu-id="30799-128">C# version 2.0 introduced the concept of [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md), which allow code blocks to be passed as parameters in place of a separately defined method.</span></span> <span data-ttu-id="30799-129">В C# 3.0 для краткой записи встроенных блоков кода введены лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="30799-129">C# 3.0 introduced lambda expressions as a more concise way of writing inline code blocks.</span></span> <span data-ttu-id="30799-130">В результате компиляции как анонимных методов, так и лямбда-выражений (в определенном контексте) получаются типы делегатов.</span><span class="sxs-lookup"><span data-stu-id="30799-130">Both anonymous methods and lambda expressions (in certain contexts) are compiled to delegate types.</span></span> <span data-ttu-id="30799-131">В настоящее время эти возможности называются анонимными возможностями.</span><span class="sxs-lookup"><span data-stu-id="30799-131">Together, these features are now known as anonymous functions.</span></span> <span data-ttu-id="30799-132">Дополнительные сведения о лямбда-выражениях см. в разделе [Анонимные функции](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="30799-132">For more information about lambda expressions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30799-133">Содержание</span><span class="sxs-lookup"><span data-stu-id="30799-133">In This Section</span></span>  
  
-   [<span data-ttu-id="30799-134">Использование делегатов</span><span class="sxs-lookup"><span data-stu-id="30799-134">Using Delegates</span></span>](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
-   [<span data-ttu-id="30799-135">Использование делегатов вместо интерфейсов (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="30799-135">When to Use Delegates Instead of Interfaces (C# Programming Guide)</span></span>](http://msdn.microsoft.com/en-us/2e759bdf-7ca4-4005-8597-af92edf6d8f0)  
  
-   [<span data-ttu-id="30799-136">Делегаты с именованными методами и делегаты с анонимными методами</span><span class="sxs-lookup"><span data-stu-id="30799-136">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
-   [<span data-ttu-id="30799-137">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="30799-137">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
-   [<span data-ttu-id="30799-138">Использование расхождения в делегатах</span><span class="sxs-lookup"><span data-stu-id="30799-138">Using Variance in Delegates</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
-   [<span data-ttu-id="30799-139">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="30799-139">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
-   [<span data-ttu-id="30799-140">Практическое руководство. Объявление, создание и использование делегата</span><span class="sxs-lookup"><span data-stu-id="30799-140">How to: Declare, Instantiate, and Use a Delegate</span></span>](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="30799-141">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="30799-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="30799-142">Главы в популярных книгах</span><span class="sxs-lookup"><span data-stu-id="30799-142">Featured Book Chapters</span></span>  
 <span data-ttu-id="30799-143">[Делегаты, события и лямбда-выражения](http://go.microsoft.com/fwlink/?LinkId=195395) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="30799-143">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="30799-144">[Делегаты и события](http://go.microsoft.com/fwlink/?LinkId=195418) в статье [Изучение C# 3.0: овладение основными понятиями C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="30799-144">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30799-145">См. также</span><span class="sxs-lookup"><span data-stu-id="30799-145">See Also</span></span>  
 <span data-ttu-id="30799-146"><xref:System.Delegate></span><span class="sxs-lookup"><span data-stu-id="30799-146"><xref:System.Delegate></span></span>   
 <span data-ttu-id="30799-147">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="30799-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="30799-148">События</span><span class="sxs-lookup"><span data-stu-id="30799-148">Events</span></span>](../../../csharp/programming-guide/events/index.md)

