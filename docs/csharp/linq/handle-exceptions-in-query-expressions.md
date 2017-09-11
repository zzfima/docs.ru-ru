---
title: "Обработка исключений в выражениях запросов"
description: "Практическое руководство по обработке исключений в выражениях запросов."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9ce4a4ca62bb476b2414ec8b93d5633faca53b59
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="54ed2-104">Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="54ed2-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="54ed2-105">В контексте выражения запроса можно вызвать любой метод.</span><span class="sxs-lookup"><span data-stu-id="54ed2-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="54ed2-106">Тем не менее рекомендуется избегать вызова в выражении запроса любого метода, который может создавать побочные эффекты, например изменение содержимого источника данных или создание исключения.</span><span class="sxs-lookup"><span data-stu-id="54ed2-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="54ed2-107">В этом примере показано, как избежать создания исключений при вызове методов в выражениях запросов без нарушения общих рекомендаций .NET Framework относительно обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="54ed2-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="54ed2-108">Эти рекомендации гласят, что можно перехватывать определенные исключения, если вы понимаете, почему они будут создаваться в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="54ed2-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="54ed2-109">Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="54ed2-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="54ed2-110">В последнем примере показано, как обрабатывать случаи, когда необходимо создать исключение во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ed2-111">Пример</span><span class="sxs-lookup"><span data-stu-id="54ed2-111">Example</span></span>  

 <span data-ttu-id="54ed2-112">В следующем примере показано, как переместить код обработки исключений за пределы выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="54ed2-113">Это возможно, только если метод не зависит от переменных, являющихся локальными для запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 <span data-ttu-id="54ed2-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="54ed2-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ed2-115">Пример</span><span class="sxs-lookup"><span data-stu-id="54ed2-115">Example</span></span> 

 <span data-ttu-id="54ed2-116">В некоторых случаях лучшей реакцией на исключение, которое вызывается в запросе, будет немедленное прекращение выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-116">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="54ed2-117">В следующем примере демонстрируется обработка исключений, которые могут быть созданы из тела запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-117">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="54ed2-118">Предположим, что `SomeMethodThatMightThrow` потенциально может вызвать исключение, которое требует остановки выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="54ed2-118">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="54ed2-119">Обратите внимание, что блок `try` включает цикл `foreach`, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="54ed2-119">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="54ed2-120">Это вызвано тем, что цикл `foreach` является точкой, в которой запрос фактически выполняется.</span><span class="sxs-lookup"><span data-stu-id="54ed2-120">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="54ed2-121">Дополнительные сведения см. в разделе [Введение в запросы LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="54ed2-121">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="54ed2-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="54ed2-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="54ed2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="54ed2-123">See Also</span></span>  
 [<span data-ttu-id="54ed2-124">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="54ed2-124">LINQ query expressions</span></span>](index.md)

