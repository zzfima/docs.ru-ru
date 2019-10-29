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
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040587"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="f80d9-102">События сборки мусора (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="f80d9-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="f80d9-103">Эти события собирают сведения, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="f80d9-104">Они помогают при диагностике и отладке, в том числе позволяют определить, сколько раз осуществлялась сборка мусора, какой объем памяти был освобожден в ходе сборки мусора и т. д.</span><span class="sxs-lookup"><span data-stu-id="f80d9-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="f80d9-105">Эта категория состоит из следующих событий:</span><span class="sxs-lookup"><span data-stu-id="f80d9-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="f80d9-106">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="f80d9-107">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="f80d9-108">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="f80d9-109">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="f80d9-110">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="f80d9-111">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="f80d9-112">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="f80d9-113">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="f80d9-114">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="f80d9-115">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="f80d9-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="f80d9-116">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="f80d9-117">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="f80d9-118">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="f80d9-119">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="f80d9-120">Событие GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="f80d9-121">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="f80d9-122">Дополнительные сведения см. в разделе [Ключевые слова и уровни ETW среды CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f80d9-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="f80d9-123">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-123">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-124">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-126">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-126">Informational (4)</span></span>|

<span data-ttu-id="f80d9-127">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-127">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-128">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-128">Event</span></span>|<span data-ttu-id="f80d9-129">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-129">Event ID</span></span>|<span data-ttu-id="f80d9-130">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="f80d9-131">1</span><span class="sxs-lookup"><span data-stu-id="f80d9-131">1</span></span>|<span data-ttu-id="f80d9-132">Сборка мусора начата.</span><span class="sxs-lookup"><span data-stu-id="f80d9-132">A garbage collection has started.</span></span>|

<span data-ttu-id="f80d9-133">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-133">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-134">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-134">Field name</span></span>|<span data-ttu-id="f80d9-135">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-135">Data type</span></span>|<span data-ttu-id="f80d9-136">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-137">Количество</span><span class="sxs-lookup"><span data-stu-id="f80d9-137">Count</span></span>|<span data-ttu-id="f80d9-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-138">win:UInt32</span></span>|<span data-ttu-id="f80d9-139">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="f80d9-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="f80d9-140">Глубина</span><span class="sxs-lookup"><span data-stu-id="f80d9-140">Depth</span></span>|<span data-ttu-id="f80d9-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-141">win:UInt32</span></span>|<span data-ttu-id="f80d9-142">Поколение, для которого выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="f80d9-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="f80d9-143">Причина</span><span class="sxs-lookup"><span data-stu-id="f80d9-143">Reason</span></span>|<span data-ttu-id="f80d9-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-144">win:UInt32</span></span>|<span data-ttu-id="f80d9-145">Причина запуска сборки мусора:</span><span class="sxs-lookup"><span data-stu-id="f80d9-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="f80d9-146">0x0 — выделение кучи маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="f80d9-147">0x1 — принудительная.</span><span class="sxs-lookup"><span data-stu-id="f80d9-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="f80d9-148">0x2 — недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="f80d9-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="f80d9-149">0x3 — пусто.</span><span class="sxs-lookup"><span data-stu-id="f80d9-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="f80d9-150">0x4 — выделение кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="f80d9-151">0x5 — недостаточно места (для кучи маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="f80d9-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="f80d9-152">0x6 — недостаточно места (для кучи больших объектов).</span><span class="sxs-lookup"><span data-stu-id="f80d9-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="f80d9-153">0x7 — принудительная, но не блокирующий.</span><span class="sxs-lookup"><span data-stu-id="f80d9-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="f80d9-154">Type</span><span class="sxs-lookup"><span data-stu-id="f80d9-154">Type</span></span>|<span data-ttu-id="f80d9-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-155">win:UInt32</span></span>|<span data-ttu-id="f80d9-156">0x0 — блокировка сборки мусора вне фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="f80d9-157">0x1 — фоновая сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="f80d9-158">0x2 — блокировка сборки мусора в ходе фоновой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="f80d9-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-159">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-160">win:UInt16</span></span>|<span data-ttu-id="f80d9-161">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="f80d9-162">Событие GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="f80d9-163">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-164">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-164">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-165">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-167">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-167">Informational (4)</span></span>|

