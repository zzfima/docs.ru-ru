---
title: "Помощник по отладке управляемого кода asynchronousThreadAbort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd99b098a619d4ad132432f4fd163d32598c2ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronousthreadabort-mda"></a><span data-ttu-id="193df-102">Помощник по отладке управляемого кода asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="193df-102">asynchronousThreadAbort MDA</span></span>
<span data-ttu-id="193df-103">Помощник по отладке управляемого кода (MDA) `asynchronousThreadAbort` активируется в том случае, если поток пытается выполнить асинхронное прерывание в другом потоке.</span><span class="sxs-lookup"><span data-stu-id="193df-103">The `asynchronousThreadAbort` managed debugging assistant (MDA) is activated when a thread attempts to introduce an asynchronous abort into another thread.</span></span> <span data-ttu-id="193df-104">При вызове синхронных прерываний потока помощник `asynchronousThreadAbort` не активируется.</span><span class="sxs-lookup"><span data-stu-id="193df-104">Synchronous thread aborts do not activate the `asynchronousThreadAbort` MDA.</span></span>

## <a name="symptoms"></a><span data-ttu-id="193df-105">Признаки</span><span class="sxs-lookup"><span data-stu-id="193df-105">Symptoms</span></span>
 <span data-ttu-id="193df-106">При прерывании потока основного приложения приложение аварийно завершает работу с необработанным исключением <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="193df-106">An application crashes with an unhandled <xref:System.Threading.ThreadAbortException> when the main application thread is aborted.</span></span> <span data-ttu-id="193df-107">Если выполнение приложения должно было продолжиться, последствия завершения могут быть даже хуже, чем при аварийном завершении, что может привести к обширному повреждению данных.</span><span class="sxs-lookup"><span data-stu-id="193df-107">If the application were to continue to execute, the consequences might be worse than the application crashing, possibly resulting in further data corruption.</span></span>

 <span data-ttu-id="193df-108">Атомарная операция, скорее всего, может быть прервана после частичного выполнения, в результате чего данные приложения будут находиться в непредсказуемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="193df-108">Operations meant to be atomic have likely been interrupted after partial completion, leaving application data in an unpredictable state.</span></span> <span data-ttu-id="193df-109">Исключение <xref:System.Threading.ThreadAbortException> может возникать в произвольных точках выполняемого кода и чаще всего в самых неожиданных местах.</span><span class="sxs-lookup"><span data-stu-id="193df-109">A <xref:System.Threading.ThreadAbortException> can be generated from seemingly random points in the execution of code, often in places from which an exception is not expected to arise.</span></span> <span data-ttu-id="193df-110">Если в коде не реализована возможность обработки такого исключения, это может привести к повреждению состояния.</span><span class="sxs-lookup"><span data-stu-id="193df-110">The code might not be capable of handling such an exception, resulting in a corrupt state.</span></span>

 <span data-ttu-id="193df-111">Из-за случайного характера возникновения этой проблемы ее симптомы могут быть самыми разными.</span><span class="sxs-lookup"><span data-stu-id="193df-111">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>

## <a name="cause"></a><span data-ttu-id="193df-112">Причина</span><span class="sxs-lookup"><span data-stu-id="193df-112">Cause</span></span>
 <span data-ttu-id="193df-113">Код в одном потоке вызвал метод <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> для целевого потока, чтобы выполнить асинхронное прерывание.</span><span class="sxs-lookup"><span data-stu-id="193df-113">Code in one thread called the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method on a target thread to introduce an asynchronous thread abort.</span></span> <span data-ttu-id="193df-114">Прерывание является асинхронным, поскольку код выполняет вызов <xref:System.Threading.Thread.Abort%2A> в потоке, который отличается от целевого потока операции прерывания.</span><span class="sxs-lookup"><span data-stu-id="193df-114">The thread abort is asynchronous because the code that makes the call to <xref:System.Threading.Thread.Abort%2A> is running on a different thread than the target of the abort operation.</span></span> <span data-ttu-id="193df-115">При синхронном прерывании проблемы не должны возникать, поскольку поток, выполняющий метод <xref:System.Threading.Thread.Abort%2A>, делает это только в безопасной контрольной точке, в которой состояние приложения является согласованным.</span><span class="sxs-lookup"><span data-stu-id="193df-115">Synchronous thread aborts should not cause a problem because the thread performing the <xref:System.Threading.Thread.Abort%2A> should have done so only at a safe checkpoint where application state is consistent.</span></span>

 <span data-ttu-id="193df-116">При асинхронном прерывании проблемы возникают потому, что обработка осуществляется в произвольных точках выполняемого целевого потока.</span><span class="sxs-lookup"><span data-stu-id="193df-116">Asynchronous thread aborts present a problem because they are processed at unpredictable points in the target thread's execution.</span></span> <span data-ttu-id="193df-117">Чтобы предотвратить это, код для выполнения в потоке, который может быть прерван таким образом, должен предусматривать обработку исключения <xref:System.Threading.ThreadAbortException> практически в каждой точке кода, чтобы обеспечить гарантированный возврат данных приложения в согласованное состояние.</span><span class="sxs-lookup"><span data-stu-id="193df-117">To avoid this, code written to run on a thread that might be aborted in this manner would need to handle a <xref:System.Threading.ThreadAbortException> at almost every line of code, taking care to put application data back into a consistent state.</span></span> <span data-ttu-id="193df-118">Естественно, сложно рассчитывать на то, что при написании кода будет учитываться вероятность возникновения этой проблемы, а также реализована защита во всех возможных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="193df-118">It is not realistic to expect code to be written with this problem in mind or to write code that protects against all possible circumstances.</span></span>

 <span data-ttu-id="193df-119">Вызовы неуправляемого кода и блоков `finally` будут прерываться не асинхронно, а непосредственно после выхода из одной из этих категорий.</span><span class="sxs-lookup"><span data-stu-id="193df-119">Calls into unmanaged code and `finally` blocks will not be aborted asynchronously but immediately upon exit from one of these categories.</span></span>

 <span data-ttu-id="193df-120">Причины этого трудно определить из-за случайного характера возникновения проблемы.</span><span class="sxs-lookup"><span data-stu-id="193df-120">The cause might be difficult to determine due to the randomness inherent to the problem.</span></span>

