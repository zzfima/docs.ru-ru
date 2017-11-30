---
title: "Уничтожение потоков"
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
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a><span data-ttu-id="6cb0e-102">Уничтожение потоков</span><span class="sxs-lookup"><span data-stu-id="6cb0e-102">Destroying Threads</span></span>
<span data-ttu-id="6cb0e-103"><xref:System.Threading.Thread.Abort%2A> Метод используется для прекращения управляемого потока, без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-103">The <xref:System.Threading.Thread.Abort%2A> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="6cb0e-104">При вызове <xref:System.Threading.Thread.Abort%2A>, общеязыковая среда выполнения создает исключение <xref:System.Threading.ThreadAbortException> в целевом потоке, который целевой поток может перехватить.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="6cb0e-105">Для получения дополнительной информации см. <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cb0e-106">Если поток выполняет неуправляемый код, при его <xref:System.Threading.Thread.Abort%2A> вызывается метод, среда выполнения отмечает его <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6cb0e-107">Исключение вызывается при возврате потока в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="6cb0e-108">После прерывания потока не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="6cb0e-109"><xref:System.Threading.Thread.Abort%2A> Метод не вызывает немедленно, прерывание потока, поскольку целевой поток может перехватить <xref:System.Threading.ThreadAbortException> и выполнить произвольный объем кода в `finally` блока.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="6cb0e-110">Можно вызвать <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> Если необходимо дождаться завершения потока.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="6cb0e-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>является блокирующий вызов, который не отвечает, пока поток остановки выполнения или истечении интервала необязательное время ожидания.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="6cb0e-112">Прерванный поток может вызвать <xref:System.Threading.Thread.ResetAbort%2A> метод или выполнить неограниченную обработку в `finally` блокировать, если указать время ожидания для завершения ожидания не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="6cb0e-113">Потоков, ожидающих во время вызова <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> метод может быть прервана, другие потоки, которые вызывают <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="6cb0e-114">Обработка ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="6cb0e-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="6cb0e-115">Если ожидается, что поток будет прерван, в результате вызова <xref:System.Threading.Thread.Abort%2A> из собственного кода или выгрузки домена приложения, в котором выполняется поток (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> использует <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для прерывания потоков), в потоке должен обрабатываться <xref:System.Threading.ThreadAbortException> и выполнить обработку в окончательный `finally` предложения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 <span data-ttu-id="6cb0e-116">Код очистки должен быть в `catch` предложение или `finally` предложение, так как <xref:System.Threading.ThreadAbortException> повторно создается системой в конце `finally` предложение, или в конце `catch` предложение, если имеется не `finally` предложения.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="6cb0e-117">Система может предотвратить повторное создание исключения путем вызова <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6cb0e-118">Однако делать это, только если код вызвал <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="6cb0e-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb0e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6cb0e-119">See Also</span></span>  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="6cb0e-120">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="6cb0e-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