<span data-ttu-id="f80d9-168">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-168">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-169">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-169">Event</span></span>|<span data-ttu-id="f80d9-170">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-170">Event ID</span></span>|<span data-ttu-id="f80d9-171">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="f80d9-172">2</span><span class="sxs-lookup"><span data-stu-id="f80d9-172">2</span></span>|<span data-ttu-id="f80d9-173">Сборка мусора закончена.</span><span class="sxs-lookup"><span data-stu-id="f80d9-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="f80d9-174">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-174">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-175">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-175">Field name</span></span>|<span data-ttu-id="f80d9-176">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-176">Data type</span></span>|<span data-ttu-id="f80d9-177">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-178">Количество</span><span class="sxs-lookup"><span data-stu-id="f80d9-178">Count</span></span>|<span data-ttu-id="f80d9-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-179">win:UInt32</span></span>|<span data-ttu-id="f80d9-180">Сборка мусора, *n*-я по счету.</span><span class="sxs-lookup"><span data-stu-id="f80d9-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="f80d9-181">Глубина</span><span class="sxs-lookup"><span data-stu-id="f80d9-181">Depth</span></span>|<span data-ttu-id="f80d9-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-182">win:UInt32</span></span>|<span data-ttu-id="f80d9-183">Поколение, для которого выполнялась сборка.</span><span class="sxs-lookup"><span data-stu-id="f80d9-183">The generation that was collected.</span></span>|
|<span data-ttu-id="f80d9-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-184">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-185">win:UInt16</span></span>|<span data-ttu-id="f80d9-186">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="f80d9-187">Событие GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="f80d9-188">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-189">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-189">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-190">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-192">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-192">Informational (4)</span></span>|