## <a name="resolution"></a><span data-ttu-id="193df-121">Решение</span><span class="sxs-lookup"><span data-stu-id="193df-121">Resolution</span></span>
 <span data-ttu-id="193df-122">Не используйте асинхронные прерывания в коде.</span><span class="sxs-lookup"><span data-stu-id="193df-122">Avoid code design that requires the use of asynchronous thread aborts.</span></span> <span data-ttu-id="193df-123">Существуют другие способы прерывания в целевом потоке, при которых не требуется вызывать метод <xref:System.Threading.Thread.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="193df-123">There are several approaches more appropriate for interruption of a target thread that do not require a call to <xref:System.Threading.Thread.Abort%2A>.</span></span> <span data-ttu-id="193df-124">Безопаснее всего реализовать механизм с использованием общего свойства, которое сигнализирует целевому потоку о необходимости запросить прерывание.</span><span class="sxs-lookup"><span data-stu-id="193df-124">The safest is to introduce a mechanism, such as a common property, that signals the target thread to request an interrupt.</span></span> <span data-ttu-id="193df-125">Целевой поток проверяет эти сигналы в определенных безопасных контрольных точках.</span><span class="sxs-lookup"><span data-stu-id="193df-125">The target thread checks the signal at certain safe checkpoints.</span></span> <span data-ttu-id="193df-126">Если обнаруживается запрос прерывания, может быть выполнено безопасное завершение потока.</span><span class="sxs-lookup"><span data-stu-id="193df-126">If it notices that an interrupt has been requested, it can shut down gracefully.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="193df-127">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="193df-127">Effect on the Runtime</span></span>
 <span data-ttu-id="193df-128">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="193df-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="193df-129">Он только выводит данные об асинхронных прерываниях потока.</span><span class="sxs-lookup"><span data-stu-id="193df-129">It only reports data about asynchronous thread aborts.</span></span>

## <a name="output"></a><span data-ttu-id="193df-130">Вывод</span><span class="sxs-lookup"><span data-stu-id="193df-130">Output</span></span>
 <span data-ttu-id="193df-131">В отчете этого помощника указывается идентификатор потока, выполнившего прерывание, а также идентификатор целевого потока для операции прерывания.</span><span class="sxs-lookup"><span data-stu-id="193df-131">The MDA reports the ID of the thread performing the abort and the ID of the thread that is the target of the abort.</span></span> <span data-ttu-id="193df-132">Они никогда не совпадают, поскольку область применения ограничивается асинхронными прерываниями.</span><span class="sxs-lookup"><span data-stu-id="193df-132">These will never be the same because this is limited to asynchronous aborts.</span></span>

## <a name="configuration"></a><span data-ttu-id="193df-133">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="193df-133">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="193df-134">Пример</span><span class="sxs-lookup"><span data-stu-id="193df-134">Example</span></span>
 <span data-ttu-id="193df-135">Для активации помощника по отладке управляемого кода `asynchronousThreadAbort` требуется только вызвать метод <xref:System.Threading.Thread.Abort%2A> для отдельного выполняющегося потока.</span><span class="sxs-lookup"><span data-stu-id="193df-135">Activating the `asynchronousThreadAbort` MDA requires only a call to <xref:System.Threading.Thread.Abort%2A> on a separate running thread.</span></span> <span data-ttu-id="193df-136">Проанализируйте последствия ситуаций, в которых функция запуска потока содержит набор более сложных операций, которые могут быть прерваны в любой произвольной точке.</span><span class="sxs-lookup"><span data-stu-id="193df-136">Consider the consequences if the contents of the thread start function were a set of more complex operations which might be interrupted at any arbitrary point by the abort.</span></span>

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a><span data-ttu-id="193df-137">См. также</span><span class="sxs-lookup"><span data-stu-id="193df-137">See Also</span></span>
 <span data-ttu-id="193df-138"><xref:System.Threading.Thread> [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)</span><span class="sxs-lookup"><span data-stu-id="193df-138"><xref:System.Threading.Thread> [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)</span></span>
