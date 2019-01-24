---
title: Помощник по отладке управляемого кода fatalExecutionEngineError
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e5c12cc6d09e2f1c5b0c58ac4ad3462dca3463c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700979"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="b6057-102">Помощник по отладке управляемого кода fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="b6057-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="b6057-103">Помощник по отладке управляемого кода `fatalExecutionEngineError` (MDA) активируется при обнаружении неустранимой ошибки в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b6057-103">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="b6057-104">В этом случае процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="b6057-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b6057-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="b6057-105">Symptoms</span></span>  
 <span data-ttu-id="b6057-106">Непредвиденное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="b6057-106">Unexpected process termination.</span></span> <span data-ttu-id="b6057-107">Другие признаки определить невозможно, поскольку сбой среды CLR может происходить по самым разным причинам.</span><span class="sxs-lookup"><span data-stu-id="b6057-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b6057-108">Причина</span><span class="sxs-lookup"><span data-stu-id="b6057-108">Cause</span></span>  
 <span data-ttu-id="b6057-109">Неустранимое повреждение среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b6057-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="b6057-110">Чаще всего это вызвано повреждением данных, которое может быть связано с целым рядом проблем, таких как вызовы некорректных функций вызова неуправляемого кода и передача недопустимых данных в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="b6057-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b6057-111">Решение</span><span class="sxs-lookup"><span data-stu-id="b6057-111">Resolution</span></span>  
 <span data-ttu-id="b6057-112">Чтобы определить причины проблемы, попробуйте включить другие помощники по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="b6057-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="b6057-113">При диагностике вам могут помочь следующие помощники по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="b6057-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
-   [<span data-ttu-id="b6057-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="b6057-114">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [<span data-ttu-id="b6057-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="b6057-115">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [<span data-ttu-id="b6057-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="b6057-116">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [<span data-ttu-id="b6057-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="b6057-117">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [<span data-ttu-id="b6057-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="b6057-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [<span data-ttu-id="b6057-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="b6057-119">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [<span data-ttu-id="b6057-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="b6057-120">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [<span data-ttu-id="b6057-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="b6057-121">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [<span data-ttu-id="b6057-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="b6057-122">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [<span data-ttu-id="b6057-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="b6057-123">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [<span data-ttu-id="b6057-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="b6057-124">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [<span data-ttu-id="b6057-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="b6057-125">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b6057-126">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="b6057-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="b6057-127">Этот помощник по отладке управляемого кода не оказывает влияния на поведение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6057-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b6057-128">Вывод</span><span class="sxs-lookup"><span data-stu-id="b6057-128">Output</span></span>  
 <span data-ttu-id="b6057-129">Адрес функции среды CLR, которая стала причиной неустранимой ошибки, идентификатор потока, в котором произошла ошибка, а также код самой ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6057-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b6057-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b6057-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6057-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b6057-131">See also</span></span>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="b6057-132">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="b6057-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