<span data-ttu-id="f80d9-193">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-193">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-194">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-194">Event</span></span>|<span data-ttu-id="f80d9-195">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-195">Event ID</span></span>|<span data-ttu-id="f80d9-196">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="f80d9-197">4</span><span class="sxs-lookup"><span data-stu-id="f80d9-197">4</span></span>|<span data-ttu-id="f80d9-198">Показывает статистику кучи по завершении каждой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="f80d9-199">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-199">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-200">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-200">Field name</span></span>|<span data-ttu-id="f80d9-201">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-201">Data type</span></span>|<span data-ttu-id="f80d9-202">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="f80d9-203">GenerationSize0</span></span>|<span data-ttu-id="f80d9-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-204">win:UInt64</span></span>|<span data-ttu-id="f80d9-205">Размер области памяти поколения 0 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="f80d9-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="f80d9-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="f80d9-206">TotalPromotedSize0</span></span>|<span data-ttu-id="f80d9-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-207">win:UInt64</span></span>|<span data-ttu-id="f80d9-208">Число байт, которые были переданы из поколения 0 в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="f80d9-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="f80d9-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="f80d9-209">GenerationSize1</span></span>|<span data-ttu-id="f80d9-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-210">win:UInt64</span></span>|<span data-ttu-id="f80d9-211">Размер области памяти поколения 1 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="f80d9-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="f80d9-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="f80d9-212">TotalPromotedSize1</span></span>|<span data-ttu-id="f80d9-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-213">win:UInt64</span></span>|<span data-ttu-id="f80d9-214">Число байт, которые были переданы из поколения 1 в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="f80d9-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="f80d9-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="f80d9-215">GenerationSize2</span></span>|<span data-ttu-id="f80d9-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-216">win:UInt64</span></span>|<span data-ttu-id="f80d9-217">Размер области памяти поколения 2 (в байтах).</span><span class="sxs-lookup"><span data-stu-id="f80d9-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="f80d9-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="f80d9-218">TotalPromotedSize2</span></span>|<span data-ttu-id="f80d9-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-219">win:UInt64</span></span>|<span data-ttu-id="f80d9-220">Число байт, оставшихся в поколении 2 после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="f80d9-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="f80d9-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="f80d9-221">GenerationSize3</span></span>|<span data-ttu-id="f80d9-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-222">win:UInt64</span></span>|<span data-ttu-id="f80d9-223">Размер кучи больших объектов (в байтах).</span><span class="sxs-lookup"><span data-stu-id="f80d9-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="f80d9-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="f80d9-224">TotalPromotedSize3</span></span>|<span data-ttu-id="f80d9-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-225">win:UInt64</span></span>|<span data-ttu-id="f80d9-226">Число байт, оставшихся в куче больших объектов после последней сборки.</span><span class="sxs-lookup"><span data-stu-id="f80d9-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="f80d9-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="f80d9-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="f80d9-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-228">win:UInt64</span></span>|<span data-ttu-id="f80d9-229">Общий размер (в байтах) объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="f80d9-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="f80d9-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="f80d9-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="f80d9-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-231">win:UInt64</span></span>|<span data-ttu-id="f80d9-232">Количество объектов, которые готовы к завершению.</span><span class="sxs-lookup"><span data-stu-id="f80d9-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="f80d9-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="f80d9-233">PinnedObjectCount</span></span>|<span data-ttu-id="f80d9-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-234">win:UInt32</span></span>|<span data-ttu-id="f80d9-235">Количество закрепленных (неподвижных) объектов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="f80d9-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="f80d9-236">SinkBlockCount</span></span>|<span data-ttu-id="f80d9-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-237">win:UInt32</span></span>|<span data-ttu-id="f80d9-238">Количество используемых блоков синхронизации.</span><span class="sxs-lookup"><span data-stu-id="f80d9-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="f80d9-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="f80d9-239">GCHandleCount</span></span>|<span data-ttu-id="f80d9-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-240">win:UInt32</span></span>|<span data-ttu-id="f80d9-241">Число используемых дескрипторов сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="f80d9-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-242">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-243">win:UInt16</span></span>|<span data-ttu-id="f80d9-244">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="f80d9-245">Событие GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="f80d9-246">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-247">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-247">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-248">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-250">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-250">Informational (4)</span></span>|

<span data-ttu-id="f80d9-251">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-251">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-252">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-252">Event</span></span>|<span data-ttu-id="f80d9-253">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-253">Event ID</span></span>|<span data-ttu-id="f80d9-254">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="f80d9-255">5</span><span class="sxs-lookup"><span data-stu-id="f80d9-255">5</span></span>|<span data-ttu-id="f80d9-256">Был создан новый сегмент сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="f80d9-257">Кроме того, при включении трассировки для уже работающего процесса это событие создается для каждого существующего сегмента.</span><span class="sxs-lookup"><span data-stu-id="f80d9-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="f80d9-258">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-258">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-259">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-259">Field name</span></span>|<span data-ttu-id="f80d9-260">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-260">Data type</span></span>|<span data-ttu-id="f80d9-261">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-262">Адрес</span><span class="sxs-lookup"><span data-stu-id="f80d9-262">Address</span></span>|<span data-ttu-id="f80d9-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-263">win:UInt64</span></span>|<span data-ttu-id="f80d9-264">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="f80d9-264">The address of the segment.</span></span>|
|<span data-ttu-id="f80d9-265">Размер</span><span class="sxs-lookup"><span data-stu-id="f80d9-265">Size</span></span>|<span data-ttu-id="f80d9-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-266">win:UInt64</span></span>|<span data-ttu-id="f80d9-267">Размер сегмента.</span><span class="sxs-lookup"><span data-stu-id="f80d9-267">The size of the segment.</span></span>|
|<span data-ttu-id="f80d9-268">Type</span><span class="sxs-lookup"><span data-stu-id="f80d9-268">Type</span></span>|<span data-ttu-id="f80d9-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-269">win:UInt32</span></span>|<span data-ttu-id="f80d9-270">0x0 — куча маленьких объектов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="f80d9-271">0x1 — куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="f80d9-272">0x2 — куча только для чтения.</span><span class="sxs-lookup"><span data-stu-id="f80d9-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="f80d9-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-273">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-274">win:UInt16</span></span>|<span data-ttu-id="f80d9-275">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="f80d9-276">Обратите внимание, что размер сегментов, выделенных сборщиком мусора, зависит от реализации и может быть изменен в любое время, в том числе при периодических обновлениях.</span><span class="sxs-lookup"><span data-stu-id="f80d9-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="f80d9-277">Приложение не должно делать никаких допущений относительно размера определенного сегмента, полагаться на него или пытаться настроить объем памяти, доступный для выделения сегментов.</span><span class="sxs-lookup"><span data-stu-id="f80d9-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="f80d9-278">Событие GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="f80d9-279">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-280">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-280">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-281">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-283">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-283">Informational (4)</span></span>|

