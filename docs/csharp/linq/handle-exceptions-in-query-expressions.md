---
title: Обработка исключений в выражениях запросов (LINQ в C#)
description: Узнайте, как обрабатывать исключения в выражениях запросов LINQ в C#.
ms.date: 12/01/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: f900669412026e69598d3939c51ff8208b51b7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688505"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="d74d6-103">Обработка исключений в выражениях запросов</span><span class="sxs-lookup"><span data-stu-id="d74d6-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="d74d6-104">В контексте выражения запроса можно вызвать любой метод.</span><span class="sxs-lookup"><span data-stu-id="d74d6-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="d74d6-105">Тем не менее рекомендуется избегать вызова в выражении запроса любого метода, который может создавать побочные эффекты, например изменение содержимого источника данных или создание исключения.</span><span class="sxs-lookup"><span data-stu-id="d74d6-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="d74d6-106">В этом примере показано, как избежать создания исключений при вызове методов в выражениях запросов без нарушения общих рекомендаций .NET относительно обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="d74d6-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="d74d6-107">Эти рекомендации гласят, что можно перехватывать определенные исключения, если вы понимаете, почему они создаются в данном контексте.</span><span class="sxs-lookup"><span data-stu-id="d74d6-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="d74d6-108">Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="d74d6-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="d74d6-109">В последнем примере показано, как обрабатывать случаи, когда необходимо создать исключение во время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="d74d6-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d74d6-110">Example</span></span>

<span data-ttu-id="d74d6-111">В следующем примере показано, как переместить код обработки исключений за пределы выражения запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="d74d6-112">Это возможно, только если метод не зависит от переменных, являющихся локальными для запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="d74d6-113">Пример</span><span class="sxs-lookup"><span data-stu-id="d74d6-113">Example</span></span>

<span data-ttu-id="d74d6-114">В некоторых случаях лучшей реакцией на исключение, которое вызывается в запросе, будет немедленное прекращение выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="d74d6-115">В следующем примере демонстрируется обработка исключений, которые могут быть созданы из тела запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="d74d6-116">Предположим, что `SomeMethodThatMightThrow` потенциально может вызвать исключение, которое требует остановки выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="d74d6-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="d74d6-117">Обратите внимание, что блок `try` включает цикл `foreach`, а не сам запрос.</span><span class="sxs-lookup"><span data-stu-id="d74d6-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="d74d6-118">Это вызвано тем, что цикл `foreach` является точкой, в которой запрос фактически выполняется.</span><span class="sxs-lookup"><span data-stu-id="d74d6-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="d74d6-119">Дополнительные сведения см. в разделе [Введение в запросы LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d74d6-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="d74d6-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d74d6-120">See also</span></span>

- [<span data-ttu-id="d74d6-121">LINQ</span><span class="sxs-lookup"><span data-stu-id="d74d6-121">Language Integrated Query (LINQ)</span></span>](index.md)
