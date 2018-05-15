---
title: События сборки мусора (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13f7e935ab999ccc3cd3ea1e308e8d686bed4171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="ea4a2-102">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="ea4a2-103">Эти события собирают сведения, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="ea4a2-104">Они помогают при диагностике и отладке, в том числе позволяют определить, сколько раз осуществлялась сборка мусора, какой объем памяти был освобожден в ходе сборки мусора и т. д.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="ea4a2-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="ea4a2-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="ea4a2-106">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="ea4a2-107">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="ea4a2-108">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="ea4a2-109">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="ea4a2-110">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="ea4a2-111">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="ea4a2-112">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="ea4a2-113">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="ea4a2-114">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="ea4a2-115">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="ea4a2-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="ea4a2-116">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="ea4a2-117">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="ea4a2-118">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="ea4a2-119">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="ea4a2-120">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-121">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="ea4a2-122">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="ea4a2-123">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-123">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-124">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-126">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-127">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-128">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-128">Event</span></span>|<span data-ttu-id="ea4a2-129">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-129">Event ID</span></span>|<span data-ttu-id="ea4a2-130">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="ea4a2-131">1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-131">1</span></span>|<span data-ttu-id="ea4a2-132">Сборка мусора начата.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="ea4a2-133">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-134">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-134">Field name</span></span>|<span data-ttu-id="ea4a2-135">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-135">Data type</span></span>|<span data-ttu-id="ea4a2-136">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-137">Количество</span><span class="sxs-lookup"><span data-stu-id="ea4a2-137">Count</span></span>|<span data-ttu-id="ea4a2-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-138">win:UInt32</span></span>|<span data-ttu-id="ea4a2-139">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="ea4a2-140">Глубина</span><span class="sxs-lookup"><span data-stu-id="ea4a2-140">Depth</span></span>|<span data-ttu-id="ea4a2-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-141">win:UInt32</span></span>|<span data-ttu-id="ea4a2-142">Поколение, для которого выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="ea4a2-143">Причина</span><span class="sxs-lookup"><span data-stu-id="ea4a2-143">Reason</span></span>|<span data-ttu-id="ea4a2-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-144">win:UInt32</span></span>|<span data-ttu-id="ea4a2-145">Причина запуска сборки мусора:</span><span class="sxs-lookup"><span data-stu-id="ea4a2-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="ea4a2-146">0x0 — выделение кучи маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="ea4a2-147">0x1 — принудительная.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="ea4a2-148">0x2 — недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="ea4a2-149">0x3 — пусто.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="ea4a2-150">0x4 — выделение кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="ea4a2-151">0x5 — недостаточно места (для кучи маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="ea4a2-152">0x6 — недостаточно места (для кучи больших объектов).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="ea4a2-153">0x7 — принудительная, но не блокирующий.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="ea4a2-154">Тип</span><span class="sxs-lookup"><span data-stu-id="ea4a2-154">Type</span></span>|<span data-ttu-id="ea4a2-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-155">win:UInt32</span></span>|<span data-ttu-id="ea4a2-156">0x0 — блокировка сборки мусора вне фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="ea4a2-157">0x1 — фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="ea4a2-158">0x2 — блокировка сборки мусора в ходе фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="ea4a2-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-159">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-160">win:UInt16</span></span>|<span data-ttu-id="ea4a2-161">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-162">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="ea4a2-163">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-164">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-165">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-165">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-166">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-168">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-169">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-170">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-170">Event</span></span>|<span data-ttu-id="ea4a2-171">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-171">Event ID</span></span>|<span data-ttu-id="ea4a2-172">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="ea4a2-173">2</span><span class="sxs-lookup"><span data-stu-id="ea4a2-173">2</span></span>|<span data-ttu-id="ea4a2-174">Сборка мусора закончена.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="ea4a2-175">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-176">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-176">Field name</span></span>|<span data-ttu-id="ea4a2-177">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-177">Data type</span></span>|<span data-ttu-id="ea4a2-178">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-179">Количество</span><span class="sxs-lookup"><span data-stu-id="ea4a2-179">Count</span></span>|<span data-ttu-id="ea4a2-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-180">win:UInt32</span></span>|<span data-ttu-id="ea4a2-181">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="ea4a2-182">Глубина</span><span class="sxs-lookup"><span data-stu-id="ea4a2-182">Depth</span></span>|<span data-ttu-id="ea4a2-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-183">win:UInt32</span></span>|<span data-ttu-id="ea4a2-184">Поколение, для которого выполнялась сборка.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="ea4a2-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-185">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-186">win:UInt16</span></span>|<span data-ttu-id="ea4a2-187">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-188">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="ea4a2-189">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-190">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-191">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-191">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-192">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-194">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-195">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-196">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-196">Event</span></span>|<span data-ttu-id="ea4a2-197">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-197">Event ID</span></span>|<span data-ttu-id="ea4a2-198">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="ea4a2-199">4</span><span class="sxs-lookup"><span data-stu-id="ea4a2-199">4</span></span>|<span data-ttu-id="ea4a2-200">Показывает статистику кучи по завершении каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="ea4a2-201">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-202">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-202">Field name</span></span>|<span data-ttu-id="ea4a2-203">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-203">Data type</span></span>|<span data-ttu-id="ea4a2-204">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="ea4a2-205">GenerationSize0</span></span>|<span data-ttu-id="ea4a2-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-206">win:UInt64</span></span>|<span data-ttu-id="ea4a2-207">Размер области памяти поколения 0 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="ea4a2-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="ea4a2-208">TotalPromotedSize0</span></span>|<span data-ttu-id="ea4a2-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-209">win:UInt64</span></span>|<span data-ttu-id="ea4a2-210">Число байт, которые были переданы из поколения 0 в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="ea4a2-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-211">GenerationSize1</span></span>|<span data-ttu-id="ea4a2-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-212">win:UInt64</span></span>|<span data-ttu-id="ea4a2-213">Размер области памяти поколения 1 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="ea4a2-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-214">TotalPromotedSize1</span></span>|<span data-ttu-id="ea4a2-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-215">win:UInt64</span></span>|<span data-ttu-id="ea4a2-216">Число байт, которые были переданы из поколения 1 в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="ea4a2-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="ea4a2-217">GenerationSize2</span></span>|<span data-ttu-id="ea4a2-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-218">win:UInt64</span></span>|<span data-ttu-id="ea4a2-219">Размер области памяти поколения 2 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="ea4a2-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="ea4a2-220">TotalPromotedSize2</span></span>|<span data-ttu-id="ea4a2-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-221">win:UInt64</span></span>|<span data-ttu-id="ea4a2-222">Число байт, оставшихся в поколении 2 после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="ea4a2-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="ea4a2-223">GenerationSize3</span></span>|<span data-ttu-id="ea4a2-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-224">win:UInt64</span></span>|<span data-ttu-id="ea4a2-225">Размер кучи больших объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="ea4a2-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="ea4a2-226">TotalPromotedSize3</span></span>|<span data-ttu-id="ea4a2-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-227">win:UInt64</span></span>|<span data-ttu-id="ea4a2-228">Число байт, оставшихся в куче больших объектов после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="ea4a2-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="ea4a2-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="ea4a2-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-230">win:UInt64</span></span>|<span data-ttu-id="ea4a2-231">Общий размер (в байтах) объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="ea4a2-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="ea4a2-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="ea4a2-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-233">win:UInt64</span></span>|<span data-ttu-id="ea4a2-234">Количество объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="ea4a2-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="ea4a2-235">PinnedObjectCount</span></span>|<span data-ttu-id="ea4a2-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-236">win:UInt32</span></span>|<span data-ttu-id="ea4a2-237">Количество закрепленных (неподвижных) объектов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="ea4a2-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="ea4a2-238">SinkBlockCount</span></span>|<span data-ttu-id="ea4a2-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-239">win:UInt32</span></span>|<span data-ttu-id="ea4a2-240">Количество используемых блоков синхронизации.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="ea4a2-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="ea4a2-241">GCHandleCount</span></span>|<span data-ttu-id="ea4a2-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-242">win:UInt32</span></span>|<span data-ttu-id="ea4a2-243">Число используемых дескрипторов сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="ea4a2-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-244">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-245">win:UInt16</span></span>|<span data-ttu-id="ea4a2-246">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-247">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="ea4a2-248">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-249">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-250">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-250">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-251">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-253">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-254">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-255">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-255">Event</span></span>|<span data-ttu-id="ea4a2-256">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-256">Event ID</span></span>|<span data-ttu-id="ea4a2-257">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="ea4a2-258">5</span><span class="sxs-lookup"><span data-stu-id="ea4a2-258">5</span></span>|<span data-ttu-id="ea4a2-259">Был создан новый сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="ea4a2-260">Кроме того, при включении трассировки для уже работающего процесса это событие создается для каждого существующего сегмента.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="ea4a2-261">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-262">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-262">Field name</span></span>|<span data-ttu-id="ea4a2-263">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-263">Data type</span></span>|<span data-ttu-id="ea4a2-264">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-265">Адрес</span><span class="sxs-lookup"><span data-stu-id="ea4a2-265">Address</span></span>|<span data-ttu-id="ea4a2-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-266">win:UInt64</span></span>|<span data-ttu-id="ea4a2-267">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-267">The address of the segment.</span></span>|  
|<span data-ttu-id="ea4a2-268">Размер</span><span class="sxs-lookup"><span data-stu-id="ea4a2-268">Size</span></span>|<span data-ttu-id="ea4a2-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-269">win:UInt64</span></span>|<span data-ttu-id="ea4a2-270">Размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-270">The size of the segment.</span></span>|  
|<span data-ttu-id="ea4a2-271">Тип</span><span class="sxs-lookup"><span data-stu-id="ea4a2-271">Type</span></span>|<span data-ttu-id="ea4a2-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-272">win:UInt32</span></span>|<span data-ttu-id="ea4a2-273">0x0 — куча маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="ea4a2-274">0x1 — куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="ea4a2-275">0x2 — куча только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="ea4a2-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-276">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-277">win:UInt16</span></span>|<span data-ttu-id="ea4a2-278">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="ea4a2-279">Обратите внимание, что размер сегментов, выделенных сборщиком мусора, зависит от реализации и может быть изменен в любое время, в том числе при периодических обновлениях.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="ea4a2-280">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="ea4a2-281">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="ea4a2-282">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-283">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-284">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-284">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-285">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-287">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-288">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-289">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-289">Event</span></span>|<span data-ttu-id="ea4a2-290">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-290">Event ID</span></span>|<span data-ttu-id="ea4a2-291">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="ea4a2-292">6</span><span class="sxs-lookup"><span data-stu-id="ea4a2-292">6</span></span>|<span data-ttu-id="ea4a2-293">Сегмент сборки мусора был освобожден.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="ea4a2-294">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-295">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-295">Field name</span></span>|<span data-ttu-id="ea4a2-296">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-296">Data type</span></span>|<span data-ttu-id="ea4a2-297">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-298">Адрес</span><span class="sxs-lookup"><span data-stu-id="ea4a2-298">Address</span></span>|<span data-ttu-id="ea4a2-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-299">win:UInt64</span></span>|<span data-ttu-id="ea4a2-300">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-300">The address of the segment.</span></span>|  
|<span data-ttu-id="ea4a2-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-301">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-302">win:UInt16</span></span>|<span data-ttu-id="ea4a2-303">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-304">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="ea4a2-305">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-306">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-307">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-307">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-308">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-310">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-311">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-312">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-312">Event</span></span>|<span data-ttu-id="ea4a2-313">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-313">Event ID</span></span>|<span data-ttu-id="ea4a2-314">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="ea4a2-315">7</span><span class="sxs-lookup"><span data-stu-id="ea4a2-315">7</span></span>|<span data-ttu-id="ea4a2-316">Началось возобновление приостановленной среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="ea4a2-317">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-317">No event data.</span></span>  
  
 [<span data-ttu-id="ea4a2-318">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="ea4a2-319">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-320">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-321">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-321">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-322">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-324">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-325">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-326">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-326">Event</span></span>|<span data-ttu-id="ea4a2-327">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-327">Event Id</span></span>|<span data-ttu-id="ea4a2-328">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="ea4a2-329">3</span><span class="sxs-lookup"><span data-stu-id="ea4a2-329">3</span></span>|<span data-ttu-id="ea4a2-330">Возобновление приостановленной среды CLR завершено.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="ea4a2-331">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-331">No event data.</span></span>  
  
 [<span data-ttu-id="ea4a2-332">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="ea4a2-333">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-334">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-335">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-335">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-336">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-338">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-339">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-340">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-340">Event</span></span>|<span data-ttu-id="ea4a2-341">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-341">Event ID</span></span>|<span data-ttu-id="ea4a2-342">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="ea4a2-343">9</span><span class="sxs-lookup"><span data-stu-id="ea4a2-343">9</span></span>|<span data-ttu-id="ea4a2-344">Началась приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="ea4a2-345">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-346">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-346">Field name</span></span>|<span data-ttu-id="ea4a2-347">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-347">Data type</span></span>|<span data-ttu-id="ea4a2-348">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-349">Причина</span><span class="sxs-lookup"><span data-stu-id="ea4a2-349">Reason</span></span>|<span data-ttu-id="ea4a2-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-350">win:UInt16</span></span>|<span data-ttu-id="ea4a2-351">0x0 — другое.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="ea4a2-352">0x1 — сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="ea4a2-353">0x2 — завершение работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="ea4a2-354">0x3 — свертка кода.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="ea4a2-355">0x4 — завершение работы.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="ea4a2-356">0x5 — отладчик.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="ea4a2-357">0x6 — подготовка к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="ea4a2-358">Количество</span><span class="sxs-lookup"><span data-stu-id="ea4a2-358">Count</span></span>|<span data-ttu-id="ea4a2-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-359">win:UInt32</span></span>|<span data-ttu-id="ea4a2-360">Счетчик сборки мусора на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-360">The GC count at the time.</span></span> <span data-ttu-id="ea4a2-361">Обычно после этого отображается последующее событие запуска сборки мусора, а значение увеличивается на 1 в соответствии с увеличением индекса сборки мусора в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="ea4a2-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-362">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-363">win:UInt16</span></span>|<span data-ttu-id="ea4a2-364">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-365">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="ea4a2-366">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-367">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="ea4a2-368">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-368">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-369">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-371">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-372">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="ea4a2-373">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-373">Event</span></span>|<span data-ttu-id="ea4a2-374">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-374">Event ID</span></span>|<span data-ttu-id="ea4a2-375">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="ea4a2-376">8</span><span class="sxs-lookup"><span data-stu-id="ea4a2-376">8</span></span>|<span data-ttu-id="ea4a2-377">Завершена приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="ea4a2-378">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-378">No event data.</span></span>  
  
 [<span data-ttu-id="ea4a2-379">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="ea4a2-380">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="ea4a2-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="ea4a2-381">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-382">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-382">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-383">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-385">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-386">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-387">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-387">Event</span></span>|<span data-ttu-id="ea4a2-388">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-388">Event ID</span></span>|<span data-ttu-id="ea4a2-389">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="ea4a2-390">10</span><span class="sxs-lookup"><span data-stu-id="ea4a2-390">10</span></span>|<span data-ttu-id="ea4a2-391">Каждый раз выделяется около 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="ea4a2-392">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-393">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-393">Field name</span></span>|<span data-ttu-id="ea4a2-394">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-394">Data type</span></span>|<span data-ttu-id="ea4a2-395">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="ea4a2-396">AllocationAmount</span></span>|<span data-ttu-id="ea4a2-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-397">win:UInt32</span></span>|<span data-ttu-id="ea4a2-398">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-398">The allocation size, in bytes.</span></span> <span data-ttu-id="ea4a2-399">Это значение является точным для выделений, размер которых меньше длины ULONG (4 294 967 295 байт).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="ea4a2-400">Если выделение больше, это поле содержит усеченное значение.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="ea4a2-401">Используйте `AllocationAmount64` для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="ea4a2-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="ea4a2-402">AllocationKind</span></span>|<span data-ttu-id="ea4a2-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-403">win:UInt32</span></span>|<span data-ttu-id="ea4a2-404">0x0 — выделение для маленького объекта (выделение в куче маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="ea4a2-405">0x1 — выделение для большого объекта (выделение в куче больших объектов).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="ea4a2-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-406">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-407">win:UInt16</span></span>|<span data-ttu-id="ea4a2-408">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="ea4a2-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-409">AllocationAmount64</span></span>|<span data-ttu-id="ea4a2-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ea4a2-410">win:UInt64</span></span>|<span data-ttu-id="ea4a2-411">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-411">The allocation size, in bytes.</span></span> <span data-ttu-id="ea4a2-412">Это значение является точным для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="ea4a2-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="ea4a2-413">TypeId</span></span>|<span data-ttu-id="ea4a2-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="ea4a2-414">win:Pointer</span></span>|<span data-ttu-id="ea4a2-415">Адрес MethodTable.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-415">The address of the MethodTable.</span></span> <span data-ttu-id="ea4a2-416">Если в ходе этого события было выделено несколько типов объектов, указывается адрес MethodTable, соответствующий последнему выделенному объекту (объекту, вызвавшему превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="ea4a2-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="ea4a2-417">TypeName</span></span>|<span data-ttu-id="ea4a2-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ea4a2-418">win:UnicodeString</span></span>|<span data-ttu-id="ea4a2-419">Имя выделенного типа.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-419">The name of the type that was allocated.</span></span> <span data-ttu-id="ea4a2-420">Если в ходе этого события было выделено несколько типов объектов, указывается тип последнего выделенного объекта (объекта, вызвавшего превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="ea4a2-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="ea4a2-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="ea4a2-421">HeapIndex</span></span>|<span data-ttu-id="ea4a2-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-422">win:UInt32</span></span>|<span data-ttu-id="ea4a2-423">Куча, в которой был выделен объект.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-423">The heap where the object was allocated.</span></span> <span data-ttu-id="ea4a2-424">Это значение равно 0 (нулю) при выполнении сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="ea4a2-425">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="ea4a2-426">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-427">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-428">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-428">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-429">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-431">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-432">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-433">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-433">Event</span></span>|<span data-ttu-id="ea4a2-434">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-434">Event ID</span></span>|<span data-ttu-id="ea4a2-435">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="ea4a2-436">14</span><span class="sxs-lookup"><span data-stu-id="ea4a2-436">14</span></span>|<span data-ttu-id="ea4a2-437">Начало выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="ea4a2-438">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-438">No event data.</span></span>  
  
 [<span data-ttu-id="ea4a2-439">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="ea4a2-440">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-441">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-442">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-442">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-443">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-445">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-446">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-447">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-447">Event</span></span>|<span data-ttu-id="ea4a2-448">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-448">Event ID</span></span>|<span data-ttu-id="ea4a2-449">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="ea4a2-450">13</span><span class="sxs-lookup"><span data-stu-id="ea4a2-450">13</span></span>|<span data-ttu-id="ea4a2-451">Завершение выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="ea4a2-452">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ea4a2-453">Имя поля</span><span class="sxs-lookup"><span data-stu-id="ea4a2-453">Field name</span></span>|<span data-ttu-id="ea4a2-454">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ea4a2-454">Data type</span></span>|<span data-ttu-id="ea4a2-455">Описание</span><span class="sxs-lookup"><span data-stu-id="ea4a2-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ea4a2-456">Количество</span><span class="sxs-lookup"><span data-stu-id="ea4a2-456">Count</span></span>|<span data-ttu-id="ea4a2-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ea4a2-457">win:UInt32</span></span>|<span data-ttu-id="ea4a2-458">Число выполненных методов завершения.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="ea4a2-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ea4a2-459">ClrInstanceID</span></span>|<span data-ttu-id="ea4a2-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ea4a2-460">win:UInt16</span></span>|<span data-ttu-id="ea4a2-461">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ea4a2-462">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="ea4a2-463">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-464">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-465">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-465">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-466">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-468">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-468">Informational (4)</span></span>|  
|<span data-ttu-id="ea4a2-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ea4a2-470">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-471">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-472">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-472">Event</span></span>|<span data-ttu-id="ea4a2-473">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-473">Event ID</span></span>|<span data-ttu-id="ea4a2-474">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="ea4a2-475">11</span><span class="sxs-lookup"><span data-stu-id="ea4a2-475">11</span></span>|<span data-ttu-id="ea4a2-476">Был создан параллельный поток сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="ea4a2-477">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-477">No event data.</span></span>  
  
 [<span data-ttu-id="ea4a2-478">К началу</span><span class="sxs-lookup"><span data-stu-id="ea4a2-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="ea4a2-479">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ea4a2-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="ea4a2-480">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ea4a2-481">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-481">Keyword for raising the event</span></span>|<span data-ttu-id="ea4a2-482">Уровень</span><span class="sxs-lookup"><span data-stu-id="ea4a2-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ea4a2-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ea4a2-484">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-484">Informational (4)</span></span>|  
|<span data-ttu-id="ea4a2-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ea4a2-486">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="ea4a2-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="ea4a2-487">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ea4a2-488">Событие</span><span class="sxs-lookup"><span data-stu-id="ea4a2-488">Event</span></span>|<span data-ttu-id="ea4a2-489">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="ea4a2-489">Event ID</span></span>|<span data-ttu-id="ea4a2-490">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="ea4a2-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="ea4a2-491">12</span><span class="sxs-lookup"><span data-stu-id="ea4a2-491">12</span></span>|<span data-ttu-id="ea4a2-492">Параллельный поток сборки мусора был завершен.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="ea4a2-493">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="ea4a2-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea4a2-494">См. также</span><span class="sxs-lookup"><span data-stu-id="ea4a2-494">See Also</span></span>  
 [<span data-ttu-id="ea4a2-495">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="ea4a2-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