<span data-ttu-id="f80d9-284">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-284">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-285">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-285">Event</span></span>|<span data-ttu-id="f80d9-286">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-286">Event ID</span></span>|<span data-ttu-id="f80d9-287">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="f80d9-288">6</span><span class="sxs-lookup"><span data-stu-id="f80d9-288">6</span></span>|<span data-ttu-id="f80d9-289">Сегмент сборки мусора был освобожден.</span><span class="sxs-lookup"><span data-stu-id="f80d9-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="f80d9-290">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-290">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-291">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-291">Field name</span></span>|<span data-ttu-id="f80d9-292">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-292">Data type</span></span>|<span data-ttu-id="f80d9-293">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-294">Адрес</span><span class="sxs-lookup"><span data-stu-id="f80d9-294">Address</span></span>|<span data-ttu-id="f80d9-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-295">win:UInt64</span></span>|<span data-ttu-id="f80d9-296">Адрес сегмента.</span><span class="sxs-lookup"><span data-stu-id="f80d9-296">The address of the segment.</span></span>|
|<span data-ttu-id="f80d9-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-297">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-298">win:UInt16</span></span>|<span data-ttu-id="f80d9-299">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="f80d9-300">Событие GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="f80d9-301">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-302">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-302">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-303">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-305">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-305">Informational (4)</span></span>|

<span data-ttu-id="f80d9-306">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-306">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-307">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-307">Event</span></span>|<span data-ttu-id="f80d9-308">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-308">Event ID</span></span>|<span data-ttu-id="f80d9-309">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="f80d9-310">7</span><span class="sxs-lookup"><span data-stu-id="f80d9-310">7</span></span>|<span data-ttu-id="f80d9-311">Началось возобновление приостановленной среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="f80d9-312">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="f80d9-313">Событие GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="f80d9-314">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-315">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-315">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-316">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-318">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-318">Informational (4)</span></span>|

<span data-ttu-id="f80d9-319">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-319">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-320">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-320">Event</span></span>|<span data-ttu-id="f80d9-321">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="f80d9-321">Event Id</span></span>|<span data-ttu-id="f80d9-322">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="f80d9-323">3</span><span class="sxs-lookup"><span data-stu-id="f80d9-323">3</span></span>|<span data-ttu-id="f80d9-324">Возобновление приостановленной среды CLR завершено.</span><span class="sxs-lookup"><span data-stu-id="f80d9-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="f80d9-325">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="f80d9-326">Событие GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="f80d9-327">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-328">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-328">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-329">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-331">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-331">Informational (4)</span></span>|

