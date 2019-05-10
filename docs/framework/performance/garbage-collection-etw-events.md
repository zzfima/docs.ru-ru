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
ms.openlocfilehash: e5e10a1dc1ad3230213a20b850741a6ec0468294
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616421"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="6b191-102">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="6b191-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="6b191-103">Эти события собирают сведения, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="6b191-104">Они помогают при диагностике и отладке, в том числе позволяют определить, сколько раз осуществлялась сборка мусора, какой объем памяти был освобожден в ходе сборки мусора и т. д.</span><span class="sxs-lookup"><span data-stu-id="6b191-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="6b191-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="6b191-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="6b191-106">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="6b191-107">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="6b191-108">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="6b191-109">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="6b191-110">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="6b191-111">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="6b191-112">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="6b191-113">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="6b191-114">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="6b191-115">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="6b191-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="6b191-116">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="6b191-117">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="6b191-118">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="6b191-119">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="6b191-120">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="6b191-121">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="6b191-122">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="6b191-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6b191-123">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-123">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-124">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-126">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-127">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-128">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-128">Event</span></span>|<span data-ttu-id="6b191-129">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-129">Event ID</span></span>|<span data-ttu-id="6b191-130">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="6b191-131">1</span><span class="sxs-lookup"><span data-stu-id="6b191-131">1</span></span>|<span data-ttu-id="6b191-132">Сборка мусора начата.</span><span class="sxs-lookup"><span data-stu-id="6b191-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="6b191-133">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-134">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-134">Field name</span></span>|<span data-ttu-id="6b191-135">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-135">Data type</span></span>|<span data-ttu-id="6b191-136">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-137">Количество</span><span class="sxs-lookup"><span data-stu-id="6b191-137">Count</span></span>|<span data-ttu-id="6b191-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-138">win:UInt32</span></span>|<span data-ttu-id="6b191-139">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="6b191-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="6b191-140">Глубина</span><span class="sxs-lookup"><span data-stu-id="6b191-140">Depth</span></span>|<span data-ttu-id="6b191-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-141">win:UInt32</span></span>|<span data-ttu-id="6b191-142">Поколение, для которого выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="6b191-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="6b191-143">Причина</span><span class="sxs-lookup"><span data-stu-id="6b191-143">Reason</span></span>|<span data-ttu-id="6b191-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-144">win:UInt32</span></span>|<span data-ttu-id="6b191-145">Причина запуска сборки мусора:</span><span class="sxs-lookup"><span data-stu-id="6b191-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="6b191-146">0x0 — выделение кучи маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="6b191-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="6b191-147">0x1 — принудительная.</span><span class="sxs-lookup"><span data-stu-id="6b191-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="6b191-148">0x2 — недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="6b191-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="6b191-149">0x3 — пусто.</span><span class="sxs-lookup"><span data-stu-id="6b191-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="6b191-150">0x4 — выделение кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="6b191-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="6b191-151">0x5 — недостаточно места (для кучи маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="6b191-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="6b191-152">0x6 — недостаточно места (для кучи больших объектов).</span><span class="sxs-lookup"><span data-stu-id="6b191-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="6b191-153">0x7 — принудительная, но не блокирующий.</span><span class="sxs-lookup"><span data-stu-id="6b191-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="6b191-154">Тип</span><span class="sxs-lookup"><span data-stu-id="6b191-154">Type</span></span>|<span data-ttu-id="6b191-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-155">win:UInt32</span></span>|<span data-ttu-id="6b191-156">0x0 — блокировка сборки мусора вне фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="6b191-157">0x1 — фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="6b191-158">0x2 — блокировка сборки мусора в ходе фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="6b191-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-159">ClrInstanceID</span></span>|<span data-ttu-id="6b191-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-160">win:UInt16</span></span>|<span data-ttu-id="6b191-161">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-162">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="6b191-163">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="6b191-164">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-165">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-165">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-166">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-168">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-169">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-170">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-170">Event</span></span>|<span data-ttu-id="6b191-171">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-171">Event ID</span></span>|<span data-ttu-id="6b191-172">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="6b191-173">2</span><span class="sxs-lookup"><span data-stu-id="6b191-173">2</span></span>|<span data-ttu-id="6b191-174">Сборка мусора закончена.</span><span class="sxs-lookup"><span data-stu-id="6b191-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="6b191-175">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-176">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-176">Field name</span></span>|<span data-ttu-id="6b191-177">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-177">Data type</span></span>|<span data-ttu-id="6b191-178">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-179">Количество</span><span class="sxs-lookup"><span data-stu-id="6b191-179">Count</span></span>|<span data-ttu-id="6b191-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-180">win:UInt32</span></span>|<span data-ttu-id="6b191-181">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="6b191-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="6b191-182">Глубина</span><span class="sxs-lookup"><span data-stu-id="6b191-182">Depth</span></span>|<span data-ttu-id="6b191-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-183">win:UInt32</span></span>|<span data-ttu-id="6b191-184">Поколение, для которого выполнялась сборка.</span><span class="sxs-lookup"><span data-stu-id="6b191-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="6b191-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-185">ClrInstanceID</span></span>|<span data-ttu-id="6b191-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-186">win:UInt16</span></span>|<span data-ttu-id="6b191-187">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-188">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="6b191-189">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="6b191-190">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-191">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-191">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-192">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-194">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-195">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-196">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-196">Event</span></span>|<span data-ttu-id="6b191-197">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-197">Event ID</span></span>|<span data-ttu-id="6b191-198">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="6b191-199">4</span><span class="sxs-lookup"><span data-stu-id="6b191-199">4</span></span>|<span data-ttu-id="6b191-200">Показывает статистику кучи по завершении каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="6b191-201">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-202">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-202">Field name</span></span>|<span data-ttu-id="6b191-203">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-203">Data type</span></span>|<span data-ttu-id="6b191-204">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="6b191-205">GenerationSize0</span></span>|<span data-ttu-id="6b191-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-206">win:UInt64</span></span>|<span data-ttu-id="6b191-207">Размер области памяти поколения 0 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="6b191-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="6b191-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="6b191-208">TotalPromotedSize0</span></span>|<span data-ttu-id="6b191-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-209">win:UInt64</span></span>|<span data-ttu-id="6b191-210">Число байт, которые были переданы из поколения 0 в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="6b191-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="6b191-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="6b191-211">GenerationSize1</span></span>|<span data-ttu-id="6b191-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-212">win:UInt64</span></span>|<span data-ttu-id="6b191-213">Размер области памяти поколения 1 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="6b191-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="6b191-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="6b191-214">TotalPromotedSize1</span></span>|<span data-ttu-id="6b191-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-215">win:UInt64</span></span>|<span data-ttu-id="6b191-216">Число байт, которые были переданы из поколения 1 в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="6b191-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="6b191-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="6b191-217">GenerationSize2</span></span>|<span data-ttu-id="6b191-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-218">win:UInt64</span></span>|<span data-ttu-id="6b191-219">Размер области памяти поколения 2 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="6b191-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="6b191-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="6b191-220">TotalPromotedSize2</span></span>|<span data-ttu-id="6b191-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-221">win:UInt64</span></span>|<span data-ttu-id="6b191-222">Число байт, оставшихся в поколении 2 после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="6b191-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="6b191-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="6b191-223">GenerationSize3</span></span>|<span data-ttu-id="6b191-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-224">win:UInt64</span></span>|<span data-ttu-id="6b191-225">Размер кучи больших объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="6b191-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="6b191-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="6b191-226">TotalPromotedSize3</span></span>|<span data-ttu-id="6b191-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-227">win:UInt64</span></span>|<span data-ttu-id="6b191-228">Число байт, оставшихся в куче больших объектов после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="6b191-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="6b191-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="6b191-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="6b191-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-230">win:UInt64</span></span>|<span data-ttu-id="6b191-231">Общий размер (в байтах) объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="6b191-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="6b191-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="6b191-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="6b191-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-233">win:UInt64</span></span>|<span data-ttu-id="6b191-234">Количество объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="6b191-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="6b191-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="6b191-235">PinnedObjectCount</span></span>|<span data-ttu-id="6b191-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-236">win:UInt32</span></span>|<span data-ttu-id="6b191-237">Количество закрепленных (неподвижных) объектов.</span><span class="sxs-lookup"><span data-stu-id="6b191-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="6b191-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="6b191-238">SinkBlockCount</span></span>|<span data-ttu-id="6b191-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-239">win:UInt32</span></span>|<span data-ttu-id="6b191-240">Количество используемых блоков синхронизации.</span><span class="sxs-lookup"><span data-stu-id="6b191-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="6b191-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="6b191-241">GCHandleCount</span></span>|<span data-ttu-id="6b191-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-242">win:UInt32</span></span>|<span data-ttu-id="6b191-243">Число используемых дескрипторов сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="6b191-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-244">ClrInstanceID</span></span>|<span data-ttu-id="6b191-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-245">win:UInt16</span></span>|<span data-ttu-id="6b191-246">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-247">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="6b191-248">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="6b191-249">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-250">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-250">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-251">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-253">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-254">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-255">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-255">Event</span></span>|<span data-ttu-id="6b191-256">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-256">Event ID</span></span>|<span data-ttu-id="6b191-257">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="6b191-258">5</span><span class="sxs-lookup"><span data-stu-id="6b191-258">5</span></span>|<span data-ttu-id="6b191-259">Был создан новый сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="6b191-260">Кроме того, при включении трассировки для уже работающего процесса это событие создается для каждого существующего сегмента.</span><span class="sxs-lookup"><span data-stu-id="6b191-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="6b191-261">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-262">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-262">Field name</span></span>|<span data-ttu-id="6b191-263">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-263">Data type</span></span>|<span data-ttu-id="6b191-264">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-265">Адрес</span><span class="sxs-lookup"><span data-stu-id="6b191-265">Address</span></span>|<span data-ttu-id="6b191-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-266">win:UInt64</span></span>|<span data-ttu-id="6b191-267">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="6b191-267">The address of the segment.</span></span>|  
|<span data-ttu-id="6b191-268">Размер</span><span class="sxs-lookup"><span data-stu-id="6b191-268">Size</span></span>|<span data-ttu-id="6b191-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-269">win:UInt64</span></span>|<span data-ttu-id="6b191-270">Размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="6b191-270">The size of the segment.</span></span>|  
|<span data-ttu-id="6b191-271">Тип</span><span class="sxs-lookup"><span data-stu-id="6b191-271">Type</span></span>|<span data-ttu-id="6b191-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-272">win:UInt32</span></span>|<span data-ttu-id="6b191-273">0x0 — куча маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="6b191-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="6b191-274">0x1 — куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="6b191-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="6b191-275">0x2 — куча только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6b191-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="6b191-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-276">ClrInstanceID</span></span>|<span data-ttu-id="6b191-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-277">win:UInt16</span></span>|<span data-ttu-id="6b191-278">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="6b191-279">Обратите внимание, что размер сегментов, выделенных сборщиком мусора, зависит от реализации и может быть изменен в любое время, в том числе при периодических обновлениях.</span><span class="sxs-lookup"><span data-stu-id="6b191-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="6b191-280">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="6b191-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="6b191-281">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="6b191-282">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="6b191-283">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-284">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-284">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-285">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-287">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-288">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-289">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-289">Event</span></span>|<span data-ttu-id="6b191-290">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-290">Event ID</span></span>|<span data-ttu-id="6b191-291">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="6b191-292">6</span><span class="sxs-lookup"><span data-stu-id="6b191-292">6</span></span>|<span data-ttu-id="6b191-293">Сегмент сборки мусора был освобожден.</span><span class="sxs-lookup"><span data-stu-id="6b191-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="6b191-294">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-295">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-295">Field name</span></span>|<span data-ttu-id="6b191-296">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-296">Data type</span></span>|<span data-ttu-id="6b191-297">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-298">Адрес</span><span class="sxs-lookup"><span data-stu-id="6b191-298">Address</span></span>|<span data-ttu-id="6b191-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-299">win:UInt64</span></span>|<span data-ttu-id="6b191-300">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="6b191-300">The address of the segment.</span></span>|  
|<span data-ttu-id="6b191-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-301">ClrInstanceID</span></span>|<span data-ttu-id="6b191-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-302">win:UInt16</span></span>|<span data-ttu-id="6b191-303">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-304">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="6b191-305">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="6b191-306">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-307">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-307">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-308">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-310">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-311">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-312">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-312">Event</span></span>|<span data-ttu-id="6b191-313">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-313">Event ID</span></span>|<span data-ttu-id="6b191-314">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="6b191-315">7</span><span class="sxs-lookup"><span data-stu-id="6b191-315">7</span></span>|<span data-ttu-id="6b191-316">Началось возобновление приостановленной среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="6b191-317">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-317">No event data.</span></span>  
  
 [<span data-ttu-id="6b191-318">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="6b191-319">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="6b191-320">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-321">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-321">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-322">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-324">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-325">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-326">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-326">Event</span></span>|<span data-ttu-id="6b191-327">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-327">Event Id</span></span>|<span data-ttu-id="6b191-328">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="6b191-329">3</span><span class="sxs-lookup"><span data-stu-id="6b191-329">3</span></span>|<span data-ttu-id="6b191-330">Возобновление приостановленной среды CLR завершено.</span><span class="sxs-lookup"><span data-stu-id="6b191-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="6b191-331">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-331">No event data.</span></span>  
  
 [<span data-ttu-id="6b191-332">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="6b191-333">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="6b191-334">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-335">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-335">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-336">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-338">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-339">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-340">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-340">Event</span></span>|<span data-ttu-id="6b191-341">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-341">Event ID</span></span>|<span data-ttu-id="6b191-342">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="6b191-343">9</span><span class="sxs-lookup"><span data-stu-id="6b191-343">9</span></span>|<span data-ttu-id="6b191-344">Началась приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="6b191-345">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-346">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-346">Field name</span></span>|<span data-ttu-id="6b191-347">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-347">Data type</span></span>|<span data-ttu-id="6b191-348">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-349">Причина</span><span class="sxs-lookup"><span data-stu-id="6b191-349">Reason</span></span>|<span data-ttu-id="6b191-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-350">win:UInt16</span></span>|<span data-ttu-id="6b191-351">0x0 — другое.</span><span class="sxs-lookup"><span data-stu-id="6b191-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="6b191-352">0x1 — сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="6b191-353">0x2 — завершение работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="6b191-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="6b191-354">0x3 — свертка кода.</span><span class="sxs-lookup"><span data-stu-id="6b191-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="6b191-355">0x4 — завершение работы.</span><span class="sxs-lookup"><span data-stu-id="6b191-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="6b191-356">0x5 — отладчик.</span><span class="sxs-lookup"><span data-stu-id="6b191-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="6b191-357">0x6 — подготовка к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="6b191-358">Количество</span><span class="sxs-lookup"><span data-stu-id="6b191-358">Count</span></span>|<span data-ttu-id="6b191-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-359">win:UInt32</span></span>|<span data-ttu-id="6b191-360">Счетчик сборки мусора на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="6b191-360">The GC count at the time.</span></span> <span data-ttu-id="6b191-361">Обычно после этого отображается последующее событие запуска сборки мусора, а значение увеличивается на 1 в соответствии с увеличением индекса сборки мусора в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="6b191-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="6b191-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-362">ClrInstanceID</span></span>|<span data-ttu-id="6b191-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-363">win:UInt16</span></span>|<span data-ttu-id="6b191-364">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-365">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="6b191-366">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="6b191-367">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="6b191-368">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-368">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-369">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-371">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-372">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="6b191-373">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-373">Event</span></span>|<span data-ttu-id="6b191-374">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-374">Event ID</span></span>|<span data-ttu-id="6b191-375">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="6b191-376">8</span><span class="sxs-lookup"><span data-stu-id="6b191-376">8</span></span>|<span data-ttu-id="6b191-377">Завершена приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="6b191-378">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-378">No event data.</span></span>  
  
 [<span data-ttu-id="6b191-379">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="6b191-380">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="6b191-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="6b191-381">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-382">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-382">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-383">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-385">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-386">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-387">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-387">Event</span></span>|<span data-ttu-id="6b191-388">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-388">Event ID</span></span>|<span data-ttu-id="6b191-389">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="6b191-390">10</span><span class="sxs-lookup"><span data-stu-id="6b191-390">10</span></span>|<span data-ttu-id="6b191-391">Каждый раз выделяется около 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="6b191-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="6b191-392">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-393">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-393">Field name</span></span>|<span data-ttu-id="6b191-394">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-394">Data type</span></span>|<span data-ttu-id="6b191-395">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="6b191-396">AllocationAmount</span></span>|<span data-ttu-id="6b191-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-397">win:UInt32</span></span>|<span data-ttu-id="6b191-398">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="6b191-398">The allocation size, in bytes.</span></span> <span data-ttu-id="6b191-399">Это значение является точным для выделений, размер которых меньше длины ULONG (4 294 967 295 байт).</span><span class="sxs-lookup"><span data-stu-id="6b191-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="6b191-400">Если выделение больше, это поле содержит усеченное значение.</span><span class="sxs-lookup"><span data-stu-id="6b191-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="6b191-401">Используйте `AllocationAmount64` для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="6b191-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="6b191-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="6b191-402">AllocationKind</span></span>|<span data-ttu-id="6b191-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-403">win:UInt32</span></span>|<span data-ttu-id="6b191-404">0x0 — выделение для маленького объекта (выделение в куче маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="6b191-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="6b191-405">0x1 — выделение для большого объекта (выделение в куче больших объектов).</span><span class="sxs-lookup"><span data-stu-id="6b191-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="6b191-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-406">ClrInstanceID</span></span>|<span data-ttu-id="6b191-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-407">win:UInt16</span></span>|<span data-ttu-id="6b191-408">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="6b191-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="6b191-409">AllocationAmount64</span></span>|<span data-ttu-id="6b191-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6b191-410">win:UInt64</span></span>|<span data-ttu-id="6b191-411">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="6b191-411">The allocation size, in bytes.</span></span> <span data-ttu-id="6b191-412">Это значение является точным для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="6b191-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="6b191-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="6b191-413">TypeId</span></span>|<span data-ttu-id="6b191-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="6b191-414">win:Pointer</span></span>|<span data-ttu-id="6b191-415">Адрес MethodTable.</span><span class="sxs-lookup"><span data-stu-id="6b191-415">The address of the MethodTable.</span></span> <span data-ttu-id="6b191-416">Если в ходе этого события было выделено несколько типов объектов, указывается адрес MethodTable, соответствующий последнему выделенному объекту (объекту, вызвавшему превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="6b191-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="6b191-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="6b191-417">TypeName</span></span>|<span data-ttu-id="6b191-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6b191-418">win:UnicodeString</span></span>|<span data-ttu-id="6b191-419">Имя выделенного типа.</span><span class="sxs-lookup"><span data-stu-id="6b191-419">The name of the type that was allocated.</span></span> <span data-ttu-id="6b191-420">Если в ходе этого события было выделено несколько типов объектов, указывается тип последнего выделенного объекта (объекта, вызвавшего превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="6b191-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="6b191-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="6b191-421">HeapIndex</span></span>|<span data-ttu-id="6b191-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-422">win:UInt32</span></span>|<span data-ttu-id="6b191-423">Куча, в которой был выделен объект.</span><span class="sxs-lookup"><span data-stu-id="6b191-423">The heap where the object was allocated.</span></span> <span data-ttu-id="6b191-424">Это значение равно 0 (нулю) при выполнении сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="6b191-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="6b191-425">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="6b191-426">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="6b191-427">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-428">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-428">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-429">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-431">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-432">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-433">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-433">Event</span></span>|<span data-ttu-id="6b191-434">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-434">Event ID</span></span>|<span data-ttu-id="6b191-435">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="6b191-436">14</span><span class="sxs-lookup"><span data-stu-id="6b191-436">14</span></span>|<span data-ttu-id="6b191-437">Начало выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="6b191-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="6b191-438">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-438">No event data.</span></span>  
  
 [<span data-ttu-id="6b191-439">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="6b191-440">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="6b191-441">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-442">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-442">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-443">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-445">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-446">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-447">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-447">Event</span></span>|<span data-ttu-id="6b191-448">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-448">Event ID</span></span>|<span data-ttu-id="6b191-449">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="6b191-450">13</span><span class="sxs-lookup"><span data-stu-id="6b191-450">13</span></span>|<span data-ttu-id="6b191-451">Завершение выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="6b191-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="6b191-452">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="6b191-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6b191-453">Имя поля</span><span class="sxs-lookup"><span data-stu-id="6b191-453">Field name</span></span>|<span data-ttu-id="6b191-454">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b191-454">Data type</span></span>|<span data-ttu-id="6b191-455">Описание</span><span class="sxs-lookup"><span data-stu-id="6b191-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6b191-456">Количество</span><span class="sxs-lookup"><span data-stu-id="6b191-456">Count</span></span>|<span data-ttu-id="6b191-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6b191-457">win:UInt32</span></span>|<span data-ttu-id="6b191-458">Число выполненных методов завершения.</span><span class="sxs-lookup"><span data-stu-id="6b191-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="6b191-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6b191-459">ClrInstanceID</span></span>|<span data-ttu-id="6b191-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6b191-460">win:UInt16</span></span>|<span data-ttu-id="6b191-461">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6b191-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6b191-462">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="6b191-463">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="6b191-464">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-465">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-465">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-466">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-468">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-468">Informational (4)</span></span>|  
|<span data-ttu-id="6b191-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6b191-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6b191-470">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-471">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-472">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-472">Event</span></span>|<span data-ttu-id="6b191-473">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-473">Event ID</span></span>|<span data-ttu-id="6b191-474">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="6b191-475">11</span><span class="sxs-lookup"><span data-stu-id="6b191-475">11</span></span>|<span data-ttu-id="6b191-476">Был создан параллельный поток сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6b191-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="6b191-477">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-477">No event data.</span></span>  
  
 [<span data-ttu-id="6b191-478">К началу</span><span class="sxs-lookup"><span data-stu-id="6b191-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="6b191-479">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="6b191-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="6b191-480">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="6b191-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6b191-481">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="6b191-481">Keyword for raising the event</span></span>|<span data-ttu-id="6b191-482">Уровень</span><span class="sxs-lookup"><span data-stu-id="6b191-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6b191-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="6b191-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="6b191-484">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-484">Informational (4)</span></span>|  
|<span data-ttu-id="6b191-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6b191-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6b191-486">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="6b191-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="6b191-487">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="6b191-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6b191-488">событие</span><span class="sxs-lookup"><span data-stu-id="6b191-488">Event</span></span>|<span data-ttu-id="6b191-489">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6b191-489">Event ID</span></span>|<span data-ttu-id="6b191-490">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="6b191-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="6b191-491">12</span><span class="sxs-lookup"><span data-stu-id="6b191-491">12</span></span>|<span data-ttu-id="6b191-492">Параллельный поток сборки мусора был завершен.</span><span class="sxs-lookup"><span data-stu-id="6b191-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="6b191-493">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="6b191-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b191-494">См. также</span><span class="sxs-lookup"><span data-stu-id="6b191-494">See also</span></span>

- [<span data-ttu-id="6b191-495">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="6b191-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
