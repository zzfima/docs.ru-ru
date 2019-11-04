---
title: Удаление потоков
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
ms.openlocfilehash: 1852135e9b7f48d6556e27f16819ddd48805af21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138091"
---
# <a name="destroying-threads"></a><span data-ttu-id="404ab-102">Удаление потоков</span><span class="sxs-lookup"><span data-stu-id="404ab-102">Destroying threads</span></span>
<span data-ttu-id="404ab-103">Метод <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> используется для остановки управляемого потока без возможности возобновления.</span><span class="sxs-lookup"><span data-stu-id="404ab-103">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method is used to stop a managed thread permanently.</span></span> <span data-ttu-id="404ab-104">При вызове <xref:System.Threading.Thread.Abort%2A> общеязыковая среда выполнения создает в целевом потоке исключение <xref:System.Threading.ThreadAbortException>, которое целевой поток может перехватить.</span><span class="sxs-lookup"><span data-stu-id="404ab-104">When you call <xref:System.Threading.Thread.Abort%2A>, the common language runtime throws a <xref:System.Threading.ThreadAbortException> in the target thread, which the target thread can catch.</span></span> <span data-ttu-id="404ab-105">Дополнительные сведения можно найти по адресу: <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="404ab-105">For more information, see <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="404ab-106">Если в потоке выполняется неуправляемый код при вызове его метода <xref:System.Threading.Thread.Abort%2A>, в среде выполнения он отмечается как <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="404ab-106">If a thread is executing unmanaged code when its <xref:System.Threading.Thread.Abort%2A> method is called, the runtime marks it <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>.</span></span> <span data-ttu-id="404ab-107">В этом случае исключение вызывается после возврата потока в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="404ab-107">The exception is thrown when the thread returns to managed code.</span></span>  
  
 <span data-ttu-id="404ab-108">После прерывания поток не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="404ab-108">Once a thread is aborted, it cannot be restarted.</span></span>  
  
 <span data-ttu-id="404ab-109">Метод <xref:System.Threading.Thread.Abort%2A> не приводит к немедленному прерыванию потока, так как целевой поток может перехватить <xref:System.Threading.ThreadAbortException> и выполнить любой объем кода в блоке `finally`.</span><span class="sxs-lookup"><span data-stu-id="404ab-109">The <xref:System.Threading.Thread.Abort%2A> method does not cause the thread to abort immediately, because the target thread can catch the <xref:System.Threading.ThreadAbortException> and execute arbitrary amounts of code in a `finally` block.</span></span> <span data-ttu-id="404ab-110">Если необходимо дождаться завершения потока, вы можете вызвать <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="404ab-110">You can call <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> if you need to wait until the thread has ended.</span></span> <span data-ttu-id="404ab-111">Блокирующий вызов <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> не завершится, пока поток полностью не закончит выполнение или не истечет указанный (необязательный) интервал времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="404ab-111"><xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> is a blocking call that does not return until the thread has actually stopped executing or an optional timeout interval has elapsed.</span></span> <span data-ttu-id="404ab-112">Прерванный поток может вызвать метод <xref:System.Threading.Thread.ResetAbort%2A> или выполнить любой объем операций в блоке `finally`, поэтому завершение ожидания не гарантируется, если вы не укажете время ожидания.</span><span class="sxs-lookup"><span data-stu-id="404ab-112">The aborted thread could call the <xref:System.Threading.Thread.ResetAbort%2A> method or perform unbounded processing in a `finally` block, so if you do not specify a timeout, the wait is not guaranteed to end.</span></span>  
  
 <span data-ttu-id="404ab-113">Потоки, ожидающие завершения метода <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, могут быть прерваны другими потоками, которые вызывают <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="404ab-113">Threads that are waiting on a call to the <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> method can be interrupted by other threads that call <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="handling-threadabortexception"></a><span data-ttu-id="404ab-114">Обработка ThreadAbortException</span><span class="sxs-lookup"><span data-stu-id="404ab-114">Handling ThreadAbortException</span></span>  
 <span data-ttu-id="404ab-115">Если вы ожидаете, что поток будет прерван вызовом <xref:System.Threading.Thread.Abort%2A> из вашего кода или в результате выгрузки домена приложения, в котором выполняется поток (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> использует <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для прерывания потоков), в таком потоке необходимо обработать <xref:System.Threading.ThreadAbortException>, включив в предложение `finally` все операции последней обработки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="404ab-115">If you expect your thread to be aborted, either as a result of calling <xref:System.Threading.Thread.Abort%2A> from your own code or as a result of unloading an application domain in which the thread is running (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> uses <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> to terminate threads), your thread must handle the <xref:System.Threading.ThreadAbortException> and perform any final processing in a `finally` clause, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="404ab-116">Код завершения работы следует поместить в предложении `catch` или `finally`, так как система повторно создаст исключение <xref:System.Threading.ThreadAbortException> в конце предложения `finally` или `catch`, если отсутствует предложение `finally`.</span><span class="sxs-lookup"><span data-stu-id="404ab-116">Your clean-up code must be in the `catch` clause or the `finally` clause, because a <xref:System.Threading.ThreadAbortException> is rethrown by the system at the end of the `finally` clause, or at the end of the `catch` clause if there is no `finally` clause.</span></span>  
  
 <span data-ttu-id="404ab-117">Чтобы предотвратить повторное создание исключения, вы можете вызвать метод <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="404ab-117">You can prevent the system from rethrowing the exception by calling the <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="404ab-118">Но этот вариант следует использовать только в том случае, если <xref:System.Threading.ThreadAbortException> вызывается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="404ab-118">However, you should do this only if your own code caused the <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404ab-119">См. также</span><span class="sxs-lookup"><span data-stu-id="404ab-119">See also</span></span>

- <xref:System.Threading.ThreadAbortException>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="404ab-120">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="404ab-120">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