<span data-ttu-id="f80d9-332">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-332">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-333">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-333">Event</span></span>|<span data-ttu-id="f80d9-334">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-334">Event ID</span></span>|<span data-ttu-id="f80d9-335">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="f80d9-336">9</span><span class="sxs-lookup"><span data-stu-id="f80d9-336">9</span></span>|<span data-ttu-id="f80d9-337">Началась приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="f80d9-338">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-338">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-339">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-339">Field name</span></span>|<span data-ttu-id="f80d9-340">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-340">Data type</span></span>|<span data-ttu-id="f80d9-341">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-342">Причина</span><span class="sxs-lookup"><span data-stu-id="f80d9-342">Reason</span></span>|<span data-ttu-id="f80d9-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-343">win:UInt16</span></span>|<span data-ttu-id="f80d9-344">0x0 — другое.</span><span class="sxs-lookup"><span data-stu-id="f80d9-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="f80d9-345">0x1 — сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="f80d9-346">0x2 — завершение работы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f80d9-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="f80d9-347">0x3 — свертка кода.</span><span class="sxs-lookup"><span data-stu-id="f80d9-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="f80d9-348">0x4 — завершение работы.</span><span class="sxs-lookup"><span data-stu-id="f80d9-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="f80d9-349">0x5 — отладчик.</span><span class="sxs-lookup"><span data-stu-id="f80d9-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="f80d9-350">0x6 — подготовка к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="f80d9-351">Количество</span><span class="sxs-lookup"><span data-stu-id="f80d9-351">Count</span></span>|<span data-ttu-id="f80d9-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-352">win:UInt32</span></span>|<span data-ttu-id="f80d9-353">Счетчик сборки мусора на текущий момент времени.</span><span class="sxs-lookup"><span data-stu-id="f80d9-353">The GC count at the time.</span></span> <span data-ttu-id="f80d9-354">Обычно после этого отображается последующее событие запуска сборки мусора, а значение увеличивается на 1 в соответствии с увеличением индекса сборки мусора в ходе этого процесса.</span><span class="sxs-lookup"><span data-stu-id="f80d9-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="f80d9-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-355">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-356">win:UInt16</span></span>|<span data-ttu-id="f80d9-357">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="f80d9-358">Событие GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="f80d9-359">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-360">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-360">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-361">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-363">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-363">Informational (4)</span></span>|

<span data-ttu-id="f80d9-364">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-364">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-365">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-365">Event</span></span>|<span data-ttu-id="f80d9-366">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-366">Event ID</span></span>|<span data-ttu-id="f80d9-367">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="f80d9-368">8</span><span class="sxs-lookup"><span data-stu-id="f80d9-368">8</span></span>|<span data-ttu-id="f80d9-369">Завершена приостановка механизма выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="f80d9-370">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="f80d9-371">Событие GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="f80d9-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="f80d9-372">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-373">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-373">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-374">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-376">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-376">Informational (4)</span></span>|

