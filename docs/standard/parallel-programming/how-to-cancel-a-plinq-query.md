---
title: "Практическое руководство. Отмена запроса PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="4af3e-102">Практическое руководство. Отмена запроса PLINQ</span><span class="sxs-lookup"><span data-stu-id="4af3e-102">How to: Cancel a PLINQ Query</span></span>
<span data-ttu-id="4af3e-103">В следующих примерах показано два способа отмены запроса PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4af3e-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="4af3e-104">В первом примере показано, как отменить запрос, который состоит в основном из обхода данных.</span><span class="sxs-lookup"><span data-stu-id="4af3e-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="4af3e-105">Во втором примере показано, как отменить запрос, который содержит пользовательскую функцию, требовательных к вычислительным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="4af3e-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af3e-106">Если включен «Только мой код», Visual Studio прерывает выполнение программы на строке, в которой создается исключение и выводит сообщение об ошибке «исключение, которое не может быть обработано пользовательским кодом».</span><span class="sxs-lookup"><span data-stu-id="4af3e-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="4af3e-107">Эта ошибка не является критической.</span><span class="sxs-lookup"><span data-stu-id="4af3e-107">This error is benign.</span></span> <span data-ttu-id="4af3e-108">Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже.</span><span class="sxs-lookup"><span data-stu-id="4af3e-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="4af3e-109">Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.</span><span class="sxs-lookup"><span data-stu-id="4af3e-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
>   
>  <span data-ttu-id="4af3e-110">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="4af3e-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="4af3e-111">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4af3e-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af3e-112">Пример</span><span class="sxs-lookup"><span data-stu-id="4af3e-112">Example</span></span>  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 <span data-ttu-id="4af3e-113">Платформа PLINQ не помещает одно <xref:System.OperationCanceledException> в <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> должно обрабатываться в отдельном блоке catch.</span><span class="sxs-lookup"><span data-stu-id="4af3e-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="4af3e-114">Если один или несколько пользовательских делегатов вызывает OperationCanceledException(externalCT) (с помощью внешней <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), но не другие исключения, а запрос был определен как `AsParallel().WithCancellation(externalCT)`, а затем PLINQ выдаст один <xref:System.OperationCanceledException> (externalCT), а не <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4af3e-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4af3e-115">Тем не менее, если один пользовательский делегат вызывает <xref:System.OperationCanceledException>и другой делегат создает другой тип исключения, а затем оба исключения помещаются в <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="4af3e-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>  
  
 <span data-ttu-id="4af3e-116">Общие рекомендации по отмене выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4af3e-116">The general guidance on cancellation is as follows:</span></span>  
  
1.  <span data-ttu-id="4af3e-117">Если выполнить отмену пользовательский делегат PLINQ должен информирования о внешних <xref:System.Threading.CancellationToken> и исключение <xref:System.OperationCanceledException>(externalCT).</span><span class="sxs-lookup"><span data-stu-id="4af3e-117">If you perform user-delegate cancellation you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>  
  
2.  <span data-ttu-id="4af3e-118">Если произошла отмена и другие исключения не возникают, необходимо обработать <xref:System.OperationCanceledException> вместо <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="4af3e-118">If cancellation occurs and no other exceptions are thrown, then you should handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4af3e-119">Пример</span><span class="sxs-lookup"><span data-stu-id="4af3e-119">Example</span></span>  
 <span data-ttu-id="4af3e-120">Приведенный ниже показано, как обработка отмены, когда имеется функция требовательных к вычислительным ресурсам в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="4af3e-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 <span data-ttu-id="4af3e-121">При обработке отмены в пользовательском коде, не нужно использовать <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> в определении запроса.</span><span class="sxs-lookup"><span data-stu-id="4af3e-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="4af3e-122">Однако рекомендуется это сделать, так как <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> не влияет на производительность запросов и позволяет отмену может быть обработано операторов запроса и пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="4af3e-122">However, we recommended that you do this because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>  
  
 <span data-ttu-id="4af3e-123">Чтобы обеспечить отклик системы, рекомендуется проверять отмену приблизительно каждую миллисекунду. Тем не менее любой период до 10 миллисекунд считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="4af3e-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="4af3e-124">Эта частота не должен отрицательно повлиять на производительность кода.</span><span class="sxs-lookup"><span data-stu-id="4af3e-124">This frequency should not have a negative impact on your code's performance.</span></span>  
  
 <span data-ttu-id="4af3e-125">При удалении перечислителя, например когда код прерывается вне цикла foreach (For Each в Visual Basic), выполняющего итерацию результатов запроса, а затем запрос отменяется, но исключение не возникает.</span><span class="sxs-lookup"><span data-stu-id="4af3e-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is cancelled, but no exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af3e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4af3e-126">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable>  
 [<span data-ttu-id="4af3e-127">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4af3e-127">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [<span data-ttu-id="4af3e-128">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="4af3e-128">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
