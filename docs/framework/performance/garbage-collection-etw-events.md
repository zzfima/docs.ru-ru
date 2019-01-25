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
ms.openlocfilehash: 95762cbda4a1a251dd64fd33b2815d474f1fe2b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685221"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="26602-102">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="26602-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="26602-103">Эти события собирают сведения, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="26602-104">Они помогают при диагностике и отладке, в том числе позволяют определить, сколько раз осуществлялась сборка мусора, какой объем памяти был освобожден в ходе сборки мусора и т. д.</span><span class="sxs-lookup"><span data-stu-id="26602-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="26602-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="26602-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="26602-106">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="26602-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="26602-107">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="26602-108">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="26602-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="26602-109">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="26602-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="26602-110">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="26602-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="26602-111">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="26602-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="26602-112">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="26602-113">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="26602-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="26602-114">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="26602-115">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="26602-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="26602-116">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="26602-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="26602-117">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="26602-118">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="26602-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="26602-119">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="26602-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="26602-120">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="26602-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="26602-121">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="26602-122">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="26602-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="26602-123">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-123">Keyword for raising the event</span></span>|<span data-ttu-id="26602-124">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-126">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-127">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-128">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-128">Event</span></span>|<span data-ttu-id="26602-129">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-129">Event ID</span></span>|<span data-ttu-id="26602-130">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="26602-131">1</span><span class="sxs-lookup"><span data-stu-id="26602-131">1</span></span>|<span data-ttu-id="26602-132">Сборка мусора начата.</span><span class="sxs-lookup"><span data-stu-id="26602-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="26602-133">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-134">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-134">Field name</span></span>|<span data-ttu-id="26602-135">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-135">Data type</span></span>|<span data-ttu-id="26602-136">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-137">Количество</span><span class="sxs-lookup"><span data-stu-id="26602-137">Count</span></span>|<span data-ttu-id="26602-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-138">win:UInt32</span></span>|<span data-ttu-id="26602-139">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="26602-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="26602-140">Глубина</span><span class="sxs-lookup"><span data-stu-id="26602-140">Depth</span></span>|<span data-ttu-id="26602-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-141">win:UInt32</span></span>|<span data-ttu-id="26602-142">Поколение, для которого выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="26602-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="26602-143">Причина</span><span class="sxs-lookup"><span data-stu-id="26602-143">Reason</span></span>|<span data-ttu-id="26602-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-144">win:UInt32</span></span>|<span data-ttu-id="26602-145">Причина запуска сборки мусора:</span><span class="sxs-lookup"><span data-stu-id="26602-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="26602-146">0x0 — выделение кучи маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="26602-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="26602-147">0x1 — принудительная.</span><span class="sxs-lookup"><span data-stu-id="26602-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="26602-148">0x2 — недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="26602-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="26602-149">0x3 — пусто.</span><span class="sxs-lookup"><span data-stu-id="26602-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="26602-150">0x4 — выделение кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="26602-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="26602-151">0x5 — недостаточно места (для кучи маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="26602-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="26602-152">0x6 — недостаточно места (для кучи больших объектов).</span><span class="sxs-lookup"><span data-stu-id="26602-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="26602-153">0x7 — принудительная, но не блокирующий.</span><span class="sxs-lookup"><span data-stu-id="26602-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="26602-154">Тип</span><span class="sxs-lookup"><span data-stu-id="26602-154">Type</span></span>|<span data-ttu-id="26602-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-155">win:UInt32</span></span>|<span data-ttu-id="26602-156">0x0 — блокировка сборки мусора вне фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="26602-157">0x1 — фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="26602-158">0x2 — блокировка сборки мусора в ходе фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="26602-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-159">ClrInstanceID</span></span>|<span data-ttu-id="26602-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-160">win:UInt16</span></span>|<span data-ttu-id="26602-161">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-162">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="26602-163">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="26602-164">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-165">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-165">Keyword for raising the event</span></span>|<span data-ttu-id="26602-166">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-168">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-169">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-170">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-170">Event</span></span>|<span data-ttu-id="26602-171">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-171">Event ID</span></span>|<span data-ttu-id="26602-172">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="26602-173">2</span><span class="sxs-lookup"><span data-stu-id="26602-173">2</span></span>|<span data-ttu-id="26602-174">Сборка мусора закончена.</span><span class="sxs-lookup"><span data-stu-id="26602-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="26602-175">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-176">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-176">Field name</span></span>|<span data-ttu-id="26602-177">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-177">Data type</span></span>|<span data-ttu-id="26602-178">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-179">Количество</span><span class="sxs-lookup"><span data-stu-id="26602-179">Count</span></span>|<span data-ttu-id="26602-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-180">win:UInt32</span></span>|<span data-ttu-id="26602-181">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="26602-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="26602-182">Глубина</span><span class="sxs-lookup"><span data-stu-id="26602-182">Depth</span></span>|<span data-ttu-id="26602-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-183">win:UInt32</span></span>|<span data-ttu-id="26602-184">Поколение, для которого выполнялась сборка.</span><span class="sxs-lookup"><span data-stu-id="26602-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="26602-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-185">ClrInstanceID</span></span>|<span data-ttu-id="26602-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-186">win:UInt16</span></span>|<span data-ttu-id="26602-187">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-188">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="26602-189">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="26602-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="26602-190">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-191">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-191">Keyword for raising the event</span></span>|<span data-ttu-id="26602-192">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-194">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-195">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-196">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-196">Event</span></span>|<span data-ttu-id="26602-197">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-197">Event ID</span></span>|<span data-ttu-id="26602-198">Описание:</span><span class="sxs-lookup"><span data-stu-id="26602-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="26602-199">4</span><span class="sxs-lookup"><span data-stu-id="26602-199">4</span></span>|<span data-ttu-id="26602-200">Показывает статистику кучи по завершении каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="26602-201">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-202">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-202">Field name</span></span>|<span data-ttu-id="26602-203">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-203">Data type</span></span>|<span data-ttu-id="26602-204">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="26602-205">GenerationSize0</span></span>|<span data-ttu-id="26602-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-206">win:UInt64</span></span>|<span data-ttu-id="26602-207">Размер области памяти поколения 0 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="26602-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="26602-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="26602-208">TotalPromotedSize0</span></span>|<span data-ttu-id="26602-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-209">win:UInt64</span></span>|<span data-ttu-id="26602-210">Число байт, которые были переданы из поколения 0 в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="26602-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="26602-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="26602-211">GenerationSize1</span></span>|<span data-ttu-id="26602-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-212">win:UInt64</span></span>|<span data-ttu-id="26602-213">Размер области памяти поколения 1 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="26602-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="26602-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="26602-214">TotalPromotedSize1</span></span>|<span data-ttu-id="26602-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-215">win:UInt64</span></span>|<span data-ttu-id="26602-216">Число байт, которые были переданы из поколения 1 в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="26602-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="26602-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="26602-217">GenerationSize2</span></span>|<span data-ttu-id="26602-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-218">win:UInt64</span></span>|<span data-ttu-id="26602-219">Размер области памяти поколения 2 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="26602-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="26602-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="26602-220">TotalPromotedSize2</span></span>|<span data-ttu-id="26602-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-221">win:UInt64</span></span>|<span data-ttu-id="26602-222">Число байт, оставшихся в поколении 2 после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="26602-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="26602-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="26602-223">GenerationSize3</span></span>|<span data-ttu-id="26602-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-224">win:UInt64</span></span>|<span data-ttu-id="26602-225">Размер кучи больших объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="26602-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="26602-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="26602-226">TotalPromotedSize3</span></span>|<span data-ttu-id="26602-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-227">win:UInt64</span></span>|<span data-ttu-id="26602-228">Число байт, оставшихся в куче больших объектов после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="26602-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="26602-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="26602-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="26602-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-230">win:UInt64</span></span>|<span data-ttu-id="26602-231">Общий размер (в байтах) объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="26602-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="26602-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="26602-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="26602-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-233">win:UInt64</span></span>|<span data-ttu-id="26602-234">Количество объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="26602-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="26602-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="26602-235">PinnedObjectCount</span></span>|<span data-ttu-id="26602-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-236">win:UInt32</span></span>|<span data-ttu-id="26602-237">Количество закрепленных (неподвижных) объектов.</span><span class="sxs-lookup"><span data-stu-id="26602-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="26602-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="26602-238">SinkBlockCount</span></span>|<span data-ttu-id="26602-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-239">win:UInt32</span></span>|<span data-ttu-id="26602-240">Количество используемых блоков синхронизации.</span><span class="sxs-lookup"><span data-stu-id="26602-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="26602-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="26602-241">GCHandleCount</span></span>|<span data-ttu-id="26602-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-242">win:UInt32</span></span>|<span data-ttu-id="26602-243">Число используемых дескрипторов сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="26602-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-244">ClrInstanceID</span></span>|<span data-ttu-id="26602-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-245">win:UInt16</span></span>|<span data-ttu-id="26602-246">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-247">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="26602-248">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="26602-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="26602-249">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-250">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-250">Keyword for raising the event</span></span>|<span data-ttu-id="26602-251">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-253">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-254">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-255">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-255">Event</span></span>|<span data-ttu-id="26602-256">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-256">Event ID</span></span>|<span data-ttu-id="26602-257">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="26602-258">5</span><span class="sxs-lookup"><span data-stu-id="26602-258">5</span></span>|<span data-ttu-id="26602-259">Был создан новый сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="26602-260">Кроме того, при включении трассировки для уже работающего процесса это событие создается для каждого существующего сегмента.</span><span class="sxs-lookup"><span data-stu-id="26602-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="26602-261">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-262">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-262">Field name</span></span>|<span data-ttu-id="26602-263">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-263">Data type</span></span>|<span data-ttu-id="26602-264">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-265">Адрес</span><span class="sxs-lookup"><span data-stu-id="26602-265">Address</span></span>|<span data-ttu-id="26602-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-266">win:UInt64</span></span>|<span data-ttu-id="26602-267">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="26602-267">The address of the segment.</span></span>|  
|<span data-ttu-id="26602-268">Размер</span><span class="sxs-lookup"><span data-stu-id="26602-268">Size</span></span>|<span data-ttu-id="26602-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-269">win:UInt64</span></span>|<span data-ttu-id="26602-270">Размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="26602-270">The size of the segment.</span></span>|  
|<span data-ttu-id="26602-271">Тип</span><span class="sxs-lookup"><span data-stu-id="26602-271">Type</span></span>|<span data-ttu-id="26602-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-272">win:UInt32</span></span>|<span data-ttu-id="26602-273">0x0 — куча маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="26602-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="26602-274">0x1 — куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="26602-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="26602-275">0x2 — куча только для чтения.</span><span class="sxs-lookup"><span data-stu-id="26602-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="26602-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-276">ClrInstanceID</span></span>|<span data-ttu-id="26602-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-277">win:UInt16</span></span>|<span data-ttu-id="26602-278">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="26602-279">Обратите внимание, что размер сегментов, выделенных сборщиком мусора, зависит от реализации и может быть изменен в любое время, в том числе при периодических обновлениях.</span><span class="sxs-lookup"><span data-stu-id="26602-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="26602-280">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="26602-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="26602-281">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="26602-282">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="26602-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="26602-283">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-284">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-284">Keyword for raising the event</span></span>|<span data-ttu-id="26602-285">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-287">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-288">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-289">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-289">Event</span></span>|<span data-ttu-id="26602-290">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-290">Event ID</span></span>|<span data-ttu-id="26602-291">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="26602-292">6</span><span class="sxs-lookup"><span data-stu-id="26602-292">6</span></span>|<span data-ttu-id="26602-293">Сегмент сборки мусора был освобожден.</span><span class="sxs-lookup"><span data-stu-id="26602-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="26602-294">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-295">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-295">Field name</span></span>|<span data-ttu-id="26602-296">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-296">Data type</span></span>|<span data-ttu-id="26602-297">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-298">Адрес</span><span class="sxs-lookup"><span data-stu-id="26602-298">Address</span></span>|<span data-ttu-id="26602-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-299">win:UInt64</span></span>|<span data-ttu-id="26602-300">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="26602-300">The address of the segment.</span></span>|  
|<span data-ttu-id="26602-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-301">ClrInstanceID</span></span>|<span data-ttu-id="26602-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-302">win:UInt16</span></span>|<span data-ttu-id="26602-303">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-304">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="26602-305">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="26602-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="26602-306">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-307">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-307">Keyword for raising the event</span></span>|<span data-ttu-id="26602-308">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-310">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-311">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-312">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-312">Event</span></span>|<span data-ttu-id="26602-313">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-313">Event ID</span></span>|<span data-ttu-id="26602-314">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="26602-315">7</span><span class="sxs-lookup"><span data-stu-id="26602-315">7</span></span>|<span data-ttu-id="26602-316">Началось возобновление приостановленной среды CLR.</span><span class="sxs-lookup"><span data-stu-id="26602-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="26602-317">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-317">No event data.</span></span>  
  
 [<span data-ttu-id="26602-318">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="26602-319">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="26602-320">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-321">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-321">Keyword for raising the event</span></span>|<span data-ttu-id="26602-322">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-324">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-325">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-326">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-326">Event</span></span>|<span data-ttu-id="26602-327">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-327">Event Id</span></span>|<span data-ttu-id="26602-328">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="26602-329">3</span><span class="sxs-lookup"><span data-stu-id="26602-329">3</span></span>|<span data-ttu-id="26602-330">Возобновление приостановленной среды CLR завершено.</span><span class="sxs-lookup"><span data-stu-id="26602-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="26602-331">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-331">No event data.</span></span>  
  
 [<span data-ttu-id="26602-332">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="26602-333">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="26602-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="26602-334">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-335">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-335">Keyword for raising the event</span></span>|<span data-ttu-id="26602-336">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-338">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-339">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-340">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-340">Event</span></span>|<span data-ttu-id="26602-341">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-341">Event ID</span></span>|<span data-ttu-id="26602-342">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="26602-343">9</span><span class="sxs-lookup"><span data-stu-id="26602-343">9</span></span>|<span data-ttu-id="26602-344">Началась приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="26602-345">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-346">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-346">Field name</span></span>|<span data-ttu-id="26602-347">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-347">Data type</span></span>|<span data-ttu-id="26602-348">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-349">Причина</span><span class="sxs-lookup"><span data-stu-id="26602-349">Reason</span></span>|<span data-ttu-id="26602-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-350">win:UInt16</span></span>|<span data-ttu-id="26602-351">0x0 — другое.</span><span class="sxs-lookup"><span data-stu-id="26602-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="26602-352">0x1 — сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="26602-353">0x2 — завершение работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="26602-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="26602-354">0x3 — свертка кода.</span><span class="sxs-lookup"><span data-stu-id="26602-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="26602-355">0x4 — завершение работы.</span><span class="sxs-lookup"><span data-stu-id="26602-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="26602-356">0x5 — отладчик.</span><span class="sxs-lookup"><span data-stu-id="26602-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="26602-357">0x6 — подготовка к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="26602-358">Количество</span><span class="sxs-lookup"><span data-stu-id="26602-358">Count</span></span>|<span data-ttu-id="26602-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-359">win:UInt32</span></span>|<span data-ttu-id="26602-360">Счетчик сборки мусора на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="26602-360">The GC count at the time.</span></span> <span data-ttu-id="26602-361">Обычно после этого отображается последующее событие запуска сборки мусора, а значение увеличивается на 1 в соответствии с увеличением индекса сборки мусора в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="26602-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="26602-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-362">ClrInstanceID</span></span>|<span data-ttu-id="26602-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-363">win:UInt16</span></span>|<span data-ttu-id="26602-364">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-365">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="26602-366">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="26602-367">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="26602-368">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-368">Keyword for raising the event</span></span>|<span data-ttu-id="26602-369">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-371">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-372">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="26602-373">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-373">Event</span></span>|<span data-ttu-id="26602-374">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-374">Event ID</span></span>|<span data-ttu-id="26602-375">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="26602-376">8</span><span class="sxs-lookup"><span data-stu-id="26602-376">8</span></span>|<span data-ttu-id="26602-377">Завершена приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="26602-378">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-378">No event data.</span></span>  
  
 [<span data-ttu-id="26602-379">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="26602-380">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="26602-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="26602-381">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-382">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-382">Keyword for raising the event</span></span>|<span data-ttu-id="26602-383">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-385">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-386">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-387">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-387">Event</span></span>|<span data-ttu-id="26602-388">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-388">Event ID</span></span>|<span data-ttu-id="26602-389">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="26602-390">10</span><span class="sxs-lookup"><span data-stu-id="26602-390">10</span></span>|<span data-ttu-id="26602-391">Каждый раз выделяется около 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="26602-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="26602-392">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-393">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-393">Field name</span></span>|<span data-ttu-id="26602-394">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-394">Data type</span></span>|<span data-ttu-id="26602-395">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="26602-396">AllocationAmount</span></span>|<span data-ttu-id="26602-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-397">win:UInt32</span></span>|<span data-ttu-id="26602-398">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="26602-398">The allocation size, in bytes.</span></span> <span data-ttu-id="26602-399">Это значение является точным для выделений, размер которых меньше длины ULONG (4 294 967 295 байт).</span><span class="sxs-lookup"><span data-stu-id="26602-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="26602-400">Если выделение больше, это поле содержит усеченное значение.</span><span class="sxs-lookup"><span data-stu-id="26602-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="26602-401">Используйте `AllocationAmount64` для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="26602-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="26602-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="26602-402">AllocationKind</span></span>|<span data-ttu-id="26602-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-403">win:UInt32</span></span>|<span data-ttu-id="26602-404">0x0 — выделение для маленького объекта (выделение в куче маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="26602-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="26602-405">0x1 — выделение для большого объекта (выделение в куче больших объектов).</span><span class="sxs-lookup"><span data-stu-id="26602-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="26602-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-406">ClrInstanceID</span></span>|<span data-ttu-id="26602-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-407">win:UInt16</span></span>|<span data-ttu-id="26602-408">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="26602-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="26602-409">AllocationAmount64</span></span>|<span data-ttu-id="26602-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="26602-410">win:UInt64</span></span>|<span data-ttu-id="26602-411">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="26602-411">The allocation size, in bytes.</span></span> <span data-ttu-id="26602-412">Это значение является точным для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="26602-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="26602-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="26602-413">TypeId</span></span>|<span data-ttu-id="26602-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="26602-414">win:Pointer</span></span>|<span data-ttu-id="26602-415">Адрес MethodTable.</span><span class="sxs-lookup"><span data-stu-id="26602-415">The address of the MethodTable.</span></span> <span data-ttu-id="26602-416">Если в ходе этого события было выделено несколько типов объектов, указывается адрес MethodTable, соответствующий последнему выделенному объекту (объекту, вызвавшему превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="26602-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="26602-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="26602-417">TypeName</span></span>|<span data-ttu-id="26602-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="26602-418">win:UnicodeString</span></span>|<span data-ttu-id="26602-419">Имя выделенного типа.</span><span class="sxs-lookup"><span data-stu-id="26602-419">The name of the type that was allocated.</span></span> <span data-ttu-id="26602-420">Если в ходе этого события было выделено несколько типов объектов, указывается тип последнего выделенного объекта (объекта, вызвавшего превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="26602-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="26602-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="26602-421">HeapIndex</span></span>|<span data-ttu-id="26602-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-422">win:UInt32</span></span>|<span data-ttu-id="26602-423">Куча, в которой был выделен объект.</span><span class="sxs-lookup"><span data-stu-id="26602-423">The heap where the object was allocated.</span></span> <span data-ttu-id="26602-424">Это значение равно 0 (нулю) при выполнении сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="26602-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="26602-425">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="26602-426">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="26602-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="26602-427">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-428">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-428">Keyword for raising the event</span></span>|<span data-ttu-id="26602-429">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-431">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-432">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-433">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-433">Event</span></span>|<span data-ttu-id="26602-434">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-434">Event ID</span></span>|<span data-ttu-id="26602-435">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="26602-436">14</span><span class="sxs-lookup"><span data-stu-id="26602-436">14</span></span>|<span data-ttu-id="26602-437">Начало выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="26602-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="26602-438">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-438">No event data.</span></span>  
  
 [<span data-ttu-id="26602-439">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="26602-440">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="26602-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="26602-441">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-442">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-442">Keyword for raising the event</span></span>|<span data-ttu-id="26602-443">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-445">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-446">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-447">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-447">Event</span></span>|<span data-ttu-id="26602-448">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-448">Event ID</span></span>|<span data-ttu-id="26602-449">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="26602-450">13</span><span class="sxs-lookup"><span data-stu-id="26602-450">13</span></span>|<span data-ttu-id="26602-451">Завершение выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="26602-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="26602-452">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="26602-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="26602-453">Имя поля</span><span class="sxs-lookup"><span data-stu-id="26602-453">Field name</span></span>|<span data-ttu-id="26602-454">Тип данных</span><span class="sxs-lookup"><span data-stu-id="26602-454">Data type</span></span>|<span data-ttu-id="26602-455">Описание</span><span class="sxs-lookup"><span data-stu-id="26602-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="26602-456">Количество</span><span class="sxs-lookup"><span data-stu-id="26602-456">Count</span></span>|<span data-ttu-id="26602-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="26602-457">win:UInt32</span></span>|<span data-ttu-id="26602-458">Число выполненных методов завершения.</span><span class="sxs-lookup"><span data-stu-id="26602-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="26602-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="26602-459">ClrInstanceID</span></span>|<span data-ttu-id="26602-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="26602-460">win:UInt16</span></span>|<span data-ttu-id="26602-461">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="26602-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="26602-462">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="26602-463">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="26602-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="26602-464">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-465">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-465">Keyword for raising the event</span></span>|<span data-ttu-id="26602-466">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-468">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-468">Informational (4)</span></span>|  
|<span data-ttu-id="26602-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="26602-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="26602-470">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-471">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-472">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-472">Event</span></span>|<span data-ttu-id="26602-473">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-473">Event ID</span></span>|<span data-ttu-id="26602-474">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="26602-475">11</span><span class="sxs-lookup"><span data-stu-id="26602-475">11</span></span>|<span data-ttu-id="26602-476">Был создан параллельный поток сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="26602-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="26602-477">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-477">No event data.</span></span>  
  
 [<span data-ttu-id="26602-478">К началу</span><span class="sxs-lookup"><span data-stu-id="26602-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="26602-479">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="26602-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="26602-480">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="26602-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="26602-481">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="26602-481">Keyword for raising the event</span></span>|<span data-ttu-id="26602-482">Уровень</span><span class="sxs-lookup"><span data-stu-id="26602-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="26602-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="26602-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="26602-484">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-484">Informational (4)</span></span>|  
|<span data-ttu-id="26602-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="26602-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="26602-486">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="26602-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="26602-487">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="26602-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="26602-488">Событие</span><span class="sxs-lookup"><span data-stu-id="26602-488">Event</span></span>|<span data-ttu-id="26602-489">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="26602-489">Event ID</span></span>|<span data-ttu-id="26602-490">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="26602-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="26602-491">12</span><span class="sxs-lookup"><span data-stu-id="26602-491">12</span></span>|<span data-ttu-id="26602-492">Параллельный поток сборки мусора был завершен.</span><span class="sxs-lookup"><span data-stu-id="26602-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="26602-493">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="26602-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26602-494">См. также</span><span class="sxs-lookup"><span data-stu-id="26602-494">See also</span></span>
- [<span data-ttu-id="26602-495">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="26602-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
