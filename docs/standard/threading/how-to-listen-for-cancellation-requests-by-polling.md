---
title: "Практическое руководство. Прослушивание запросов на отмену посредством опросов"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="75f2d-102">Практическое руководство. Прослушивание запросов на отмену посредством опросов</span><span class="sxs-lookup"><span data-stu-id="75f2d-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="75f2d-103">В следующем примере показано одним из способов пользовательский код может выполнять опрос токена отмены через регулярные интервалы, чтобы увидеть, есть ли запрос на отмену из вызывающего потока.</span><span class="sxs-lookup"><span data-stu-id="75f2d-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="75f2d-104">В этом примере используется <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> типа, но тот же принцип применяется к асинхронных операций, которые созданы напрямую с помощью <xref:System.Threading.ThreadPool?displayProperty=nameWithType> типа или <xref:System.Threading.Thread?displayProperty=nameWithType> типа.</span><span class="sxs-lookup"><span data-stu-id="75f2d-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75f2d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="75f2d-105">Example</span></span>  
 <span data-ttu-id="75f2d-106">Опроса необходим циклический или рекурсивный код, который может периодически считывать значение логического <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="75f2d-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="75f2d-107">Если вы используете <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> типа и ожидается для задачи завершения в вызывающем потоке, можно использовать <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> метода проверьте свойство, и выдается исключение.</span><span class="sxs-lookup"><span data-stu-id="75f2d-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="75f2d-108">При использовании этого метода убедитесь, что правильно исключение вызывается в ответ на запрос.</span><span class="sxs-lookup"><span data-stu-id="75f2d-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="75f2d-109">Если вы используете <xref:System.Threading.Tasks.Task>, то вызов этого метода лучше, чем вручную вызов <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="75f2d-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="75f2d-110">Если нет необходимости создавать исключение, то можно просто проверить свойство и возврата из метода, если свойство `true`.</span><span class="sxs-lookup"><span data-stu-id="75f2d-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="75f2d-111">Вызов <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> выполняется очень быстро и не вносит в циклы существенную нагрузку.</span><span class="sxs-lookup"><span data-stu-id="75f2d-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="75f2d-112">При вызове <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, необходимо явно проверить <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойства, если у вас есть другие типы работ, действие в ответ на отмену, помимо создания исключения.</span><span class="sxs-lookup"><span data-stu-id="75f2d-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="75f2d-113">В этом примере видно, что код фактически обращается к свойству дважды: один раз в явный доступ и снова <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="75f2d-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="75f2d-114">Но поскольку в действии по считыванию <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> свойство используется только одна временная, инструкция чтения для каждого доступа, двойной доступ не важен с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="75f2d-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="75f2d-115">По-прежнему рекомендуется, чтобы вызвать метод, не вызывая вручную <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="75f2d-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f2d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="75f2d-116">See Also</span></span>  
 [<span data-ttu-id="75f2d-117">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="75f2d-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)
