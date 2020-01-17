---
title: Сборка мусора и производительность
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, troubleshooting
- garbage collection, performance
ms.assetid: c203467b-e95c-4ccf-b30b-953eb3463134
ms.openlocfilehash: 72cf742aae26f9441229b355dc6e70da7a5fc9cd
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900581"
---
# <a name="garbage-collection-and-performance"></a><span data-ttu-id="bf2e0-102">Сборка мусора и производительность</span><span class="sxs-lookup"><span data-stu-id="bf2e0-102">Garbage Collection and Performance</span></span>

<span data-ttu-id="bf2e0-103">В этом разделе описаны вопросы, связанные со сборкой мусора и использованием памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-103">This topic describes issues related to garbage collection and memory usage.</span></span> <span data-ttu-id="bf2e0-104">Здесь рассматриваются проблемы, относящиеся к управляемой куче, и объясняется, как свести к минимуму влияние сборки мусора на работу приложений.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-104">It addresses issues that pertain to the managed heap and explains how to minimize the effect of garbage collection on your applications.</span></span> <span data-ttu-id="bf2e0-105">Для каждого аспекта приводятся ссылки на процедуры, которые можно использовать для анализа проблем.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-105">Each issue has links to procedures that you can use to investigate problems.</span></span>

## <a name="performance-analysis-tools"></a><span data-ttu-id="bf2e0-106">Средства анализа производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-106">Performance Analysis Tools</span></span>

