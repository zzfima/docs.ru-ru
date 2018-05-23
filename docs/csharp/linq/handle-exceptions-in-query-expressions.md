---
title: Обработка исключений в выражениях запросов
description: Практическое руководство по обработке исключений в выражениях запросов.
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 691373fabeb3934ecc454cbc3b36a5f7bf477bee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="06aed-103">Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="06aed-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="06aed-104">В контексте выражения запроса можно вызвать любой метод.</span><span class="sxs-lookup"><span data-stu-id="06aed-104">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="06aed-105">Тем не менее рекомендуется избегать вызова в выражении запроса любого метода, который может создавать побочные эффекты, например изменение содержимого источника данных или создание исключения.</span><span class="sxs-lookup"><span data-stu-id="06aed-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="06aed-106">В этом примере показано, как избежать создания исключений при вызове методов в выражениях запросов без нарушения общих рекомендаций .NET Framework относительно обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="06aed-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="06aed-107">Эти рекомендации гласят, что можно перехватывать определенные исключения, если вы понимаете, почему они будут создаваться в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="06aed-107">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="06aed-108">Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="06aed-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="06aed-109">В последнем примере показано, как обрабатывать случаи, когда необходимо создать исключение во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06aed-110">Пример</span><span class="sxs-lookup"><span data-stu-id="06aed-110">Example</span></span>  

 <span data-ttu-id="06aed-111">В следующем примере показано, как переместить код обработки исключений за пределы выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="06aed-112">Это возможно, только если метод не зависит от переменных, являющихся локальными для запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-112">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="06aed-113">Пример</span><span class="sxs-lookup"><span data-stu-id="06aed-113">Example</span></span> 

 <span data-ttu-id="06aed-114">В некоторых случаях лучшей реакцией на исключение, которое вызывается в запросе, будет немедленное прекращение выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="06aed-115">В следующем примере демонстрируется обработка исключений, которые могут быть созданы из тела запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="06aed-116">Предположим, что `SomeMethodThatMightThrow` потенциально может вызвать исключение, которое требует остановки выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="06aed-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="06aed-117">Обратите внимание, что блок `try` включает цикл `foreach`, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="06aed-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="06aed-118">Это вызвано тем, что цикл `foreach` является точкой, в которой запрос фактически выполняется.</span><span class="sxs-lookup"><span data-stu-id="06aed-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="06aed-119">Дополнительные сведения см. в разделе [Введение в запросы LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="06aed-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="06aed-120">См. также</span><span class="sxs-lookup"><span data-stu-id="06aed-120">See Also</span></span>  
 [<span data-ttu-id="06aed-121">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="06aed-121">LINQ query expressions</span></span>](index.md)
