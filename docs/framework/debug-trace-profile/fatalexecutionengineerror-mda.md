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
ms.openlocfilehash: 4595049d4ea71de30cf13334e32cd4bb2699f2ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33392542"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="8e038-102">Помощник по отладке управляемого кода fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="8e038-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="8e038-103">Помощник по отладке управляемого кода `fatalExecutionEngine``Error` (MDA) активируется при обнаружении неустранимой ошибки в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="8e038-103">The `fatalExecutionEngine``Error` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="8e038-104">В этом случае процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="8e038-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8e038-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="8e038-105">Symptoms</span></span>  
 <span data-ttu-id="8e038-106">Непредвиденное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="8e038-106">Unexpected process termination.</span></span> <span data-ttu-id="8e038-107">Другие признаки определить невозможно, поскольку сбой среды CLR может происходить по самым разным причинам.</span><span class="sxs-lookup"><span data-stu-id="8e038-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8e038-108">Причина</span><span class="sxs-lookup"><span data-stu-id="8e038-108">Cause</span></span>  
 <span data-ttu-id="8e038-109">Неустранимое повреждение среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8e038-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="8e038-110">Чаще всего это вызвано повреждением данных, которое может быть связано с целым рядом проблем, таких как вызовы некорректных функций вызова неуправляемого кода и передача недопустимых данных в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="8e038-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8e038-111">Решение</span><span class="sxs-lookup"><span data-stu-id="8e038-111">Resolution</span></span>  
 <span data-ttu-id="8e038-112">Чтобы определить причины проблемы, попробуйте включить другие помощники по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8e038-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="8e038-113">При диагностике вам могут помочь следующие помощники по отладке управляемого кода:</span><span class="sxs-lookup"><span data-stu-id="8e038-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
-   [<span data-ttu-id="8e038-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="8e038-114">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [<span data-ttu-id="8e038-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="8e038-115">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [<span data-ttu-id="8e038-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="8e038-116">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [<span data-ttu-id="8e038-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="8e038-117">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [<span data-ttu-id="8e038-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="8e038-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [<span data-ttu-id="8e038-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="8e038-119">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [<span data-ttu-id="8e038-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="8e038-120">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [<span data-ttu-id="8e038-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="8e038-121">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [<span data-ttu-id="8e038-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="8e038-122">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [<span data-ttu-id="8e038-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="8e038-123">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [<span data-ttu-id="8e038-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="8e038-124">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [<span data-ttu-id="8e038-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="8e038-125">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8e038-126">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="8e038-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="8e038-127">Этот помощник по отладке управляемого кода не оказывает влияния на поведение среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e038-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8e038-128">Вывод</span><span class="sxs-lookup"><span data-stu-id="8e038-128">Output</span></span>  
 <span data-ttu-id="8e038-129">Адрес функции среды CLR, которая стала причиной неустранимой ошибки, идентификатор потока, в котором произошла ошибка, а также код самой ошибки.</span><span class="sxs-lookup"><span data-stu-id="8e038-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8e038-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="8e038-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e038-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8e038-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [<span data-ttu-id="8e038-132">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="8e038-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