<span data-ttu-id="bf2e0-107">В следующих разделах описываются средства, которые можно использовать для диагностики проблем с использованием памяти и сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-107">The following sections describe the tools that are available for investigating memory usage and garbage collection issues.</span></span> <span data-ttu-id="bf2e0-108">Эти средства используются в [процедурах](#performance-check-procedures), описанных далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-108">The [procedures](#performance-check-procedures) provided later in this topic refer to these tools.</span></span>

### <a name="memory-performance-counters"></a><span data-ttu-id="bf2e0-109">Счетчики памяти</span><span class="sxs-lookup"><span data-stu-id="bf2e0-109">Memory Performance Counters</span></span>

<span data-ttu-id="bf2e0-110">Счетчики производительности можно использовать для сбора данных производительности.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-110">You can use performance counters to gather performance data.</span></span> <span data-ttu-id="bf2e0-111">Инструкции см. в разделе [Профилирование среды выполнения](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-111">For instructions, see [Runtime Profiling](../../../docs/framework/debug-trace-profile/runtime-profiling.md).</span></span> <span data-ttu-id="bf2e0-112">Категория счетчиков производительности "Память CLR .NET" (как описано в разделе [Счетчики производительности в .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md)) предоставляет сведения о сборщике мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-112">The .NET CLR Memory category of performance counters, as described in [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md), provides information about the garbage collector.</span></span>

### <a name="debugging-with-sos"></a><span data-ttu-id="bf2e0-113">Отладка с помощью расширения SOS</span><span class="sxs-lookup"><span data-stu-id="bf2e0-113">Debugging with SOS</span></span>

<span data-ttu-id="bf2e0-114">Для проверки объектов в управляемой куче можно использовать [отладчик Windows (WinDbg)](/windows-hardware/drivers/debugger/index).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-114">You can use the [Windows Debugger (WinDbg)](/windows-hardware/drivers/debugger/index) to inspect objects on the managed heap.</span></span>

<span data-ttu-id="bf2e0-115">Чтобы установить WinDbg, установите средства отладки для Windows со страницы [скачивания средств отладки для Windows](/windows-hardware/drivers/debugger/debugger-download-tools).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-115">To install WinDbg, install Debugging Tools for Windows from the [Download Debugging Tools for Windows](/windows-hardware/drivers/debugger/debugger-download-tools) page.</span></span>

### <a name="garbage-collection-etw-events"></a><span data-ttu-id="bf2e0-116">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="bf2e0-116">Garbage Collection ETW Events</span></span>

<span data-ttu-id="bf2e0-117">Трассировка событий Windows (ETW) — это система трассировки, дополняющая поддержку профилирования и отладки в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-117">Event tracing for Windows (ETW) is a tracing system that supplements the profiling and debugging support provided by the .NET Framework.</span></span> <span data-ttu-id="bf2e0-118">Начиная с .NET Framework 4, [события ETW для сборки мусора](../../../docs/framework/performance/garbage-collection-etw-events.md) собирают полезные сведения для анализа управляемой кучи с точки зрения статистики.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-118">Starting with the .NET Framework 4, [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md) capture useful information for analyzing the managed heap from a statistical point of view.</span></span> <span data-ttu-id="bf2e0-119">Например, событие `GCStart_V1`, которое вызывается перед началом сборки мусора, предоставляет следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-119">For example, the `GCStart_V1` event, which is raised when a garbage collection is about to occur, provides the following information:</span></span>

- <span data-ttu-id="bf2e0-120">собираемое поколение объектов;</span><span class="sxs-lookup"><span data-stu-id="bf2e0-120">Which generation of objects is being collected.</span></span>

- <span data-ttu-id="bf2e0-121">что активировало сборку мусора;</span><span class="sxs-lookup"><span data-stu-id="bf2e0-121">What triggered the garbage collection.</span></span>

- <span data-ttu-id="bf2e0-122">тип сборки мусора (параллельная или непараллельная).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-122">Type of garbage collection (concurrent or not concurrent).</span></span>

<span data-ttu-id="bf2e0-123">Ведение журнала событий трассировки событий Windows эффективно и не скрывает проблемы производительности, связанные со сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-123">ETW event logging is efficient and will not mask any performance problems associated with garbage collection.</span></span> <span data-ttu-id="bf2e0-124">Процесс может предоставлять свои собственные события вместе с событиями трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-124">A process can provide its own events in conjunction with ETW events.</span></span> <span data-ttu-id="bf2e0-125">При регистрации в журнале события приложения можно соотнести с событиями сборки мусора, чтобы определить, как и когда возникают проблемы кучи.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-125">When logged, both the application's events and the garbage collection events can be correlated to determine how and when heap problems occur.</span></span> <span data-ttu-id="bf2e0-126">Например, серверное приложение может предоставлять события в начале и в конце запроса клиента.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-126">For example, a server application could provide events at the start and end of a client request.</span></span>

### <a name="the-profiling-api"></a><span data-ttu-id="bf2e0-127">API профилирования</span><span class="sxs-lookup"><span data-stu-id="bf2e0-127">The Profiling API</span></span>

<span data-ttu-id="bf2e0-128">Интерфейсы профилирования среды выполнения (CLR) предоставляют подробные сведения об объектах, которые были затронуты во время сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-128">The common language runtime (CLR) profiling interfaces provide detailed information about the objects that were affected during garbage collection.</span></span> <span data-ttu-id="bf2e0-129">Профилировщик может получать уведомления о начале и завершении сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-129">A profiler can be notified when a garbage collection starts and ends.</span></span> <span data-ttu-id="bf2e0-130">Он может предоставлять отчеты об объектах в управляемой куче, включая идентификацию объектов в каждом поколении.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-130">It can provide reports about the objects on the managed heap, including an identification of objects in each generation.</span></span> <span data-ttu-id="bf2e0-131">Дополнительные сведения см. в разделе [Общие сведения о профилировании](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-131">For more information, see [Profiling Overview](../../../docs/framework/unmanaged-api/profiling/profiling-overview.md).</span></span>

<span data-ttu-id="bf2e0-132">Профилировщики могут предоставлять исчерпывающую информацию.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-132">Profilers can provide comprehensive information.</span></span> <span data-ttu-id="bf2e0-133">Однако сложные профилировщики потенциально могут менять поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-133">However, complex profilers can potentially modify an application's behavior.</span></span>

### <a name="application-domain-resource-monitoring"></a><span data-ttu-id="bf2e0-134">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="bf2e0-134">Application Domain Resource Monitoring</span></span>

<span data-ttu-id="bf2e0-135">Начиная с .NET Framework 4 функция отслеживания ресурсов домена приложения (ARM) позволяет узлам отслеживать загрузку ЦП и использование памяти доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-135">Starting with the .NET Framework 4, Application domain resource monitoring (ARM) enables hosts to monitor CPU and memory usage by application domain.</span></span> <span data-ttu-id="bf2e0-136">Дополнительные сведения см. в разделе [Отслеживание ресурсов домена приложения](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-136">For more information, see [Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md).</span></span>

## <a name="troubleshooting-performance-issues"></a><span data-ttu-id="bf2e0-137">Диагностика проблем производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-137">Troubleshooting Performance Issues</span></span>

<span data-ttu-id="bf2e0-138">Первый этап — [определить, действительно ли проблема относится к сборке мусора](#IsGC).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-138">The first step is to [determine whether the issue is actually garbage collection](#IsGC).</span></span> <span data-ttu-id="bf2e0-139">Если это так, выберите одну из проблем в списке ниже, чтобы определить способ ее устранения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-139">If you determine that it is, select from the following list to troubleshoot the problem.</span></span>

- [<span data-ttu-id="bf2e0-140">Создается исключение нехватки памяти</span><span class="sxs-lookup"><span data-stu-id="bf2e0-140">An out-of-memory exception is thrown</span></span>](#Issue_OOM)

- [<span data-ttu-id="bf2e0-141">Процесс использует слишком много памяти</span><span class="sxs-lookup"><span data-stu-id="bf2e0-141">The process uses too much memory</span></span>](#Issue_TooMuchMemory)

- [<span data-ttu-id="bf2e0-142">Сборщик мусора недостаточно быстро освобождает объекты</span><span class="sxs-lookup"><span data-stu-id="bf2e0-142">The garbage collector does not reclaim objects fast enough</span></span>](#Issue_NotFastEnough)

- [<span data-ttu-id="bf2e0-143">Управляемая куча слишком сильно фрагментирована</span><span class="sxs-lookup"><span data-stu-id="bf2e0-143">The managed heap is too fragmented</span></span>](#Issue_Fragmentation)

- [<span data-ttu-id="bf2e0-144">Слишком большие интервалы между сборками мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-144">Garbage collection pauses are too long</span></span>](#Issue_LongPauses)

- [<span data-ttu-id="bf2e0-145">Слишком большой размер поколения 0</span><span class="sxs-lookup"><span data-stu-id="bf2e0-145">Generation 0 is too big</span></span>](#Issue_Gen0)

- [<span data-ttu-id="bf2e0-146">Слишком высокая загрузка ЦП во время сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-146">CPU usage during a garbage collection is too high</span></span>](#Issue_HighCPU)

<a name="Issue_OOM"></a>

### <a name="issue-an-out-of-memory-exception-is-thrown"></a><span data-ttu-id="bf2e0-147">Проблема. Создается исключение нехватки памяти</span><span class="sxs-lookup"><span data-stu-id="bf2e0-147">Issue: An Out-of-Memory Exception Is Thrown</span></span>

<span data-ttu-id="bf2e0-148">Существует два допустимых случая создания управляемого исключения <xref:System.OutOfMemoryException>:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-148">There are two legitimate cases for a managed <xref:System.OutOfMemoryException> to be thrown:</span></span>

- <span data-ttu-id="bf2e0-149">нехватка виртуальной памяти;</span><span class="sxs-lookup"><span data-stu-id="bf2e0-149">Running out of virtual memory.</span></span>

  <span data-ttu-id="bf2e0-150">Сборщик мусора распределяет память из системы в виде сегментов заранее заданного размера.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-150">The garbage collector allocates memory from the system in segments of a pre-determined size.</span></span> <span data-ttu-id="bf2e0-151">Если выделению требуется дополнительный сегмент, но в пространстве виртуальной памяти процесса не осталось непрерывных свободных блоков, произойдет сбой выделения памяти для управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-151">If an allocation requires an additional segment, but there is no contiguous free block left in the process's virtual memory space, the allocation for the managed heap will fail.</span></span>

- <span data-ttu-id="bf2e0-152">нехватка физической памяти для выделения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-152">Not having enough physical memory to allocate.</span></span>

|<span data-ttu-id="bf2e0-153">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-153">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-154">Определите, является ли исключение нехватки памяти управляемым.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-154">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)<br /><br /> [<span data-ttu-id="bf2e0-155">Определите, сколько виртуальной памяти можно зарезервировать.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-155">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="bf2e0-156">Определите, имеется ли достаточный объем физической памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-156">Determine whether there is enough physical memory.</span></span>](#Physical)|

<span data-ttu-id="bf2e0-157">Если выяснилось, что исключение не относится к допустимым сценариям, обратитесь в службу технической поддержки Майкрософт, сообщив следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-157">If you determine that the exception is not legitimate, contact Microsoft Customer Service and Support with the following information:</span></span>

- <span data-ttu-id="bf2e0-158">стек с управляемым исключением нехватки памяти,</span><span class="sxs-lookup"><span data-stu-id="bf2e0-158">The stack with the managed out-of-memory exception.</span></span>

- <span data-ttu-id="bf2e0-159">полный дамп памяти,</span><span class="sxs-lookup"><span data-stu-id="bf2e0-159">Full memory dump.</span></span>

- <span data-ttu-id="bf2e0-160">данные, подтверждающие недопустимый характер исключения нехватки памяти, включая данные, показывающие, что проблема не связана с виртуальной или физической памятью.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-160">Data that proves that it is not a legitimate out-of-memory exception, including data that shows that virtual or physical memory is not an issue.</span></span>

<a name="Issue_TooMuchMemory"></a>

### <a name="issue-the-process-uses-too-much-memory"></a><span data-ttu-id="bf2e0-161">Проблема. Процесс использует слишком много памяти</span><span class="sxs-lookup"><span data-stu-id="bf2e0-161">Issue: The Process Uses Too Much Memory</span></span>

<span data-ttu-id="bf2e0-162">Считается, что с помощью индикатора использования памяти на вкладке **Быстродействие** диспетчера задач Windows можно определить, что процесс использует слишком много памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-162">A common assumption is that the memory usage display on the **Performance** tab of Windows Task Manager can indicate when too much memory is being used.</span></span> <span data-ttu-id="bf2e0-163">Однако этот индикатор относится к рабочему набору; он не предоставляет сведения об использовании виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-163">However, that display pertains to the working set; it does not provide information about virtual memory usage.</span></span>

<span data-ttu-id="bf2e0-164">Если выяснилось, что проблема вызвана управляемой кучей, необходимо провести для управляемой кучи измерения в динамике, чтобы определить наличие каких-либо шаблонов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-164">If you determine that the issue is caused by the managed heap, you must measure the managed heap over time to determine any patterns.</span></span>

<span data-ttu-id="bf2e0-165">Если выяснилось, что проблема не вызвана управляемой кучей, необходимо использовать отладку неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-165">If you determine that the problem is not caused by the managed heap, you must use native debugging.</span></span>

|<span data-ttu-id="bf2e0-166">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-166">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-167">Определите, сколько виртуальной памяти можно зарезервировать.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-167">Determine how much virtual memory can be reserved.</span></span>](#GetVM)<br /><br /> [<span data-ttu-id="bf2e0-168">Определите объем памяти, зафиксированный управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-168">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)<br /><br /> [<span data-ttu-id="bf2e0-169">Определите объем памяти, зарезервированный управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-169">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)<br /><br /> [<span data-ttu-id="bf2e0-170">Определите большие объекты в поколении 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-170">Determine large objects in generation 2.</span></span>](#ExamineGen2)<br /><br /> [<span data-ttu-id="bf2e0-171">Определите ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-171">Determine references to objects.</span></span>](#ObjRef)|

<a name="Issue_NotFastEnough"></a>

### <a name="issue-the-garbage-collector-does-not-reclaim-objects-fast-enough"></a><span data-ttu-id="bf2e0-172">Проблема. Сборщик мусора недостаточно быстро освобождает объекты</span><span class="sxs-lookup"><span data-stu-id="bf2e0-172">Issue: The Garbage Collector Does Not Reclaim Objects Fast Enough</span></span>

<span data-ttu-id="bf2e0-173">Если есть признаки того, что объекты не освобождаются сборкой мусора должным образом, необходимо определить, нет ли строгих ссылок на эти объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-173">When it appears as if objects are not being reclaimed as expected for garbage collection, you must determine if there are any strong references to those objects.</span></span>

<span data-ttu-id="bf2e0-174">Эта проблема также может возникать, если не выполнялась сборка мусора для поколения, содержащего неиспользуемый объект. Это является признаком того, что для неиспользуемого объекта не выполнялся метод завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-174">You may also encounter this issue if there has been no garbage collection for the generation that contains a dead object, which indicates that the finalizer for the dead object has not been run.</span></span> <span data-ttu-id="bf2e0-175">Например, это может происходить, когда вы запускаете приложение однопотокового подразделения (STA) и не удается вызвать в него поток, который обслуживает очередь метода завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-175">For example, this is possible when you are running a single-threaded apartment (STA) application and the thread that services the finalizer queue cannot call into it.</span></span>

|<span data-ttu-id="bf2e0-176">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-176">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-177">Проверьте ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-177">Check references to objects.</span></span>](#ObjRef)<br /><br /> [<span data-ttu-id="bf2e0-178">Определите, выполнялся ли метод завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-178">Determine whether a finalizer has been run.</span></span>](#Induce)<br /><br /> [<span data-ttu-id="bf2e0-179">Определите наличие объектов, ожидающих завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-179">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)|

<a name="Issue_Fragmentation"></a>

### <a name="issue-the-managed-heap-is-too-fragmented"></a><span data-ttu-id="bf2e0-180">Проблема. Управляемая куча слишком сильно фрагментирована</span><span class="sxs-lookup"><span data-stu-id="bf2e0-180">Issue: The Managed Heap Is Too fragmented</span></span>

<span data-ttu-id="bf2e0-181">Уровень фрагментации рассчитывается как отношение свободного пространства ко всей выделенной памяти для поколения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-181">The fragmentation level is calculated as the ratio of free space over the total allocated memory for the generation.</span></span> <span data-ttu-id="bf2e0-182">Для поколения 2 допустимый уровень фрагментации составляет не более 20 %.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-182">For generation 2, an acceptable level of fragmentation is no more than 20%.</span></span> <span data-ttu-id="bf2e0-183">Поскольку поколение 2 может очень сильно вырасти, показатель фрагментации более важен, чем абсолютное значение.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-183">Because generation 2 can get very big, the ratio of fragmentation is more important than the absolute value.</span></span>

<span data-ttu-id="bf2e0-184">Наличие большого объема свободного пространства в поколении 0 не является проблемой, так как это поколение, в котором выделяются новые объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-184">Having lots of free space in generation 0 is not a problem because this is the generation where new objects are allocated.</span></span>

<span data-ttu-id="bf2e0-185">Фрагментация всегда возникает в куче больших объектов, так как для нее не выполняется сжатие.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-185">Fragmentation always occurs in the large object heap because it is not compacted.</span></span> <span data-ttu-id="bf2e0-186">Смежные свободные объекты естественным образом свертываются в одно пространство для удовлетворения запросов на размещение больших объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-186">Free objects that are adjacent are naturally collapsed into a single space to satisfy large object allocation requests.</span></span>

<span data-ttu-id="bf2e0-187">Фрагментация может стать проблемой в поколении 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-187">Fragmentation can become a problem in generation 1 and generation 2.</span></span> <span data-ttu-id="bf2e0-188">Если эти поколения имеют большой объем свободного места после сборки мусора, возможно, потребуется внести изменения в использование объекта приложения. Кроме того, может потребоваться пересмотреть время существования долгосрочных объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-188">If these generations have a large amount of free space after a garbage collection, an application's object usage may need modification, and you should consider re-evaluating the lifetime of long-term objects.</span></span>

<span data-ttu-id="bf2e0-189">Чрезмерное закрепление объектов может привести к увеличению фрагментации.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-189">Excessive pinning of objects can increase fragmentation.</span></span> <span data-ttu-id="bf2e0-190">Если наблюдается высокая фрагментация, возможно, закреплено слишком много объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-190">If fragmentation is high, too many objects could have been pinned.</span></span>

<span data-ttu-id="bf2e0-191">Если фрагментация виртуальной памяти препятствует добавлению сегментов сборщиком мусора, возможны следующие причины:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-191">If fragmentation of virtual memory is preventing the garbage collector from adding segments, the causes could be one of the following:</span></span>

- <span data-ttu-id="bf2e0-192">частая загрузка и выгрузка большого числа небольших сборок;</span><span class="sxs-lookup"><span data-stu-id="bf2e0-192">Frequent loading and unloading of many small assemblies.</span></span>

- <span data-ttu-id="bf2e0-193">поддержание слишком большого числа ссылок на COM-объекты при взаимодействии с неуправляемым кодом;</span><span class="sxs-lookup"><span data-stu-id="bf2e0-193">Holding too many references to COM objects when interoperating with unmanaged code.</span></span>

- <span data-ttu-id="bf2e0-194">создание больших временных объектов, что приводит к частому выделению и освобождению сегментов кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-194">Creation of large transient objects, which causes the large object heap to allocate and free heap segments frequently.</span></span>

  <span data-ttu-id="bf2e0-195">При размещении среды CLR приложение может запросить сохранение сегментов сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-195">When hosting the CLR, an application can request that the garbage collector retain its segments.</span></span> <span data-ttu-id="bf2e0-196">Это снижает частоту выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-196">This reduces the frequency of segment allocations.</span></span> <span data-ttu-id="bf2e0-197">Для этого необходимо использовать флаг STARTUP_HOARD_GC_VM в [перечислении STARTUP_FLAGS](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-197">This is accomplished by using the STARTUP_HOARD_GC_VM flag in the [STARTUP_FLAGS Enumeration](../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>

|<span data-ttu-id="bf2e0-198">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-198">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-199">Определите объем свободного пространства в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-199">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)<br /><br /> [<span data-ttu-id="bf2e0-200">Определите количество закрепленных объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-200">Determine the number of pinned objects.</span></span>](#Pinned)|

<span data-ttu-id="bf2e0-201">Если вы считаете, что нет допустимых причин для фрагментации, обратитесь в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-201">If you think that there is no legitimate cause for the fragmentation, contact Microsoft Customer Service and Support.</span></span>

<a name="Issue_LongPauses"></a>

### <a name="issue-garbage-collection-pauses-are-too-long"></a><span data-ttu-id="bf2e0-202">Проблема. Слишком большие интервалы между сборками мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-202">Issue: Garbage Collection Pauses Are Too Long</span></span>

<span data-ttu-id="bf2e0-203">Сборка мусора выполняется в режиме мягкого реального времени, поэтому приложение должно быть способно допускать определенные перерывы.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-203">Garbage collection operates in soft real time, so an application must be able to tolerate some pauses.</span></span> <span data-ttu-id="bf2e0-204">Критерием мягкого реального времени является своевременное завершение 95 % операций.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-204">A criterion for soft real time is that 95% of the operations must finish on time.</span></span>

<span data-ttu-id="bf2e0-205">В ходе параллельной сборки мусора управляемые потоки могут выполняться во время сборки, что означает крайне незначительные перерывы в работе.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-205">In concurrent garbage collection, managed threads are allowed to run during a collection, which means that pauses are very minimal.</span></span>

<span data-ttu-id="bf2e0-206">Эфемерные сборки мусора (поколения 0 и 1) длятся лишь несколько миллисекунд, поэтому уменьшение перерывов обычно нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-206">Ephemeral garbage collections (generations 0 and 1) last only a few milliseconds, so decreasing pauses is usually not feasible.</span></span> <span data-ttu-id="bf2e0-207">Тем не менее, перерывы в сборках поколения 2 можно сократить, изменив шаблон обработки запросов приложения на выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-207">However, you can decrease the pauses in generation 2 collections by changing the pattern of allocation requests by an application.</span></span>

<span data-ttu-id="bf2e0-208">Еще одним, более точным методом является использование [событий трассировки ETW для сборки мусора](../../../docs/framework/performance/garbage-collection-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-208">Another, more accurate, method is to use [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md).</span></span> <span data-ttu-id="bf2e0-209">Затраты времени для сборок можно найти путем добавления разницы отметок времени для последовательности событий.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-209">You can find the timings for collections by adding the time stamp differences for a sequence of events.</span></span> <span data-ttu-id="bf2e0-210">Вся последовательность сборки включает приостановку подсистемы выполнения, собственно сборку мусора и возобновление работы подсистемы выполнения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-210">The whole collection sequence includes suspension of the execution engine, the garbage collection itself, and the resumption of the execution engine.</span></span>

<span data-ttu-id="bf2e0-211">С помощью [уведомлений сборки мусора](../../../docs/standard/garbage-collection/notifications.md) можно определить, когда сервер приступает к сборке поколения 2. Кроме того, с их помощью можно определить, поможет ли маршрутизация запросов на другой сервер решить проблемы, связанные с задержками.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-211">You can use [Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md) to determine whether a server is about to have a generation 2 collection, and whether rerouting requests to another server could ease any problems with pauses.</span></span>

|<span data-ttu-id="bf2e0-212">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-212">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-213">Определите продолжительность сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-213">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)<br /><br /> [<span data-ttu-id="bf2e0-214">Определите, что вызвало сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-214">Determine what caused a garbage collection.</span></span>](#Triggered)|

<a name="Issue_Gen0"></a>

### <a name="issue-generation-0-is-too-big"></a><span data-ttu-id="bf2e0-215">Проблема. Слишком большой размер поколения 0</span><span class="sxs-lookup"><span data-stu-id="bf2e0-215">Issue: Generation 0 Is Too Big</span></span>

<span data-ttu-id="bf2e0-216">Поколение 0 скорее всего имеет большое количество объектов в 64-разрядной системе, особенно если используется сборка мусора на сервере вместо сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-216">Generation 0 is likely to have a larger number of objects on a 64-bit system, especially when you use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="bf2e0-217">Это происходит потому, что пороговое значение запуска сборки мусора для поколения 0 в таких средах выше и объемы сборки поколения 0 могут значительно увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-217">This is because the threshold to trigger a generation 0 garbage collection is higher in these environments, and generation 0 collections can get much bigger.</span></span> <span data-ttu-id="bf2e0-218">Производительность повышается, если приложение выделяет больше памяти перед активацией сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-218">Performance is improved when an application allocates more memory before a garbage collection is triggered.</span></span>

<a name="Issue_HighCPU"></a>

### <a name="issue-cpu-usage-during-a-garbage-collection-is-too-high"></a><span data-ttu-id="bf2e0-219">Проблема. Слишком высокая загрузка ЦП во время сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-219">Issue: CPU Usage During a Garbage Collection Is Too High</span></span>

<span data-ttu-id="bf2e0-220">Во время сборки мусора загрузка ЦП будет высокой,</span><span class="sxs-lookup"><span data-stu-id="bf2e0-220">CPU usage will be high during a garbage collection.</span></span> <span data-ttu-id="bf2e0-221">если на сборку мусора тратится значительное время обработки, количество сборок слишком велико или сборка продолжается слишком долго.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-221">If a significant amount of process time is spent in a garbage collection, the number of collections is too frequent or the collection is lasting too long.</span></span> <span data-ttu-id="bf2e0-222">Чем чаще выполняется выделение памяти для объектов в управляемой куче, тем чаще происходит сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-222">An increased allocation rate of objects on the managed heap causes garbage collection to occur more frequently.</span></span> <span data-ttu-id="bf2e0-223">Уменьшение частоты выделения снижает частоту сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-223">Decreasing the allocation rate reduces the frequency of garbage collections.</span></span>

<span data-ttu-id="bf2e0-224">Частоту выделения можно отслеживать с помощью счетчика производительности `Allocated Bytes/second`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-224">You can monitor allocation rates by using the `Allocated Bytes/second` performance counter.</span></span> <span data-ttu-id="bf2e0-225">Дополнительные сведения см. в разделе [Счетчики производительности в .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-225">For more information, see [Performance Counters in the .NET Framework](../../../docs/framework/debug-trace-profile/performance-counters.md).</span></span>

<span data-ttu-id="bf2e0-226">Длительность сборки определяется в первую очередь количеством объектов, оставшихся после выделения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-226">The duration of a collection is primarily a factor of the number of objects that survive after allocation.</span></span> <span data-ttu-id="bf2e0-227">Сборщик мусора должен пройти большой объем памяти, если требуется выполнить сборку многих объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-227">The garbage collector must go through a large amount of memory if many objects remain to be collected.</span></span> <span data-ttu-id="bf2e0-228">Работа по сжатию оставшихся объектов занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-228">The work to compact the survivors is time-consuming.</span></span> <span data-ttu-id="bf2e0-229">Чтобы определить, сколько объектов было обработано во время сборки, установите точку останова в отладчике в конце сборки мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-229">To determine how many objects were handled during a collection, set a breakpoint in the debugger at the end of a garbage collection for a specified generation.</span></span>

|<span data-ttu-id="bf2e0-230">Проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-230">Performance checks</span></span>|
|------------------------|
|[<span data-ttu-id="bf2e0-231">Определите, вызвана ли высокая загрузка ЦП сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-231">Determine if high CPU usage is caused by garbage collection.</span></span>](#HighCPU)<br /><br /> [<span data-ttu-id="bf2e0-232">Задайте точку останова в конце сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-232">Set a breakpoint at the end of garbage collection.</span></span>](#GenBreak)|

## <a name="troubleshooting-guidelines"></a><span data-ttu-id="bf2e0-233">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="bf2e0-233">Troubleshooting Guidelines</span></span>

<span data-ttu-id="bf2e0-234">В этом разделе приводятся рекомендации, на которые следует опираться при проведении анализа.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-234">This section describes guidelines that you should consider as you begin your investigations.</span></span>

### <a name="workstation-or-server-garbage-collection"></a><span data-ttu-id="bf2e0-235">Сборка мусора на сервере или рабочей станции</span><span class="sxs-lookup"><span data-stu-id="bf2e0-235">Workstation or Server Garbage Collection</span></span>

<span data-ttu-id="bf2e0-236">Убедитесь, что вы используете правильный тип сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-236">Determine if you are using the correct type of garbage collection.</span></span> <span data-ttu-id="bf2e0-237">Если приложение использует несколько потоков и экземпляров объектов, используйте сборку мусора на сервере вместо сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-237">If your application uses multiple threads and object instances, use server garbage collection instead of workstation garbage collection.</span></span> <span data-ttu-id="bf2e0-238">Серверная сборка мусора обрабатывает несколько потоков, тогда как сборка мусора на рабочей станции требует, чтобы несколько экземпляров приложения выполняли собственные потоки сборки мусора, конкурируя за ресурсы процессора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-238">Server garbage collection operates on multiple threads, whereas workstation garbage collection requires multiple instances of an application to run their own garbage collection threads and compete for CPU time.</span></span>

<span data-ttu-id="bf2e0-239">Приложение с низкой нагрузкой, редко выполняющее задачи в фоновом режиме, например служба, может использовать сборку мусора на рабочей станции с отключенной параллельной сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-239">An application that has a low load and that performs tasks infrequently in the background, such as a service, could use workstation garbage collection with concurrent garbage collection disabled.</span></span>

### <a name="when-to-measure-the-managed-heap-size"></a><span data-ttu-id="bf2e0-240">Когда измерять размер управляемой кучи</span><span class="sxs-lookup"><span data-stu-id="bf2e0-240">When to Measure the Managed Heap Size</span></span>

<span data-ttu-id="bf2e0-241">Если вы не используете профилировщик, необходимо создать согласованный шаблон измерений для эффективной диагностики проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-241">Unless you are using a profiler, you will have to establish a consistent measuring pattern to effectively diagnose performance issues.</span></span> <span data-ttu-id="bf2e0-242">При формировании расписания учтите следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-242">Consider the following points to establish a schedule:</span></span>

- <span data-ttu-id="bf2e0-243">Если измерение выполняется после сборки мусора поколения 2, вся куча будет свободна от мусора (неиспользуемых объектов).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-243">If you measure after a generation 2 garbage collection, the entire managed heap will be free of garbage (dead objects).</span></span>

- <span data-ttu-id="bf2e0-244">Если измерение выполняется сразу после сборки мусора поколения 0, объекты в поколении 1 и 2 еще не будут собраны.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-244">If you measure immediately after a generation 0 garbage collection, the objects in generations 1 and 2 will not be collected yet.</span></span>

- <span data-ttu-id="bf2e0-245">Если измерение выполняется сразу же перед сборкой мусора, будет измерено максимально возможное выделение до начала сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-245">If you measure immediately before a garbage collection, you will measure as much allocation as possible before the garbage collection starts.</span></span>

- <span data-ttu-id="bf2e0-246">Измерение во время сборки мусора проблематично, поскольку структуры данных сборщика мусора не находятся в допустимом состоянии для обхода и могут не предоставлять полные результаты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-246">Measuring during a garbage collection is problematic, because the garbage collector data structures are not in a valid state for traversal and may not be able to give you the complete results.</span></span> <span data-ttu-id="bf2e0-247">Это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-247">This is by design.</span></span>

- <span data-ttu-id="bf2e0-248">При использовании сборки мусора на рабочей станции с параллельной сборкой мусора освобожденные объекты не сжимаются, поэтому размер кучи может быть таким же или больше (из-за фрагментации размер может казаться больше).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-248">When you are using workstation garbage collection with concurrent garbage collection, the reclaimed objects are not compacted, so the heap size can be the same or larger (fragmentation can make it appear to be larger).</span></span>

- <span data-ttu-id="bf2e0-249">Параллельная сборка мусора для поколения 2 откладывается, если загрузка физической памяти слишком велика.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-249">Concurrent garbage collection on generation 2 is delayed when the physical memory load is too high.</span></span>

<span data-ttu-id="bf2e0-250">Ниже приведена процедура задания точки останова для измерения управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-250">The following procedure describes how to set a breakpoint so that you can measure the managed heap.</span></span>

<a name="GenBreak"></a>

#### <a name="to-set-a-breakpoint-at-the-end-of-garbage-collection"></a><span data-ttu-id="bf2e0-251">Задание точки останова в конце сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-251">To set a breakpoint at the end of garbage collection</span></span>

- <span data-ttu-id="bf2e0-252">В WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-252">In WinDbg with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="bf2e0-253">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-253">**bp mscorwks!WKS::GCHeap::RestartEE "j (dwo(mscorwks!WKS::GCHeap::GcCondemnedGeneration)==2) 'kb';'g'"**</span></span>

  <span data-ttu-id="bf2e0-254">Где **GcCondemnedGeneration** — желаемое поколение.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-254">where **GcCondemnedGeneration** is set to the desired generation.</span></span> <span data-ttu-id="bf2e0-255">Команда требует закрытых символов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-255">This command requires private symbols.</span></span>

  <span data-ttu-id="bf2e0-256">Эта команда принудительно выполняет останов, если **RestartEE** выполняется после освобождения объектов поколения 2 для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-256">This command forces a break if **RestartEE** is executed after generation 2 objects have been reclaimed for garbage collection.</span></span>

  <span data-ttu-id="bf2e0-257">В серверной сборке мусора только один поток вызывает **RestartEE**, поэтому точка останова будет появляться только один раз во время сборки мусора поколения 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-257">In server garbage collection, only one thread calls **RestartEE**, so the breakpoint will occur only once during a generation 2 garbage collection.</span></span>

## <a name="performance-check-procedures"></a><span data-ttu-id="bf2e0-258">Процедуры проверки производительности</span><span class="sxs-lookup"><span data-stu-id="bf2e0-258">Performance Check Procedures</span></span>

<span data-ttu-id="bf2e0-259">В этом разделе описаны следующие процедуры по выявлению причин проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-259">This section describes the following procedures to isolate the cause of your performance issue:</span></span>

- [<span data-ttu-id="bf2e0-260">Определите, вызвана ли проблема сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-260">Determine whether the problem is caused by garbage collection.</span></span>](#IsGC)

- [<span data-ttu-id="bf2e0-261">Определите, является ли исключение нехватки памяти управляемым.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-261">Determine whether the out-of-memory exception is managed.</span></span>](#OOMIsManaged)

- [<span data-ttu-id="bf2e0-262">Определите, сколько виртуальной памяти можно зарезервировать.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-262">Determine how much virtual memory can be reserved.</span></span>](#GetVM)

- [<span data-ttu-id="bf2e0-263">Определите, имеется ли достаточный объем физической памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-263">Determine whether there is enough physical memory.</span></span>](#Physical)

- [<span data-ttu-id="bf2e0-264">Определите объем памяти, зафиксированный управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-264">Determine how much memory the managed heap is committing.</span></span>](#ManagedHeapCommit)

- [<span data-ttu-id="bf2e0-265">Определите объем памяти, зарезервированный управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-265">Determine how much memory the managed heap reserves.</span></span>](#ManagedHeapReserve)

- [<span data-ttu-id="bf2e0-266">Определите большие объекты в поколении 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-266">Determine large objects in generation 2.</span></span>](#ExamineGen2)

- [<span data-ttu-id="bf2e0-267">Определите ссылки на объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-267">Determine references to objects.</span></span>](#ObjRef)

- [<span data-ttu-id="bf2e0-268">Определите, выполнялся ли метод завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-268">Determine whether a finalizer has been run.</span></span>](#Induce)

- [<span data-ttu-id="bf2e0-269">Определите наличие объектов, ожидающих завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-269">Determine whether there are objects waiting to be finalized.</span></span>](#Finalize)

- [<span data-ttu-id="bf2e0-270">Определите объем свободного пространства в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-270">Determine the amount of free space in the managed heap.</span></span>](#Fragmented)

- [<span data-ttu-id="bf2e0-271">Определите количество закрепленных объектов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-271">Determine the number of pinned objects.</span></span>](#Pinned)

- [<span data-ttu-id="bf2e0-272">Определите продолжительность сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-272">Determine the length of time in a garbage collection.</span></span>](#TimeInGC)

- [<span data-ttu-id="bf2e0-273">Определите, что вызвало сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-273">Determine what triggered a garbage collection.</span></span>](#Triggered)

- [<span data-ttu-id="bf2e0-274">Определите, вызвана ли высокая загрузка ЦП сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-274">Determine whether high CPU usage is caused by garbage collection.</span></span>](#HighCPU)

<a name="IsGC"></a>

### <a name="to-determine-whether-the-problem-is-caused-by-garbage-collection"></a><span data-ttu-id="bf2e0-275">Чтобы определить, вызвана ли проблема сборкой мусора, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-275">To determine whether the problem is caused by garbage collection</span></span>

- <span data-ttu-id="bf2e0-276">Проверьте следующие два счетчика производительности памяти:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-276">Examine the following two memory performance counters:</span></span>

  - <span data-ttu-id="bf2e0-277">**% времени в сборке мусора**.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-277">**% Time in GC**.</span></span> <span data-ttu-id="bf2e0-278">Отображение времени, потраченного на выполнение сборки мусора с момента последнего цикла сборки мусора (в процентах).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-278">Displays the percentage of elapsed time that was spent performing a garbage collection after the last garbage collection cycle.</span></span> <span data-ttu-id="bf2e0-279">Этот счетчик используется, чтобы определить, тратит ли сборщик мусора слишком много времени на освобождение пространства в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-279">Use this counter to determine whether the garbage collector is spending too much time to make managed heap space available.</span></span> <span data-ttu-id="bf2e0-280">Если время, затраченное на сборку мусора, сравнительно мало, это может указывать на проблему ресурсов за пределами управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-280">If the time spent in garbage collection is relatively low, that could indicate a resource problem outside the managed heap.</span></span> <span data-ttu-id="bf2e0-281">Этот счетчик может предоставлять неточные данные при участии параллельной или фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-281">This counter may not be accurate when concurrent or background garbage collection is involved.</span></span>

  - <span data-ttu-id="bf2e0-282">**Всего зафиксировано байт**.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-282">**# Total committed Bytes**.</span></span> <span data-ttu-id="bf2e0-283">Отображение объема виртуальной памяти, в данный момент выделенной сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-283">Displays the amount of virtual memory currently committed by the garbage collector.</span></span> <span data-ttu-id="bf2e0-284">С помощью этого счетчика можно определить, является ли память, используемая сборщиком мусора, избыточной частью памяти, которую использует приложение.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-284">Use this counter to determine whether the memory consumed by the garbage collector is an excessive portion of the memory that your application uses.</span></span>

  <span data-ttu-id="bf2e0-285">Большинство счетчиков памяти обновляются в конце каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-285">Most of the memory performance counters are updated at the end of each garbage collection.</span></span> <span data-ttu-id="bf2e0-286">Таким образом, они могут не отражать текущие условия, сведения о которых вам требуются.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-286">Therefore, they may not reflect the current conditions that you want information about.</span></span>

<a name="OOMIsManaged"></a>

### <a name="to-determine-whether-the-out-of-memory-exception-is-managed"></a><span data-ttu-id="bf2e0-287">Чтобы определить, является ли исключение нехватки памяти управляемым, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-287">To determine whether the out-of-memory exception is managed</span></span>

1. <span data-ttu-id="bf2e0-288">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите команду печати исключения (**pe**).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-288">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the print exception (**pe**) command:</span></span>

    <span data-ttu-id="bf2e0-289">**!pe**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-289">**!pe**</span></span>

    <span data-ttu-id="bf2e0-290">Если исключение является управляемым, <xref:System.OutOfMemoryException> отображается как тип исключения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-290">If the exception is managed, <xref:System.OutOfMemoryException> is displayed as the exception type, as shown in the following example.</span></span>

    ```console
    Exception object: 39594518
    Exception type: System.OutOfMemoryException
    Message: <none>
    InnerException: <none>
    StackTrace (generated):
    ```

2. <span data-ttu-id="bf2e0-291">Если выходные данные не указывают на исключение, необходимо определить, к какому потоку относится исключение нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-291">If the output does not specify an exception, you have to determine which thread the out-of-memory exception is from.</span></span> <span data-ttu-id="bf2e0-292">Для вывода на экран всех потоков со стеками вызовов введите в отладчике следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-292">Type the following command in the debugger to show all the threads with their call stacks:</span></span>

    <span data-ttu-id="bf2e0-293">**~\*kb**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-293">**~\*kb**</span></span>

    <span data-ttu-id="bf2e0-294">Поток со стеком, для которого есть вызовы исключений, обозначается аргументом `RaiseTheException`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-294">The thread with the stack that has exception calls is indicated by the `RaiseTheException` argument.</span></span> <span data-ttu-id="bf2e0-295">Это объект управляемого исключения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-295">This is the managed exception object.</span></span>

    ```console
    28adfb44 7923918f 5b61f2b4 00000000 5b61f2b4 mscorwks!RaiseTheException+0xa0
    ```

3. <span data-ttu-id="bf2e0-296">Чтобы создать дамп вложенных исключений, можно использовать следующую команду.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-296">You can use the following command to dump nested exceptions.</span></span>

    <span data-ttu-id="bf2e0-297">**!pe -nested**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-297">**!pe -nested**</span></span>

    <span data-ttu-id="bf2e0-298">Если исключения не обнаружены, значит исключение нехватки памяти возникло в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-298">If you do not find any exceptions, the out-of-memory exception originated from unmanaged code.</span></span>

<a name="GetVM"></a>

### <a name="to-determine-how-much-virtual-memory-can-be-reserved"></a><span data-ttu-id="bf2e0-299">Чтобы определить, сколько виртуальной памяти можно зарезервировать, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-299">To determine how much virtual memory can be reserved</span></span>

- <span data-ttu-id="bf2e0-300">В WinDbg с загруженным расширением отладчика SOS введите следующую команду, чтобы получить самую крупную свободную область:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-300">In WinDbg with the SOS debugger extension loaded, type the following command to get the largest free region:</span></span>

  <span data-ttu-id="bf2e0-301">**!address -summary**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-301">**!address -summary**</span></span>

  <span data-ttu-id="bf2e0-302">Самая крупная свободная область отображается, как показано в выходных данных команды ниже.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-302">The largest free region is displayed as shown in the following output.</span></span>

  ```console
  Largest free region: Base 54000000 - Size 0003A980
  ```

  <span data-ttu-id="bf2e0-303">В этом примере размер самой крупной свободной области составляет приблизительно 24 000 КБ (3A980 в шестнадцатеричном формате).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-303">In this example, the size of the largest free region is approximately 24000 KB (3A980 in hexadecimal).</span></span> <span data-ttu-id="bf2e0-304">Эта область гораздо меньше, чем требуется сборщику мусора для сегмента.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-304">This region is much smaller than what the garbage collector needs for a segment.</span></span>

  <span data-ttu-id="bf2e0-305">-или-</span><span class="sxs-lookup"><span data-stu-id="bf2e0-305">-or-</span></span>

- <span data-ttu-id="bf2e0-306">Используйте команду **vmstat**:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-306">Use the **vmstat** command:</span></span>

  <span data-ttu-id="bf2e0-307">**!vmstat**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-307">**!vmstat**</span></span>

  <span data-ttu-id="bf2e0-308">Самая крупная свободная область представлена самым большим значением в столбце MAXIMUM, как показано в следующих выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-308">The largest free region is the largest value in the MAXIMUM column, as shown in the following output.</span></span>

  ```console
  TYPE        MINIMUM   MAXIMUM     AVERAGE   BLK COUNT   TOTAL
  ~~~~        ~~~~~~~   ~~~~~~~     ~~~~~~~   ~~~~~~~~~~  ~~~~
  Free:
  Small       8K        64K         46K       36          1,671K
  Medium      80K       864K        349K      3           1,047K
  Large       1,384K    1,278,848K  151,834K  12          1,822,015K
  Summary     8K        1,278,848K  35,779K   51          1,824,735K
  ```

<a name="Physical"></a>

### <a name="to-determine-whether-there-is-enough-physical-memory"></a><span data-ttu-id="bf2e0-309">Чтобы определить, имеется ли достаточный объем физической памяти, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-309">To determine whether there is enough physical memory</span></span>

1. <span data-ttu-id="bf2e0-310">Запустите диспетчер задач Windows.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-310">Start Windows Task Manager.</span></span>

2. <span data-ttu-id="bf2e0-311">На вкладке **Быстродействие** обратите внимание на значение выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-311">On the **Performance** tab, look at the committed value.</span></span> <span data-ttu-id="bf2e0-312">(В Windows 7 это строка **Выделено (КБ)** в группе **Система**.)</span><span class="sxs-lookup"><span data-stu-id="bf2e0-312">(In Windows 7, look at **Commit (KB)** in the **System group**.)</span></span>

    <span data-ttu-id="bf2e0-313">Если значение в строке **Всего** близко к значению **Ограничение**, физической памяти не хватает.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-313">If the **Total** is close to the **Limit**, you are running low on physical memory.</span></span>

<a name="ManagedHeapCommit"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-is-committing"></a><span data-ttu-id="bf2e0-314">Чтобы определить объем памяти, зафиксированный управляемой кучей, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-314">To determine how much memory the managed heap is committing</span></span>

- <span data-ttu-id="bf2e0-315">Используйте счетчик производительности памяти `# Total committed bytes`, чтобы получить число байтов, фиксируемых управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-315">Use the `# Total committed bytes` memory performance counter to get the number of bytes that the managed heap is committing.</span></span> <span data-ttu-id="bf2e0-316">Сборщик мусора выделяет фрагменты в сегменте по мере необходимости, но не все одновременно.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-316">The garbage collector commits chunks on a segment as needed, not all at the same time.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bf2e0-317">Не используйте счетчик производительности `# Bytes in all Heaps`, так как он не отражает фактическое использование памяти управляемой кучей.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-317">Do not use the `# Bytes in all Heaps` performance counter, because it does not represent actual memory usage by the managed heap.</span></span> <span data-ttu-id="bf2e0-318">Размер поколения включается в это значение и, фактически, является его пороговым размером, то есть размером, который вызывает сборку мусора, если поколение заполнено объектами.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-318">The size of a generation is included in this value and is actually its threshold size, that is, the size that induces a garbage collection if the generation is filled with objects.</span></span> <span data-ttu-id="bf2e0-319">Поэтому это значение обычно равно нулю.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-319">Therefore, this value is usually zero.</span></span>

<a name="ManagedHeapReserve"></a>

### <a name="to-determine-how-much-memory-the-managed-heap-reserves"></a><span data-ttu-id="bf2e0-320">Чтобы определить объем памяти, зарезервированный управляемой кучей, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-320">To determine how much memory the managed heap reserves</span></span>

- <span data-ttu-id="bf2e0-321">Используйте счетчик производительности памяти `# Total reserved bytes`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-321">Use the `# Total reserved bytes` memory performance counter.</span></span>

  <span data-ttu-id="bf2e0-322">Сборщик мусора резервирует память сегментами, и определить, где начинается сегмент, можно с помощью команды **eeheap**.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-322">The garbage collector reserves memory in segments, and you can determine where a segment starts by using the **eeheap** command.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="bf2e0-323">Хотя и можно определить объем памяти, выделяемой сборщиком мусора для каждого сегмента, размер сегмента зависит от реализации и может измениться в любое время, в том числе в ходе периодических обновлений.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-323">Although you can determine the amount of memory the garbage collector allocates for each segment, segment size is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="bf2e0-324">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-324">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

- <span data-ttu-id="bf2e0-325">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-325">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="bf2e0-326">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-326">**!eeheap -gc**</span></span>

  <span data-ttu-id="bf2e0-327">Далее приведен результат.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-327">The result is as follows.</span></span>

  ```console
  Number of GC Heaps: 2
  ------------------------------
  Heap 0 (002db550)
  generation 0 starts at 0x02abe29c
  generation 1 starts at 0x02abdd08
  generation 2 starts at 0x02ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  02ab0000 02ab0038  02aceff4 0x0001efbc(126908)
  Large object heap starts at 0x0aab0038
    segment    begin allocated     size
  0aab0000 0aab0038  0aab2278 0x00002240(8768)
  Heap Size   0x211fc(135676)
  ------------------------------
  Heap 1 (002dc958)
  generation 0 starts at 0x06ab1bd8
  generation 1 starts at 0x06ab1bcc
  generation 2 starts at 0x06ab0038
  ephemeral segment allocation context: none
    segment    begin allocated     size
  06ab0000 06ab0038  06ab3be4 0x00003bac(15276)
  Large object heap starts at 0x0cab0038
    segment    begin allocated     size
  0cab0000 0cab0038  0cab0048 0x00000010(16)
  Heap Size    0x3bbc(15292)
  ------------------------------
  GC Heap Size   0x24db8(150968)
  ```

  <span data-ttu-id="bf2e0-328">Адреса с отметкой segment являются начальными адресами сегментов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-328">The addresses indicated by "segment" are the starting addresses of the segments.</span></span>

<a name="ExamineGen2"></a>

### <a name="to-determine-large-objects-in-generation-2"></a><span data-ttu-id="bf2e0-329">Чтобы определить большие объекты в поколении 2, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-329">To determine large objects in generation 2</span></span>

- <span data-ttu-id="bf2e0-330">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-330">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="bf2e0-331">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-331">**!dumpheap –stat**</span></span>

  <span data-ttu-id="bf2e0-332">Если управляемая куча имеет большой размер, выполнение команды **dumpheap** может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-332">If the managed heap is big, **dumpheap** may take a while to finish.</span></span>

  <span data-ttu-id="bf2e0-333">Вы можете начать анализ с последних нескольких строк вывода, поскольку в них перечислены объекты, занимающие наибольшее пространство.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-333">You can start analyzing from the last few lines of the output, because they list the objects that use the most space.</span></span> <span data-ttu-id="bf2e0-334">Пример:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-334">For example:</span></span>

  ```console
  2c6108d4   173712     14591808 DevExpress.XtraGrid.Views.Grid.ViewInfo.GridCellInfo
  00155f80      533     15216804      Free
  7a747c78   791070     15821400 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700930     19626040 System.Collections.Specialized.ListDictionary
  2c64e36c    78644     20762016 DevExpress.XtraEditors.ViewInfo.TextEditViewInfo
  79124228   121143     29064120 System.Object[]
  035f0ee4    81626     35588936 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    40182     90664128 System.Collections.Hashtable+bucket[]
  790fa3e0  3154024    137881448 System.String
  Total 8454945 objects
  ```

  <span data-ttu-id="bf2e0-335">Последний объект в списке является строкой и занимает больше всего места.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-335">The last object listed is a string and occupies the most space.</span></span> <span data-ttu-id="bf2e0-336">Вы можете проанализировать приложение, чтобы понять, как можно оптимизировать строковые объекты.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-336">You can examine your application to see how your string objects can be optimized.</span></span> <span data-ttu-id="bf2e0-337">Чтобы вывести на экран строки в диапазоне от 150 до 200 байтов, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-337">To see strings that are between 150 and 200 bytes, type the following:</span></span>

  <span data-ttu-id="bf2e0-338">**!dumpheap -type System.String -min 150 -max 200**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-338">**!dumpheap -type System.String -min 150 -max 200**</span></span>

  <span data-ttu-id="bf2e0-339">Далее приведен пример результатов команды.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-339">An example of the results is as follows.</span></span>

  ```console
  Address  MT           Size  Gen
  1875d2c0 790fa3e0      152    2 System.String HighlightNullStyle_Blotter_PendingOrder-11_Blotter_PendingOrder-11
  …
  ```

  <span data-ttu-id="bf2e0-340">Использование целого числа вместо строки для идентификаторов может быть более эффективным.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-340">Using an integer instead of a string for an ID can be more efficient.</span></span> <span data-ttu-id="bf2e0-341">Если та же строка повторяется тысячи раз, рекомендуется настроить интернирование строк.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-341">If the same string is being repeated thousands of times, consider string interning.</span></span> <span data-ttu-id="bf2e0-342">Дополнительные сведения об интернировании строк см. в разделе справки по методу <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-342">For more information about string interning, see the reference topic for the <xref:System.String.Intern%2A?displayProperty=nameWithType> method.</span></span>

<a name="ObjRef"></a>

### <a name="to-determine-references-to-objects"></a><span data-ttu-id="bf2e0-343">Чтобы определить ссылки на объекты, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-343">To determine references to objects</span></span>

- <span data-ttu-id="bf2e0-344">В WinDbg с загруженным расширением отладчика SOS введите следующую команду, чтобы получить список ссылок на объекты:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-344">In WinDbg with the SOS debugger extension loaded, type the following command to list references to objects:</span></span>

  <span data-ttu-id="bf2e0-345">**!gcroot**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-345">**!gcroot**</span></span>

  `-or-`

- <span data-ttu-id="bf2e0-346">Чтобы определить ссылки для конкретного объекта, включите соответствующий адрес:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-346">To determine the references for a specific object, include the address:</span></span>

  <span data-ttu-id="bf2e0-347">**!gcroot 1c37b2ac**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-347">**!gcroot 1c37b2ac**</span></span>

  <span data-ttu-id="bf2e0-348">Корни, найденные в стеках, могут быть ложными положительными результатами.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-348">Roots found on stacks may be false positives.</span></span> <span data-ttu-id="bf2e0-349">Чтобы получить дополнительные сведения, используйте команду `!help gcroot`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-349">For more information, use the command `!help gcroot`.</span></span>

  ```console
  ebx:Root:19011c5c(System.Windows.Forms.Application+ThreadContext)->
  19010b78(DemoApp.FormDemoApp)->
  19011158(System.Windows.Forms.PropertyStore)->
  … [omitted]
  1c3745ec(System.Data.DataTable)->
  1c3747a8(System.Data.DataColumnCollection)->
  1c3747f8(System.Collections.Hashtable)->
  1c376590(System.Collections.Hashtable+bucket[])->
  1c376c98(System.Data.DataColumn)->
  1c37b270(System.Data.Common.DoubleStorage)->
  1c37b2ac(System.Double[])
  Scan Thread 0 OSTHread 99c
  Scan Thread 6 OSTHread 484
  ```

  <span data-ttu-id="bf2e0-350">Выполнение команды **gcroot** может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-350">The **gcroot** command can take a long time to finish.</span></span> <span data-ttu-id="bf2e0-351">Любой объект, не освобождаемый сборщиком мусора, является активным объектом.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-351">Any object that is not reclaimed by garbage collection is a live object.</span></span> <span data-ttu-id="bf2e0-352">Это означает, что некоторый корневой объект прямо или опосредованно привязан к данному объекту, поэтому команда **gcroot** должна возвращать сведения о пути к объекту.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-352">This means that some root is directly or indirectly holding onto the object, so **gcroot** should return path information to the object.</span></span> <span data-ttu-id="bf2e0-353">Необходимо изучить возвращенные диаграммы, чтобы понять, на какие объекты по-прежнему имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-353">You should examine the graphs returned and see why these objects are still referenced.</span></span>

<a name="Induce"></a>

### <a name="to-determine-whether-a-finalizer-has-been-run"></a><span data-ttu-id="bf2e0-354">Чтобы определить, выполнялся ли метод завершения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-354">To determine whether a finalizer has been run</span></span>

- <span data-ttu-id="bf2e0-355">Запустите тестовую программу, содержащую следующий код:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-355">Run a test program that contains the following code:</span></span>

  ```csharp
  GC.Collect();
  GC.WaitForPendingFinalizers();
  GC.Collect();
  ```

  <span data-ttu-id="bf2e0-356">Если с помощью теста удалось разрешить проблему, значит сборщик мусора не освобождает объекты, так как методы завершения для этих объектов приостановлены.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-356">If the test resolves the problem, this means that the garbage collector was not reclaiming objects, because the finalizers for those objects had been suspended.</span></span> <span data-ttu-id="bf2e0-357">Метод <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> позволяет методам завершения выполнить свои задачи и устраняет проблему.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-357">The <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method enables the finalizers to complete their tasks, and fixes the problem.</span></span>

<a name="Finalize"></a>

### <a name="to-determine-whether-there-are-objects-waiting-to-be-finalized"></a><span data-ttu-id="bf2e0-358">Чтобы определить наличие объектов, ожидающих завершения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-358">To determine whether there are objects waiting to be finalized</span></span>

1. <span data-ttu-id="bf2e0-359">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-359">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

    <span data-ttu-id="bf2e0-360">**!finalizequeue**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-360">**!finalizequeue**</span></span>

    <span data-ttu-id="bf2e0-361">Проверьте число объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-361">Look at the number of objects that are ready for finalization.</span></span> <span data-ttu-id="bf2e0-362">Если число большое, необходимо выяснить, почему эти методы завершения вообще не могут выполняться или не могут выполняться достаточно быстро.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-362">If the number is high, you must examine why these finalizers cannot progress at all or cannot progress fast enough.</span></span>

2. <span data-ttu-id="bf2e0-363">Для получения выходных данных потоков, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-363">To get an output of threads, type the following command:</span></span>

    <span data-ttu-id="bf2e0-364">**threads -special**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-364">**threads -special**</span></span>

    <span data-ttu-id="bf2e0-365">Эта команда предоставляет примерно следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-365">This command provides output such as the following.</span></span>

    ```console
       OSID     Special thread type
    2    cd0    DbgHelper
    3    c18    Finalizer
    4    df0    GC SuspendEE
    ```

    <span data-ttu-id="bf2e0-366">Поток метода завершения указывает, какой метод завершения (при наличии) выполняется в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-366">The finalizer thread indicates which finalizer, if any, is currently being run.</span></span> <span data-ttu-id="bf2e0-367">Если в потоке метода завершения не выполняются никакие методы завершения, значит он ожидает событие, которое запустит его выполнение.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-367">When a finalizer thread is not running any finalizers, it is waiting for an event to tell it to do its work.</span></span> <span data-ttu-id="bf2e0-368">Как правило, поток находится в этом состоянии, так как выполняется с приоритетом THREAD_HIGHEST_PRIORITY и должен закончить выполнение методов завершения (при наличии) очень быстро.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-368">Most of the time you will see the finalizer thread in this state because it runs at THREAD_HIGHEST_PRIORITY and is supposed to finish running finalizers, if any, very quickly.</span></span>

<a name="Fragmented"></a>

### <a name="to-determine-the-amount-of-free-space-in-the-managed-heap"></a><span data-ttu-id="bf2e0-369">Чтобы определить объем свободного пространства в управляемой куче, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-369">To determine the amount of free space in the managed heap</span></span>

- <span data-ttu-id="bf2e0-370">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-370">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="bf2e0-371">**!dumpheap -type Free -stat**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-371">**!dumpheap -type Free -stat**</span></span>

  <span data-ttu-id="bf2e0-372">Эта команда выводит на экран общий размер всех свободных объектов в управляемой куче, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-372">This command displays the total size of all the free objects on the managed heap, as shown in the following example.</span></span>

  ```console
  total 230 objects
  Statistics:
        MT    Count    TotalSize Class Name
  00152b18      230     40958584      Free
  Total 230 objects
  ```

- <span data-ttu-id="bf2e0-373">Чтобы определить объем свободного места в поколении 0, введите следующую команду, которая выводит сведения о потреблении памяти для каждого поколения:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-373">To determine the free space in generation 0, type the following command for memory consumption information by generation:</span></span>

  <span data-ttu-id="bf2e0-374">**!eeheap -gc**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-374">**!eeheap -gc**</span></span>

  <span data-ttu-id="bf2e0-375">Эта команда выводит примерно следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-375">This command displays output similar to the following.</span></span> <span data-ttu-id="bf2e0-376">В последней строке показан эфемерный сегмент.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-376">The last line shows the ephemeral segment.</span></span>

  ```console
  Heap 0 (0015ad08)
  generation 0 starts at 0x49521f8c
  generation 1 starts at 0x494d7f64
  generation 2 starts at 0x007f0038
  ephemeral segment allocation context: none
  segment  begin     allocated  size
  00178250 7a80d84c  7a82f1cc   0x00021980(137600)
  00161918 78c50e40  78c7056c   0x0001f72c(128812)
  007f0000 007f0038  047eed28   0x03ffecf0(67103984)
  3a120000 3a120038  3a3e84f8   0x002c84c0(2917568)
  46120000 46120038  49e05d04   0x03ce5ccc(63855820)
  ```

- <span data-ttu-id="bf2e0-377">Вычислите пространство, используемое поколением 0:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-377">Calculate the space used by generation 0:</span></span>

  <span data-ttu-id="bf2e0-378">**? 49e05d04-0x49521f8c**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-378">**? 49e05d04-0x49521f8c**</span></span>

  <span data-ttu-id="bf2e0-379">Далее приведен результат.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-379">The result is as follows.</span></span> <span data-ttu-id="bf2e0-380">Поколение 0 занимает приблизительно 9 МБ.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-380">Generation 0 is approximately 9 MB.</span></span>

  ```console
  Evaluate expression: 9321848 = 008e3d78
  ```

- <span data-ttu-id="bf2e0-381">Следующая команда создает дамп свободного места в диапазоне поколения 0:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-381">The following command dumps the free space within the generation 0 range:</span></span>

  <span data-ttu-id="bf2e0-382">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-382">**!dumpheap -type Free -stat 0x49521f8c 49e05d04**</span></span>

  <span data-ttu-id="bf2e0-383">Далее приведен результат.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-383">The result is as follows.</span></span>

  ```console
  ------------------------------
  Heap 0
  total 409 objects
  ------------------------------
  Heap 1
  total 0 objects
  ------------------------------
  Heap 2
  total 0 objects
  ------------------------------
  Heap 3
  total 0 objects
  ------------------------------
  total 409 objects
  Statistics:
        MT    Count TotalSize Class Name
  0015a498      409   7296540      Free
  Total 409 objects
  ```

  <span data-ttu-id="bf2e0-384">Эти выходные данные показывают, что часть кучи поколения 0 использует 9 МБ пространства для объектов, а 7 МБ свободны.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-384">This output shows that the generation 0 portion of the heap is using 9 MB of space for objects and has 7 MB free.</span></span> <span data-ttu-id="bf2e0-385">Этот анализ показывает предел, до которого поколение 0 участвует в фрагментации.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-385">This analysis shows the extent to which generation 0 contributes to fragmentation.</span></span> <span data-ttu-id="bf2e0-386">Этот объем используемой памяти кучи необходимо вычесть из общего объема как причину фрагментации долгосрочными объектами.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-386">This amount of heap usage should be discounted from the total amount as the cause of fragmentation by long-term objects.</span></span>

<a name="Pinned"></a>

### <a name="to-determine-the-number-of-pinned-objects"></a><span data-ttu-id="bf2e0-387">Чтобы определить количество закрепленных объектов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-387">To determine the number of pinned objects</span></span>

- <span data-ttu-id="bf2e0-388">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-388">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command:</span></span>

  <span data-ttu-id="bf2e0-389">**!gchandles**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-389">**!gchandles**</span></span>

  <span data-ttu-id="bf2e0-390">Выводимая на экран статистика включает число закрепленных дескрипторов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-390">The statistics displayed includes the number of pinned handles, as the following example shows.</span></span>

  ```console
  GC Handle Statistics:
  Strong Handles:      29
  Pinned Handles:      10
  ```

<a name="TimeInGC"></a>

### <a name="to-determine-the-length-of-time-in-a-garbage-collection"></a><span data-ttu-id="bf2e0-391">Чтобы определить продолжительность сборки мусора, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-391">To determine the length of time in a garbage collection</span></span>

- <span data-ttu-id="bf2e0-392">Проверьте счетчик производительности памяти `% Time in GC`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-392">Examine the `% Time in GC` memory performance counter.</span></span>

  <span data-ttu-id="bf2e0-393">Значение вычисляется с помощью интервала выборки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-393">The value is calculated by using a sample interval time.</span></span> <span data-ttu-id="bf2e0-394">Поскольку счетчики обновляются в конце каждой сборки мусора, текущая выборка будет иметь то же значение, что и предыдущая, если в течение интервала не будут выполняться сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-394">Because the counters are updated at the end of each garbage collection, the current sample will have the same value as the previous sample if no collections occurred during the interval.</span></span>

  <span data-ttu-id="bf2e0-395">Время сборки вычисляется путем умножения интервала выборки на процентное значение.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-395">Collection time is obtained by multiplying the sample interval time with the percentage value.</span></span>

  <span data-ttu-id="bf2e0-396">В следующих данных показаны четыре интервала выборки продолжительностью две секунды для 8-секундного исследования.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-396">The following data shows four sampling intervals of two seconds, for an 8-second study.</span></span> <span data-ttu-id="bf2e0-397">Столбцы `Gen0`, `Gen1` и `Gen2` показывают количество сборок мусора, выполнявшихся в течение этого интервала для данного поколения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-397">The `Gen0`, `Gen1`, and `Gen2` columns show the number of garbage collections that occurred during that interval for that generation.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2    % Time in GC
          1       9       3       1              10
          2      10       3       1               1
          3      11       3       1               3
          4      11       3       1               3
  ```

  <span data-ttu-id="bf2e0-398">Эти сведения не указывают на момент выполнения сборки мусора, но вы можете определить число сборок, выполнявшихся в определенный интервал.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-398">This information does not show when the garbage collection occurred, but you can determine the number of garbage collections that occurred in an interval of time.</span></span> <span data-ttu-id="bf2e0-399">В худшем случае десятая сборка мусора поколения 0 завершается в начале второго интервала, а одиннадцатая сборка мусора поколения 0 завершается в конце пятого интервала.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-399">Assuming the worst case, the tenth generation 0 garbage collection finished at the start of the second interval, and the eleventh generation 0 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="bf2e0-400">Время между окончанием десятой и одиннадцатой сборок мусора составляет 2 секунды, а счетчик производительности выдает значение 3 %, таким образом длительность одиннадцатой сборки мусора поколения 0 составляет (2 секунды \* 3 % =) 60 мс.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-400">The time between the end of the tenth and the end of the eleventh garbage collection is about 2 seconds, and the performance counter shows 3%, so the duration of the eleventh generation 0 garbage collection was (2 seconds \* 3% = 60ms).</span></span>

  <span data-ttu-id="bf2e0-401">В этом примере приведено 5 периодов.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-401">In this example, there are 5 periods.</span></span>

  ```console
  Interval    Gen0    Gen1    Gen2     % Time in GC
          1       9       3       1                3
          2      10       3       1                1
          3      11       4       2                1
          4      11       4       2                1
          5      11       4       2               20
  ```

  <span data-ttu-id="bf2e0-402">Вторая сборка поколения 2 запускается во время третьего интервала и завершается в пятом интервале.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-402">The second generation 2 garbage collection started during the third interval and finished at the fifth interval.</span></span> <span data-ttu-id="bf2e0-403">В худшем случае последняя сборка мусора поколения 0 завершается в начале второго интервала, а сборка мусора поколения 2 завершается в конце пятого интервала.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-403">Assuming the worst case, the last garbage collection was for a generation 0 collection that finished at the start of the second interval, and the generation 2 garbage collection finished at the end of the fifth interval.</span></span> <span data-ttu-id="bf2e0-404">Таким образом, время между завершением сборки мусора для поколения 0 и завершением сборки мусора для поколения 2 составляет 4 секунды.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-404">Therefore, the time between the end of the generation 0 garbage collection and the end of the generation 2 garbage collection is 4 seconds.</span></span> <span data-ttu-id="bf2e0-405">Поскольку счетчик `% Time in GC` выдает значение 20 %, максимальная длительность сборки мусора поколения 2 могла составлять (4 секунды \* 20 % =) 800 мс.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-405">Because the `% Time in GC` counter is 20%, the maximum amount of time the generation 2 garbage collection could have taken is (4 seconds \* 20% = 800ms).</span></span>

- <span data-ttu-id="bf2e0-406">Кроме того, продолжительность сборки мусора можно определить с помощью [событий ETW для сборки мусора](../../../docs/framework/performance/garbage-collection-etw-events.md), проанализировав данные для выяснения длительности сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-406">Alternatively, you can determine the length of a garbage collection by using [garbage collection ETW events](../../../docs/framework/performance/garbage-collection-etw-events.md), and analyze the information to determine the duration of garbage collection.</span></span>

  <span data-ttu-id="bf2e0-407">Например, следующие данные показывают последовательность событий, возникших во время непараллельной сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-407">For example, the following data shows an event sequence that occurred during a non-concurrent garbage collection.</span></span>

  ```console
  Timestamp    Event name
  513052        GCSuspendEEBegin_V1
  513078        GCSuspendEEEnd
  513090        GCStart_V1
  517890        GCEnd_V1
  517894        GCHeapStats
  517897        GCRestartEEBegin
  517918        GCRestartEEEnd
  ```

  <span data-ttu-id="bf2e0-408">Приостановка управляемого потока заняла 26 мкс (`GCSuspendEEEnd`–`GCSuspendEEBegin_V1`).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-408">Suspending the managed thread took 26us (`GCSuspendEEEnd` – `GCSuspendEEBegin_V1`).</span></span>

  <span data-ttu-id="bf2e0-409">Фактическая сборка мусора заняла 4,8 мс (`GCEnd_V1`–`GCStart_V1`).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-409">The actual garbage collection took 4.8ms (`GCEnd_V1` – `GCStart_V1`).</span></span>

  <span data-ttu-id="bf2e0-410">Возобновление управляемого потока заняло 21 мкс (`GCRestartEEEnd`–`GCRestartEEBegin`).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-410">Resuming the managed threads took 21us (`GCRestartEEEnd` – `GCRestartEEBegin`).</span></span>

  <span data-ttu-id="bf2e0-411">Следующие выходные данные содержат пример фоновой сборки мусора и включают сведения о процессе, потоке и полях событий</span><span class="sxs-lookup"><span data-stu-id="bf2e0-411">The following output provides an example for background garbage collection, and includes the process, thread, and event fields.</span></span> <span data-ttu-id="bf2e0-412">(показаны не все данные).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-412">(Not all data is shown.)</span></span>

  ```console
  timestamp(us)    event name            process    thread    event field
  42504385        GCSuspendEEBegin_V1    Test.exe    4372             1
  42504648        GCSuspendEEEnd         Test.exe    4372
  42504816        GCStart_V1             Test.exe    4372        102019
  42504907        GCStart_V1             Test.exe    4372        102020
  42514170        GCEnd_V1               Test.exe    4372
  42514204        GCHeapStats            Test.exe    4372        102020
  42832052        GCRestartEEBegin       Test.exe    4372
  42832136        GCRestartEEEnd         Test.exe    4372
  63685394        GCSuspendEEBegin_V1    Test.exe    4744             6
  63686347        GCSuspendEEEnd         Test.exe    4744
  63784294        GCRestartEEBegin       Test.exe    4744
  63784407        GCRestartEEEnd         Test.exe    4744
  89931423        GCEnd_V1               Test.exe    4372        102019
  89931464        GCHeapStats            Test.exe    4372
  ```

  <span data-ttu-id="bf2e0-413">Событие `GCStart_V1` на отметке 42504816 указывает на выполнение фоновой сборки мусора, так как последнее поле — `1`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-413">The `GCStart_V1` event at 42504816 indicates that this is a background garbage collection, because the last field is `1`.</span></span> <span data-ttu-id="bf2e0-414">Оно становится сборкой мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-414">This becomes garbage collection No.</span></span> <span data-ttu-id="bf2e0-415">102019.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-415">102019.</span></span>

  <span data-ttu-id="bf2e0-416">Событие `GCStart` возникает из-за необходимости выполнить эфемерную сборку мусора до запуска фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-416">The `GCStart` event occurs because there is a need for an ephemeral garbage collection before you start a background garbage collection.</span></span> <span data-ttu-id="bf2e0-417">Оно становится сборкой мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-417">This becomes garbage collection No.</span></span> <span data-ttu-id="bf2e0-418">102020.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-418">102020.</span></span>

  <span data-ttu-id="bf2e0-419">На отметке 42514170 завершается выполнение сборки мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-419">At 42514170, garbage collection No.</span></span> <span data-ttu-id="bf2e0-420">102020.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-420">102020 finishes.</span></span> <span data-ttu-id="bf2e0-421">На этом этапе перезапускаются управляемые потоки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-421">The managed threads are restarted at this point.</span></span> <span data-ttu-id="bf2e0-422">Это действие выполняется для потока 4372, активировавшего эту фоновую сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-422">This is completed on thread 4372, which triggered this background garbage collection.</span></span>

  <span data-ttu-id="bf2e0-423">Для потока 4744 происходит приостановка.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-423">On thread 4744, a suspension occurs.</span></span> <span data-ttu-id="bf2e0-424">Это единственный случай, когда фоновой сборке мусора приходится приостанавливать управляемые потоки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-424">This is the only time at which the background garbage collection has to suspend managed threads.</span></span> <span data-ttu-id="bf2e0-425">Продолжительность приостановки составляет примерно 99 мс ((63784407-63685394)/1000).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-425">This duration is approximately 99ms ((63784407-63685394)/1000).</span></span>

  <span data-ttu-id="bf2e0-426">Событие `GCEnd` для фоновой сборки мусора находится на отметке 89931423.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-426">The `GCEnd` event for the background garbage collection is at 89931423.</span></span> <span data-ttu-id="bf2e0-427">Это означает, что фоновая сборка мусора продолжалась около 47 секунд ((89931423-42504816)/1000).</span><span class="sxs-lookup"><span data-stu-id="bf2e0-427">This means that the background garbage collection lasted for about 47seconds ((89931423-42504816)/1000).</span></span>

  <span data-ttu-id="bf2e0-428">Во время выполнения управляемых потоков можно наблюдать любое количество эфемерных сборок мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-428">While the managed threads are running, you can see any number of ephemeral garbage collections occurring.</span></span>

<a name="Triggered"></a>

### <a name="to-determine-what-triggered-a-garbage-collection"></a><span data-ttu-id="bf2e0-429">Чтобы определить, что активировало сборку мусора, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-429">To determine what triggered a garbage collection</span></span>

- <span data-ttu-id="bf2e0-430">В отладчике Visual Studio или WinDbg с загруженным расширением отладчика SOS введите следующую команду, чтобы вывести на экран все потоки со стеками вызовов:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-430">In the WinDbg or Visual Studio debugger with the SOS debugger extension loaded, type the following command to show all the threads with their call stacks:</span></span>

  <span data-ttu-id="bf2e0-431">**~\*kb**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-431">**~\*kb**</span></span>

  <span data-ttu-id="bf2e0-432">Эта команда выводит примерно следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-432">This command displays output similar to the following.</span></span>

  ```console
  0012f3b0 79ff0bf8 mscorwks!WKS::GCHeap::GarbageCollect
  0012f454 30002894 mscorwks!GCInterface::CollectGeneration+0xa4
  0012f490 79fa22bd fragment_ni!request.Main(System.String[])+0x48
  ```

  <span data-ttu-id="bf2e0-433">Если сборка мусора была вызвана уведомлением о нехватке памяти от операционной системы, стек вызовов аналогичен за исключением того, что поток является потоком метода завершения.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-433">If the garbage collection was caused by a low memory notification from the operating system, the call stack is similar, except that the thread is the finalizer thread.</span></span> <span data-ttu-id="bf2e0-434">Поток метода завершения получает асинхронное уведомление о нехватке памяти и запускает сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-434">The finalizer thread gets an asynchronous low memory notification and induces the garbage collection.</span></span>

  <span data-ttu-id="bf2e0-435">Если сборка мусора вызвана выделением памяти, стек будет следующим:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-435">If the garbage collection was caused by memory allocation, the stack appears as follows:</span></span>

  ```console
  0012f230 7a07c551 mscorwks!WKS::GCHeap::GarbageCollectGeneration
  0012f2b8 7a07cba8 mscorwks!WKS::gc_heap::try_allocate_more_space+0x1a1
  0012f2d4 7a07cefb mscorwks!WKS::gc_heap::allocate_more_space+0x18
  0012f2f4 7a02a51b mscorwks!WKS::GCHeap::Alloc+0x4b
  0012f310 7a02ae4c mscorwks!Alloc+0x60
  0012f364 7a030e46 mscorwks!FastAllocatePrimitiveArray+0xbd
  0012f424 300027f4 mscorwks!JIT_NewArr1+0x148
  000af70f 3000299f fragment_ni!request..ctor(Int32, Single)+0x20c
  0000002a 79fa22bd fragment_ni!request.Main(System.String[])+0x153
  ```

  <span data-ttu-id="bf2e0-436">Вспомогательный JIT-объект (`JIT_New*`) в конечном итоге вызывает `GCHeap::GarbageCollectGeneration`.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-436">A just-in-time helper (`JIT_New*`) eventually calls `GCHeap::GarbageCollectGeneration`.</span></span> <span data-ttu-id="bf2e0-437">Если выяснилось, что сборки мусора поколения 2 вызываются выделением памяти, необходимо определить, какие объекты собираются при сборке мусора поколения 2, и постараться избежать их.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-437">If you determine that generation 2 garbage collections are caused by allocations, you must determine which objects are collected by a generation 2 garbage collection and how to avoid them.</span></span> <span data-ttu-id="bf2e0-438">То есть необходимо определить разницу между началом и концом сборки мусора поколения 2 и выяснить, какие объекты, вызвали сборку мусора поколения 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-438">That is, you want to determine the difference between the start and the end of a generation 2 garbage collection, and the objects that caused the generation 2 collection.</span></span>

  <span data-ttu-id="bf2e0-439">Например, введите в отладчике следующую команду, чтобы вывести на экран время начала сборки поколения 2:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-439">For example, type the following command in the debugger to show the beginning of a generation 2 collection:</span></span>

  <span data-ttu-id="bf2e0-440">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-440">**!dumpheap –stat**</span></span>

  <span data-ttu-id="bf2e0-441">Пример выходных данных (сокращено для отображения объектов, использующих наибольшее пространство):</span><span class="sxs-lookup"><span data-stu-id="bf2e0-441">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    31857      9862328 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  00155f80    21248     12256296      Free
  79103b6c   297003     13068132 System.Threading.ReaderWriterLock
  7a747ad4   708732     14174640 System.Collections.Specialized.HybridDictionary
  7a747c78   786498     15729960 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  035f0ee4    89192     38887712 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  7912c444    91616     71887080 System.Double[]
  791242ec    32451     82462728 System.Collections.Hashtable+bucket[]
  790fa3e0  2459154    112128436 System.String
  Total 6471774 objects
  ```

  <span data-ttu-id="bf2e0-442">Повторите команду в конце сборки поколения 2:</span><span class="sxs-lookup"><span data-stu-id="bf2e0-442">Repeat the command at the end of generation 2:</span></span>

  <span data-ttu-id="bf2e0-443">**!dumpheap –stat**</span><span class="sxs-lookup"><span data-stu-id="bf2e0-443">**!dumpheap –stat**</span></span>

  <span data-ttu-id="bf2e0-444">Пример выходных данных (сокращено для отображения объектов, использующих наибольшее пространство):</span><span class="sxs-lookup"><span data-stu-id="bf2e0-444">Example output (abridged to show the objects that use the most space):</span></span>

  ```console
  79124228    26648      9314256 System.Object[]
  035f0384    25668     11601936 Toolkit.TlkPosition
  79103b6c   296770     13057880 System.Threading.ReaderWriterLock
  7a747ad4   708730     14174600 System.Collections.Specialized.HybridDictionary
  7a747c78   786497     15729940 System.Collections.Specialized.ListDictionary+DictionaryNode
  7a747bac   700298     19608344 System.Collections.Specialized.ListDictionary
  00155f80    13806     34007212      Free
  035f0ee4    89187     38885532 Toolkit.TlkOrder
  00fcae40     6193     44911636 WaveBasedStrategy.Tick_Snap[]
  791242ec    32370     82359768 System.Collections.Hashtable+bucket[]
  790fa3e0  2440020    111341808 System.String
  Total 6417525 objects
  ```

  <span data-ttu-id="bf2e0-445">Объекты `double[]` больше не отображаются в конце списка выходных данных, что означает, что они были собраны.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-445">The `double[]` objects disappeared from the end of the output, which means that they were collected.</span></span> <span data-ttu-id="bf2e0-446">На эти объекты приходится приблизительно 70 МБ.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-446">These objects account for approximately 70 MB.</span></span> <span data-ttu-id="bf2e0-447">Остальные объекты не сильно изменились.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-447">The remaining objects did not change much.</span></span> <span data-ttu-id="bf2e0-448">Следовательно, эти объекты `double[]` были причиной выполнения этой сборки мусора поколения 2.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-448">Therefore, these `double[]` objects were the reason why this generation 2 garbage collection occurred.</span></span> <span data-ttu-id="bf2e0-449">Затем вам потребуется выяснить, почему объекты `double[]` попали в сборку и почему они перестали использоваться.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-449">Your next step is to determine why the `double[]` objects are there and why they died.</span></span> <span data-ttu-id="bf2e0-450">Происхождение этих объектов можно узнать от разработчика или с помощью команды **gcroot**.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-450">You can ask the code developer where these objects came from, or you can use the **gcroot** command.</span></span>

<a name="HighCPU"></a>

### <a name="to-determine-whether-high-cpu-usage-is-caused-by-garbage-collection"></a><span data-ttu-id="bf2e0-451">Чтобы определить, вызвана ли высокая загрузка ЦП сборкой мусора, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-451">To determine whether high CPU usage is caused by garbage collection</span></span>

- <span data-ttu-id="bf2e0-452">Сопоставьте значение счетчика производительности памяти `% Time in GC` с временем обработки.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-452">Correlate the `% Time in GC` memory performance counter value with the process time.</span></span>

  <span data-ttu-id="bf2e0-453">Если значение `% Time in GC` резко возрастает одновременно с временем обработки, значит сборка мусора вызывает высокую загрузку ЦП.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-453">If the `% Time in GC` value spikes at the same time as process time, garbage collection is causing a high CPU usage.</span></span> <span data-ttu-id="bf2e0-454">В противном случае выполните профилирование приложения, чтобы определить, где возникает высокая загрузка.</span><span class="sxs-lookup"><span data-stu-id="bf2e0-454">Otherwise, profile the application to find where the high usage is occurring.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf2e0-455">См. также</span><span class="sxs-lookup"><span data-stu-id="bf2e0-455">See also</span></span>

- [<span data-ttu-id="bf2e0-456">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="bf2e0-456">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