<span data-ttu-id="f80d9-377">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-377">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-378">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-378">Event</span></span>|<span data-ttu-id="f80d9-379">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-379">Event ID</span></span>|<span data-ttu-id="f80d9-380">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="f80d9-381">10</span><span class="sxs-lookup"><span data-stu-id="f80d9-381">10</span></span>|<span data-ttu-id="f80d9-382">Каждый раз выделяется около 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="f80d9-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="f80d9-383">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-383">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-384">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-384">Field name</span></span>|<span data-ttu-id="f80d9-385">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-385">Data type</span></span>|<span data-ttu-id="f80d9-386">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="f80d9-387">AllocationAmount</span></span>|<span data-ttu-id="f80d9-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-388">win:UInt32</span></span>|<span data-ttu-id="f80d9-389">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="f80d9-389">The allocation size, in bytes.</span></span> <span data-ttu-id="f80d9-390">Это значение является точным для выделений, размер которых меньше длины ULONG (4 294 967 295 байт).</span><span class="sxs-lookup"><span data-stu-id="f80d9-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="f80d9-391">Если выделение больше, это поле содержит усеченное значение.</span><span class="sxs-lookup"><span data-stu-id="f80d9-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="f80d9-392">Используйте `AllocationAmount64` для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="f80d9-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="f80d9-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="f80d9-393">AllocationKind</span></span>|<span data-ttu-id="f80d9-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-394">win:UInt32</span></span>|<span data-ttu-id="f80d9-395">0x0 — выделение для маленького объекта (выделение в куче маленьких объектов).</span><span class="sxs-lookup"><span data-stu-id="f80d9-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="f80d9-396">0x1 — выделение для большого объекта (выделение в куче больших объектов).</span><span class="sxs-lookup"><span data-stu-id="f80d9-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="f80d9-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-397">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-398">win:UInt16</span></span>|<span data-ttu-id="f80d9-399">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="f80d9-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="f80d9-400">AllocationAmount64</span></span>|<span data-ttu-id="f80d9-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f80d9-401">win:UInt64</span></span>|<span data-ttu-id="f80d9-402">Размер выделения в байтах.</span><span class="sxs-lookup"><span data-stu-id="f80d9-402">The allocation size, in bytes.</span></span> <span data-ttu-id="f80d9-403">Это значение является точным для очень больших выделений.</span><span class="sxs-lookup"><span data-stu-id="f80d9-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="f80d9-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="f80d9-404">TypeId</span></span>|<span data-ttu-id="f80d9-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="f80d9-405">win:Pointer</span></span>|<span data-ttu-id="f80d9-406">Адрес MethodTable.</span><span class="sxs-lookup"><span data-stu-id="f80d9-406">The address of the MethodTable.</span></span> <span data-ttu-id="f80d9-407">Если в ходе этого события было выделено несколько типов объектов, указывается адрес MethodTable, соответствующий последнему выделенному объекту (объекту, вызвавшему превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="f80d9-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="f80d9-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="f80d9-408">TypeName</span></span>|<span data-ttu-id="f80d9-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f80d9-409">win:UnicodeString</span></span>|<span data-ttu-id="f80d9-410">Имя выделенного типа.</span><span class="sxs-lookup"><span data-stu-id="f80d9-410">The name of the type that was allocated.</span></span> <span data-ttu-id="f80d9-411">Если в ходе этого события было выделено несколько типов объектов, указывается тип последнего выделенного объекта (объекта, вызвавшего превышение порогового значения 100 КБ).</span><span class="sxs-lookup"><span data-stu-id="f80d9-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="f80d9-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="f80d9-412">HeapIndex</span></span>|<span data-ttu-id="f80d9-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-413">win:UInt32</span></span>|<span data-ttu-id="f80d9-414">Куча, в которой был выделен объект.</span><span class="sxs-lookup"><span data-stu-id="f80d9-414">The heap where the object was allocated.</span></span> <span data-ttu-id="f80d9-415">Это значение равно 0 (нулю) при выполнении сборки мусора на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="f80d9-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="f80d9-416">Событие GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="f80d9-417">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-418">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-418">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-419">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-421">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-421">Informational (4)</span></span>|

<span data-ttu-id="f80d9-422">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-422">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-423">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-423">Event</span></span>|<span data-ttu-id="f80d9-424">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-424">Event ID</span></span>|<span data-ttu-id="f80d9-425">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="f80d9-426">14</span><span class="sxs-lookup"><span data-stu-id="f80d9-426">14</span></span>|<span data-ttu-id="f80d9-427">Начало выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="f80d9-427">The start of running finalizers.</span></span>|

<span data-ttu-id="f80d9-428">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="f80d9-429">Событие GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="f80d9-430">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-431">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-431">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-432">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-434">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-434">Informational (4)</span></span>|

<span data-ttu-id="f80d9-435">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-435">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-436">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-436">Event</span></span>|<span data-ttu-id="f80d9-437">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-437">Event ID</span></span>|<span data-ttu-id="f80d9-438">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="f80d9-439">13</span><span class="sxs-lookup"><span data-stu-id="f80d9-439">13</span></span>|<span data-ttu-id="f80d9-440">Завершение выполнения методов завершения.</span><span class="sxs-lookup"><span data-stu-id="f80d9-440">The end of running finalizers.</span></span>|

<span data-ttu-id="f80d9-441">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-441">The following table shows the event data:</span></span>

|<span data-ttu-id="f80d9-442">Имя поля</span><span class="sxs-lookup"><span data-stu-id="f80d9-442">Field name</span></span>|<span data-ttu-id="f80d9-443">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f80d9-443">Data type</span></span>|<span data-ttu-id="f80d9-444">Описание</span><span class="sxs-lookup"><span data-stu-id="f80d9-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="f80d9-445">Количество</span><span class="sxs-lookup"><span data-stu-id="f80d9-445">Count</span></span>|<span data-ttu-id="f80d9-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f80d9-446">win:UInt32</span></span>|<span data-ttu-id="f80d9-447">Число выполненных методов завершения.</span><span class="sxs-lookup"><span data-stu-id="f80d9-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="f80d9-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f80d9-448">ClrInstanceID</span></span>|<span data-ttu-id="f80d9-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f80d9-449">win:UInt16</span></span>|<span data-ttu-id="f80d9-450">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f80d9-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="f80d9-451">Событие GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="f80d9-452">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-453">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-453">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-454">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-456">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-456">Informational (4)</span></span>|
|<span data-ttu-id="f80d9-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f80d9-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f80d9-458">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-458">Informational (4)</span></span>|

<span data-ttu-id="f80d9-459">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-459">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-460">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-460">Event</span></span>|<span data-ttu-id="f80d9-461">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-461">Event ID</span></span>|<span data-ttu-id="f80d9-462">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="f80d9-463">11</span><span class="sxs-lookup"><span data-stu-id="f80d9-463">11</span></span>|<span data-ttu-id="f80d9-464">Был создан параллельный поток сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f80d9-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="f80d9-465">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="f80d9-466">Событие GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="f80d9-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="f80d9-467">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="f80d9-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="f80d9-468">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="f80d9-468">Keyword for raising the event</span></span>|<span data-ttu-id="f80d9-469">Уровень</span><span class="sxs-lookup"><span data-stu-id="f80d9-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f80d9-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="f80d9-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="f80d9-471">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-471">Informational (4)</span></span>|
|<span data-ttu-id="f80d9-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f80d9-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f80d9-473">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="f80d9-473">Informational (4)</span></span>|

<span data-ttu-id="f80d9-474">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="f80d9-474">The following table shows the event information:</span></span>

|<span data-ttu-id="f80d9-475">событие</span><span class="sxs-lookup"><span data-stu-id="f80d9-475">Event</span></span>|<span data-ttu-id="f80d9-476">Код события</span><span class="sxs-lookup"><span data-stu-id="f80d9-476">Event ID</span></span>|<span data-ttu-id="f80d9-477">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="f80d9-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="f80d9-478">12</span><span class="sxs-lookup"><span data-stu-id="f80d9-478">12</span></span>|<span data-ttu-id="f80d9-479">Параллельный поток сборки мусора был завершен.</span><span class="sxs-lookup"><span data-stu-id="f80d9-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="f80d9-480">Нет данных события.</span><span class="sxs-lookup"><span data-stu-id="f80d9-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="f80d9-481">См. также</span><span class="sxs-lookup"><span data-stu-id="f80d9-481">See also</span></span>

- [<span data-ttu-id="f80d9-482">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="f80d9-482">CLR ETW Events</span></span>](clr-etw-events.md)
