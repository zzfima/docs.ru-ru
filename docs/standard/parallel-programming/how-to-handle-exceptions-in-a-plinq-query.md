---
title: Практическое руководство. Обработка исключений в запросе PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: 3645f5dc470ef53710aa7f4c78c60431fb27ecfa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123095"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a><span data-ttu-id="0550a-102">Практическое руководство. Обработка исключений в запросе PLINQ</span><span class="sxs-lookup"><span data-stu-id="0550a-102">How to: Handle Exceptions in a PLINQ Query</span></span>

<span data-ttu-id="0550a-103">В первом примере в этой статье показано, как правильно обрабатывать исключение <xref:System.AggregateException?displayProperty=nameWithType>, создаваемое при выполнении запроса PLINQ.</span><span class="sxs-lookup"><span data-stu-id="0550a-103">The first example in this topic shows how to handle the <xref:System.AggregateException?displayProperty=nameWithType> that can be thrown from a PLINQ query when it executes.</span></span> <span data-ttu-id="0550a-104">Во втором примере показано, как разместить блоки try-catch в делегатах, то есть максимально близко к точке, в которой будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="0550a-104">The second example shows how to put try-catch blocks within delegates, as close as possible to where the exception will be thrown.</span></span> <span data-ttu-id="0550a-105">Этот подход позволит перехватить исключение сразу после создания, и при удачных обстоятельствах продолжить выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="0550a-105">In this way, you can catch them as soon as they occur and possibly continue query execution.</span></span> <span data-ttu-id="0550a-106">Если исключения могут всплывать обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.</span><span class="sxs-lookup"><span data-stu-id="0550a-106">When exceptions are allowed to bubble up back to the joining thread, then it is possible that a query may continue to process some items after the exception is raised.</span></span>

<span data-ttu-id="0550a-107">В некоторых случаях, когда PLINQ прибегает к последовательному выполнению, возникающие исключения могут распространяться напрямую, без оболочки <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="0550a-107">In some cases when PLINQ falls back to sequential execution, and an exception occurs, the exception may be propagated directly, and not wrapped in an <xref:System.AggregateException>.</span></span> <span data-ttu-id="0550a-108">Кроме того, <xref:System.Threading.ThreadAbortException> всегда распространяются напрямую.</span><span class="sxs-lookup"><span data-stu-id="0550a-108">Also, <xref:System.Threading.ThreadAbortException>s are always propagated directly.</span></span>

> [!NOTE]
> <span data-ttu-id="0550a-109">Если включен режим "Только мой код", Visual Studio прерывает выполнение программы на той строке, в которой создается исключение, и выводит сообщение об ошибке "Exception not handled by user code" (Исключение, не обработанное пользовательским кодом).</span><span class="sxs-lookup"><span data-stu-id="0550a-109">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="0550a-110">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="0550a-110">This error is benign.</span></span> <span data-ttu-id="0550a-111">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="0550a-111">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="0550a-112">Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.</span><span class="sxs-lookup"><span data-stu-id="0550a-112">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="0550a-113">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="0550a-113">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="0550a-114">Дополнительные сведения см. в статье [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="0550a-114">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="0550a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="0550a-115">Example</span></span>

<span data-ttu-id="0550a-116">В этом примере показано, как поместить блоки try-catch вокруг кода выполнения запроса, чтобы перехватить все создаваемые <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0550a-116">This example shows how to put the try-catch blocks around the code that executes the query to catch any <xref:System.AggregateException?displayProperty=nameWithType>s that are thrown.</span></span>

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

<span data-ttu-id="0550a-117">Код в этом примере не позволяет обрабатывать запрос после создания исключения.</span><span class="sxs-lookup"><span data-stu-id="0550a-117">In this example, the query cannot continue after the exception is thrown.</span></span> <span data-ttu-id="0550a-118">К тому моменту, когда код приложения перехватит исключение, PLINQ уже остановит запрос во всех потоках.</span><span class="sxs-lookup"><span data-stu-id="0550a-118">By the time your application code catches the exception, PLINQ has already stopped the query on all threads.</span></span>

## <a name="example"></a><span data-ttu-id="0550a-119">Пример</span><span class="sxs-lookup"><span data-stu-id="0550a-119">Example</span></span>

<span data-ttu-id="0550a-120">В следующем примере показано, как поместить блок try-catch в делегат, чтобы быстро перехватить исключение и продолжить выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="0550a-120">The following example shows how to put a try-catch block in a delegate to make it possible to catch an exception and continue with the query execution.</span></span>

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a><span data-ttu-id="0550a-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0550a-121">Compiling the Code</span></span>

- <span data-ttu-id="0550a-122">Чтобы скомпилировать и запустить эти примеры, скопируйте их в пример данных для PLINQ и вызовите этот метод из Main.</span><span class="sxs-lookup"><span data-stu-id="0550a-122">To compile and run these examples, copy them into the PLINQ Data Sample example and call the method from Main.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="0550a-123">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="0550a-123">Robust Programming</span></span>

<span data-ttu-id="0550a-124">Не перехватывайте исключение, если не знаете, как его обрабатывать, чтобы не нарушить состояние программы.</span><span class="sxs-lookup"><span data-stu-id="0550a-124">Do not catch an exception unless you know how to handle it so that you do not corrupt the state of your program.</span></span>

## <a name="see-also"></a><span data-ttu-id="0550a-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0550a-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="0550a-126">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="0550a-126">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
