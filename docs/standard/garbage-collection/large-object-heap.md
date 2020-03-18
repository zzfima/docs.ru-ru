---
title: Куча больших объектов в Windows — .NET
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
ms.openlocfilehash: 5125b76dd26ffa4fb363ecf8449f65b490f57b93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74283624"
---
# <a name="the-large-object-heap-on-windows-systems"></a><span data-ttu-id="ba2f9-102">Куча больших объектов в системах Windows</span><span class="sxs-lookup"><span data-stu-id="ba2f9-102">The large object heap on Windows systems</span></span>

<span data-ttu-id="ba2f9-103">Сборщик мусора .NET (GC) разделяет объекты на две категории — большие и маленькие.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-103">The .NET Garbage Collector (GC) divides objects up into small and large objects.</span></span> <span data-ttu-id="ba2f9-104">Некоторые атрибуты больших объектов становятся более значимыми, чем атрибуты маленьких.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-104">When an object is large, some of its attributes become more significant than if the object is small.</span></span> <span data-ttu-id="ba2f9-105">Например, для сжатия объекта (копирования его в другое место в куче) требуется много ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-105">For instance, compacting it -- that is, copying it in memory elsewhere on the heap -- can be expensive.</span></span> <span data-ttu-id="ba2f9-106">Поэтому сборщик мусора .NET помещает большие объекты в кучу больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-106">Because of this, the .NET Garbage Collector places large objects on the large object heap (LOH).</span></span> <span data-ttu-id="ba2f9-107">В этом разделе мы подробно рассмотрим кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-107">In this topic, we'll look at the large object heap in depth.</span></span> <span data-ttu-id="ba2f9-108">Мы поговорим о том, что такое большой объект, как собираются большие объекты и как они влияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-108">We'll discuss what qualifies an object as a large object, how these large objects are collected, and what kind of performance implications large objects impose.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba2f9-109">В этом разделе рассматривается куча больших объектов в .NET Framework и .NET Core только в системах Windows.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-109">This topic discusses the large object heap in the .NET Framework and .NET Core running on Windows systems only.</span></span> <span data-ttu-id="ba2f9-110">Эти сведения не относятся к куче больших объектов в реализациях .NET на других платформах.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-110">It does not cover the LOH running on .NET implementations on other platforms.</span></span>

## <a name="how-an-object-ends-up-on-the-large-object-heap-and-how-gc-handles-them"></a><span data-ttu-id="ba2f9-111">Как объект оказывается в куче больших объектов и как сборщик мусора обрабатывает их</span><span class="sxs-lookup"><span data-stu-id="ba2f9-111">How an object ends up on the large object heap and how GC handles them</span></span>

<span data-ttu-id="ba2f9-112">Большим считается объект не менее 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-112">If an object is greater than or equal to 85,000 bytes in size, it’s considered a large object.</span></span> <span data-ttu-id="ba2f9-113">Это число рассчитано путем настройки производительности.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-113">This number was determined by performance tuning.</span></span> <span data-ttu-id="ba2f9-114">Если запрашивается выделение 85 000 или более байтов, среда выполнения отправляет объект в кучу больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-114">When an object allocation request is for 85,000 or more bytes, the runtime allocates it on the large object heap.</span></span>

<span data-ttu-id="ba2f9-115">Чтобы понять, что это значит, давайте рассмотрим основные принципы работы сборщика мусора .NET.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-115">To understand what this means, it's useful to examine some fundamentals about the .NET GC.</span></span>

<span data-ttu-id="ba2f9-116">Сборщик мусора .NET работает по поколениям.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-116">The .NET Garbage Collector is a generational collector.</span></span> <span data-ttu-id="ba2f9-117">Он имеет три поколения: поколение 0, поколение 1 и поколение 2.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-117">It has three generations: generation 0, generation 1, and generation 2.</span></span> <span data-ttu-id="ba2f9-118">Причина использования трех поколений в том, что в правильно настроенных приложениях большинство объектов отмирают на стадии gen0.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-118">The reason for having 3 generations is that, in a well-tuned app, most objects die in gen0.</span></span> <span data-ttu-id="ba2f9-119">Например, в серверном приложении выделения памяти, связанные с каждым запросом, должны исчезнуть после завершения запроса.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-119">For example, in a server app, the allocations associated with each request should die after the request is finished.</span></span> <span data-ttu-id="ba2f9-120">Находящиеся в пути запросы на выделение памяти достигнут поколения 1 и умрут там.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-120">The in-flight allocation requests will make it into gen1 and die there.</span></span> <span data-ttu-id="ba2f9-121">По сути, поколение 1 служит буфером между областями молодых объектов и областями долгоживущих объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-121">Essentially, gen1 acts as a buffer between young object areas and long-lived object areas.</span></span>

<span data-ttu-id="ba2f9-122">Маленькие объекты всегда размещаются в поколении 0 и, в зависимости от времени их существования, могут перейти в поколение 1 или поколение 2.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-122">Small objects are always allocated in generation 0 and, depending on their lifetime, may be promoted to generation 1 or generation2.</span></span> <span data-ttu-id="ba2f9-123">Большие объекты всегда размещаются в поколении 2.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-123">Large objects are always allocated in generation 2.</span></span>

<span data-ttu-id="ba2f9-124">Большие объекты принадлежат к поколению 2, поскольку они собираются только при сборке поколения 2.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-124">Large objects belong to generation 2 because they are collected only during a generation 2 collection.</span></span> <span data-ttu-id="ba2f9-125">При сборке поколения собираются и все предыдущие поколения.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-125">When a generation is collected, all its younger generation(s) are also collected.</span></span> <span data-ttu-id="ba2f9-126">Например, когда происходит сборка мусора поколения 1, собираются поколения 1 и 0.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-126">For example, when a generation 1 GC happens, both generation 1 and 0 are collected.</span></span> <span data-ttu-id="ba2f9-127">А когда происходит сборка мусора поколения 2, собирается вся куча.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-127">And when a generation 2 GC happens, the whole heap is collected.</span></span> <span data-ttu-id="ba2f9-128">Поэтому сборка мусора поколения 2 также называется *полной сборкой мусора*.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-128">For this reason, a generation 2 GC is also called a *full GC*.</span></span> <span data-ttu-id="ba2f9-129">В этой статье используется термин "сборка мусора поколения 2", а не "полная сборка мусора", но эти термины равнозначны.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-129">This article refers to generation 2 GC instead of full GC, but the terms are interchangeable.</span></span>

<span data-ttu-id="ba2f9-130">Поколения обеспечивают логическое представление кучи сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-130">Generations provide a logical view of the GC heap.</span></span> <span data-ttu-id="ba2f9-131">На физическом уровне объекты существуют в управляемых сегментах кучи.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-131">Physically, objects live in managed heap segments.</span></span> <span data-ttu-id="ba2f9-132">*Управляемый сегмент кучи* — это блок памяти, который сборщик мусора резервирует в ОС через вызов [функции VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) от имени управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-132">A *managed heap segment* is a chunk of memory that the GC reserves from the OS by calling the [VirtualAlloc function](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) on behalf of managed code.</span></span> <span data-ttu-id="ba2f9-133">При загрузке CLR сборка мусора выделяет два первоначальных сегмента кучи: один для маленьких объектов (куча маленьких объектов, или SOH) и один для больших объектов (куча больших объектов, или LOH).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-133">When the CLR is loaded, the GC allocates two initial heap segments: one for small objects (the small object heap, or SOH), and one for large objects (the large object heap).</span></span>

<span data-ttu-id="ba2f9-134">После этого запросы на выделение памяти удовлетворяются путем размещения управляемых объектов в одном из этих сегментов управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-134">The allocation requests are then satisfied by putting managed objects on these managed heap segments.</span></span> <span data-ttu-id="ba2f9-135">Если объект меньше 85 000 байтов, он будет помещен в сегмент SOH. В противном случае он помещается в сегмент LOH.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-135">If the object is less than 85,000 bytes, it is put on the segment for the SOH; otherwise, it is put on an LOH segment.</span></span> <span data-ttu-id="ba2f9-136">Память из сегментов выделяется (блоками) по мере того, как в них помещается все больше объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-136">Segments are committed (in smaller chunks) as more and more objects are allocated onto them.</span></span>
<span data-ttu-id="ba2f9-137">В куче маленьких объектов объекты, пережившие сборку мусора, переходят в следующее поколение.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-137">For the SOH, objects that survive a GC are promoted to the next generation.</span></span> <span data-ttu-id="ba2f9-138">Объекты, пережившие сборку мусора поколения 0, считаются объектами поколения 1 и так далее.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-138">Objects that survive a generation 0 collection are now considered generation 1 objects, and so on.</span></span> <span data-ttu-id="ba2f9-139">Однако объекты, пережившие сборку мусора последнего поколения, по-прежнему будут относиться к этому поколению.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-139">However, objects that survive the oldest generation are still considered to be in the oldest generation.</span></span> <span data-ttu-id="ba2f9-140">Другими словами, выжившие из поколения 2 — это объекты поколения 2; а выжившие из кучи больших объектов — это объекты кучи больших объектов (которые собираются с поколением 2).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-140">In other words, survivors from generation 2 are generation 2 objects; and survivors from the LOH are LOH objects (which are collected with gen2).</span></span>

<span data-ttu-id="ba2f9-141">Пользовательский код может размещать объекты только в поколении 0 (маленькие объекты) или в куче больших объектов (большие объекты).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-141">User code can only allocate in generation 0 (small objects) or the LOH (large objects).</span></span> <span data-ttu-id="ba2f9-142">Только сборщик мусора может помещать объекты в поколение 1 (повышая уровень выживших из поколения 0) и поколение 2 (повышая уровень выживших из поколений 1 и 2).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-142">Only the GC can “allocate” objects in generation 1 (by promoting survivors from generation 0) and generation 2 (by promoting survivors from generations 1 and 2).</span></span>

<span data-ttu-id="ba2f9-143">При запуске сборки мусора сборщик мусора отслеживает живые объекты и сжимает их.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-143">When a garbage collection is triggered, the GC traces through the live objects and compacts them.</span></span> <span data-ttu-id="ba2f9-144">Но поскольку сжатие требует большого количества ресурсов, сборщик мусора *сметает* кучу больших объектов, составляя свободный список из мертвых объектов, которые можно повторно использовать позднее для удовлетворения запросов на выделение памяти для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-144">But because compaction is expensive, the GC *sweeps* the LOH; it makes a free list out of dead objects that can be reused later to satisfy large object allocation requests.</span></span> <span data-ttu-id="ba2f9-145">Смежные мертвые объекты превращаются в один свободный объект.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-145">Adjacent dead objects are made into one free object.</span></span>

<span data-ttu-id="ba2f9-146">.NET Core и .NET Framework (начиная с .NET Framework 4.5.1) включают в себя свойство <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType>, которое дает пользователям возможность указать, что необходимо сжать кучу больших объектов при следующей полной блокирующей сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-146">.NET Core and .NET Framework (starting with .NET Framework 4.5.1) include the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType> property that allows users to specify that the LOH should be compacted during the next full blocking GC.</span></span> <span data-ttu-id="ba2f9-147">И в будущем .NET может сжимать кучу больших объектов автоматически.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-147">And in the future, .NET may decide to compact the LOH automatically.</span></span> <span data-ttu-id="ba2f9-148">Это означает, что в случае выделения больших объектов, перемещение которых недопустимо, их по-прежнему следует закреплять.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-148">This means that, if you allocate large objects and want to make sure that they don’t move, you should still pin them.</span></span>

<span data-ttu-id="ba2f9-149">На рис. 1 проиллюстрирована ситуация, где сборщик мусора формирует поколение 1 после первого поколения 0, где объекты `Obj1` и `Obj3` мертвы; и он формирует поколение 2 после первого поколения 1, где объекты `Obj2` и `Obj5` мертвы.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-149">Figure 1 illustrates a scenario where the GC forms generation 1 after the first generation 0 GC where `Obj1` and `Obj3` are dead, and it forms generation 2 after the first generation 1 GC where `Obj2` and `Obj5` are dead.</span></span> <span data-ttu-id="ba2f9-150">Это и следующие изображения приводятся только для иллюстрации; они содержат мало объектов, чтобы продемонстрировать происходящее в куче.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-150">Note that this and the following figures are only for illustration purposes; they contain very few objects to better show what happens on the heap.</span></span> <span data-ttu-id="ba2f9-151">На самом деле сборщик мусора обрабатывает гораздо больше объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-151">In reality, many more objects are typically involved in a GC.</span></span>

![Рис. 1. Сборка мусора поколения 0 и поколения 1](media/loh/loh-figure-1.jpg)\
<span data-ttu-id="ba2f9-153">Рис. 1. Сборка мусора поколения 0 и поколения 1.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-153">Figure 1: A generation 0 and a generation 1 GC.</span></span>

<span data-ttu-id="ba2f9-154">На рисунке 2 показано, что после сборки мусора поколения 2, где объекты `Obj1` и `Obj2` мертвы, сборщик мусора создает непрерывное свободное пространство в памяти, которое занимали объекты `Obj1` и `Obj2`. Это пространство затем используется для удовлетворения запроса на выделение памяти для объекта `Obj4`.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-154">Figure 2 shows that after a generation 2 GC which saw that `Obj1` and `Obj2` are dead, the GC forms contiguous free space out of memory that used to be occupied by `Obj1` and `Obj2`, which then was used to satisfy an allocation request for `Obj4`.</span></span> <span data-ttu-id="ba2f9-155">Пространство после последнего объекта `Obj3` и до конца сегмента все еще может быть использовано для удовлетворения дальнейших запросов на выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-155">The space after the last object, `Obj3`, to end of the segment can also be used to satisfy allocation requests.</span></span>

![Рис. 2. После сборки мусора поколения 2](media/loh/loh-figure-2.jpg)\
<span data-ttu-id="ba2f9-157">Рис. 2. После сборки мусора поколения 2</span><span class="sxs-lookup"><span data-stu-id="ba2f9-157">Figure 2: After a generation 2 GC</span></span>

<span data-ttu-id="ba2f9-158">Если свободного пространства недостаточно для выполнения запросов на выделение памяти для больших объектов, сборщик мусора пытается получить дополнительные сегменты от ОС.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-158">If there isn't enough free space to accommodate the large object allocation requests, the GC first attempts to acquire more segments from the OS.</span></span> <span data-ttu-id="ba2f9-159">Если это не удается, он инициирует сборку мусора поколения 2 в надежде освободить место.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-159">If that fails, it triggers a generation 2 GC in the hope of freeing up some space.</span></span>

<span data-ttu-id="ba2f9-160">В ходе сборки мусора поколения 1 или 2 сборщик мусора отдает ОС сегменты, в которых нет живых объектов (вызывая [функцию VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree)).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-160">During a generation 1 or generation 2 GC, the garbage collector releases segments that have no live objects on them back to the OS by calling the [VirtualFree function](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree).</span></span> <span data-ttu-id="ba2f9-161">Свободное место после последнего живого объекта до конца сегмента освобождается (за исключением временных сегментов с объектами поколения 0 и 1, в которых сборщик мусора сохраняет свободное пространство, поскольку вскоре приложение будет размещать в него объекты).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-161">Space after the last live object to the end of the segment is decommitted (except on the ephemeral segment where gen0/gen1 live, where the garbage collector does keep some committed because your application will be allocating in it right away).</span></span> <span data-ttu-id="ba2f9-162">А свободные пространства остаются выделенными, хотя и сбрасываются, освобождая ОС от необходимости записывать данные с них обратно на диск.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-162">And the free spaces remain committed though they are reset, meaning that the OS doesn’t need to write data in them back to disk.</span></span>

<span data-ttu-id="ba2f9-163">Поскольку куча больших объектов собирается только во время сборки мусора поколения 2, сегмент этой кучи можно освободить только во время этой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-163">Since the LOH is only collected during generation 2 GCs, the LOH segment can only be freed during such a GC.</span></span> <span data-ttu-id="ba2f9-164">На рисунке 3 показан сценарий, где сборщик мусора возвращает ОС один сегмент (сегмент 2) и освобождает дополнительное место в оставшихся сегментах.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-164">Figure 3 illustrates a scenario where the garbage collector releases one segment (segment 2) back to the OS and decommits more space on the remaining segments.</span></span> <span data-ttu-id="ba2f9-165">Если освободившееся пространство в конце сегмента необходимо использовать для удовлетворения запросов на выделение памяти для большого объекта, он фиксирует память снова.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-165">If it needs to use the decommitted space at the end of the segment to satisfy large object allocation requests, it commits the memory again.</span></span> <span data-ttu-id="ba2f9-166">(Дополнительные сведения о фиксации и освобождении см. в документации по [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-166">(For an explanation of commit/decommit, see the documentation for [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc).</span></span>

![Рис. 3. Куча больших объектов после сборки мусора поколения 2](media/loh/loh-figure-3.jpg)\
<span data-ttu-id="ba2f9-168">Рис. 3. Куча больших объектов после сборки мусора поколения 2</span><span class="sxs-lookup"><span data-stu-id="ba2f9-168">Figure 3: The LOH after a generation 2 GC</span></span>

## <a name="when-is-a-large-object-collected"></a><span data-ttu-id="ba2f9-169">Когда собираются большие объекты?</span><span class="sxs-lookup"><span data-stu-id="ba2f9-169">When is a large object collected?</span></span>

<span data-ttu-id="ba2f9-170">Как правило, сборка мусора происходит при выполнении одного из следующих трех условий:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-170">In general, a GC occurs when one of the following 3 conditions happens:</span></span>

- <span data-ttu-id="ba2f9-171">Выделение памяти превышает пороговое значение для поколения 0 или больших объектов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-171">Allocation exceeds the generation 0 or large object threshold.</span></span>

  <span data-ttu-id="ba2f9-172">Пороговое значение является свойством поколения.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-172">The threshold is a property of a generation.</span></span> <span data-ttu-id="ba2f9-173">Пороговое значение для поколения задается, когда сборщик мусора распределяет в него объекты.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-173">A threshold for a generation is set when the garbage collector allocates objects into it.</span></span> <span data-ttu-id="ba2f9-174">При превышении порогового значения для этого поколения происходит сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-174">When the threshold is exceeded, a GC is triggered on that generation.</span></span> <span data-ttu-id="ba2f9-175">При распределении маленьких или больших объектов учитываются пороговые значения для поколения 0 или кучи больших объектов соответственно.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-175">When you allocate small or large objects, you consume generation 0 and the LOH’s thresholds, respectively.</span></span> <span data-ttu-id="ba2f9-176">Когда сборщик мусора распределяет объекты в поколения 1 и 2, учитываются соответствующие пороговые значения.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-176">When the garbage collector allocates into generation 1 and 2, it consumes their thresholds.</span></span> <span data-ttu-id="ba2f9-177">Эти пороговые значения динамически настраиваются в ходе работы программы.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-177">These thresholds are dynamically tuned as the program runs.</span></span>

  <span data-ttu-id="ba2f9-178">Это типичный случай. Как правило, сборка мусора происходит в связи с распределениями в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-178">This is the typical case; most GCs happen because of allocations on the managed heap.</span></span>

- <span data-ttu-id="ba2f9-179">вызывается метод <xref:System.GC.Collect%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ba2f9-179">The <xref:System.GC.Collect%2A?displayProperty=nameWithType> method is called.</span></span>

  <span data-ttu-id="ba2f9-180">Если вызывается метод <xref:System.GC.Collect?displayProperty=nameWithType> без параметров или другая перегрузка передается <xref:System.GC.MaxGeneration?displayProperty=nameWithType> как аргумент, сборка мусора в куче больших объектов происходит одновременно со сборкой мусора в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-180">If the parameterless <xref:System.GC.Collect?displayProperty=nameWithType> method is called or another overload is passed <xref:System.GC.MaxGeneration?displayProperty=nameWithType> as an argument, the LOH is collected along with the rest of the managed heap.</span></span>

- <span data-ttu-id="ba2f9-181">В системе недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-181">The system is in low memory situation.</span></span>

  <span data-ttu-id="ba2f9-182">Это происходит, когда сборщик мусора получает от ОС уведомление верхней памяти.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-182">This occurs when the garbage collector receives a high memory notification from the OS.</span></span> <span data-ttu-id="ba2f9-183">Если сборщик мусора считает, что сборка мусора поколения 2 будет продуктивной, он запускает ее.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-183">If the garbage collector thinks that doing a generation 2 GC will be productive, it triggers one.</span></span>

## <a name="loh-performance-implications"></a><span data-ttu-id="ba2f9-184">Влияние кучи больших объектов на производительность</span><span class="sxs-lookup"><span data-stu-id="ba2f9-184">LOH Performance Implications</span></span>

<span data-ttu-id="ba2f9-185">Распределение в куче больших объектов влияет на производительность следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-185">Allocations on the large object heap impact performance in the following ways.</span></span>

- <span data-ttu-id="ba2f9-186">Затраты на распределение.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-186">Allocation cost.</span></span>

  <span data-ttu-id="ba2f9-187">CLR гарантирует очистку памяти для каждого выдаваемого им нового объекта.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-187">The CLR makes the guarantee that the memory for every new object it gives out is cleared.</span></span> <span data-ttu-id="ba2f9-188">Это значит, что при распределении большого объекта ресурсы, в основном, расходуются на очистку памяти (если не запускается сборка мусора).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-188">This means the allocation cost of a large object is completely dominated by memory clearing (unless it triggers a GC).</span></span> <span data-ttu-id="ba2f9-189">Если очистка одного байта занимает два цикла, то на очистку самого маленького большого объекта уйдет 170 000 циклов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-189">If it takes 2 cycles to clear one byte, it takes 170,000 cycles to clear the smallest large object.</span></span> <span data-ttu-id="ba2f9-190">Очистка памяти для объекта размером 16 МБ на компьютере с частотой 2 ГГц занимает приблизительно 16 мс.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-190">Clearing the memory of a 16MB object on a 2GHz machine takes approximately 16ms.</span></span> <span data-ttu-id="ba2f9-191">Это довольно большие затраты.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-191">That's a rather large cost.</span></span>

- <span data-ttu-id="ba2f9-192">Затраты на сбор.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-192">Collection cost.</span></span>

  <span data-ttu-id="ba2f9-193">Поскольку куча больших объектов и поколение 2 собираются вместе, при превышении порогового значения для любого из них запускается сборка мусора поколения 2.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-193">Because the LOH and generation 2 are collected together, if either one's threshold is exceeded, a generation 2 collection is triggered.</span></span> <span data-ttu-id="ba2f9-194">Если сборка поколения 2 была запущена из-за кучи больших объектов, то само поколение 2 необязательно значительно уменьшится после сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-194">If a generation 2 collection is triggered because of the LOH, generation 2 won't necessarily be much smaller after the GC.</span></span> <span data-ttu-id="ba2f9-195">Если в поколении 2 не так много данных, влияние минимально.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-195">If there's not much data on generation 2, this has minimal impact.</span></span> <span data-ttu-id="ba2f9-196">Но если поколение 2 большое, запуск многочисленных сборок мусора поколения 2 может вызвать проблемы с производительностью.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-196">But if generation 2 is large, it can cause performance problems if many generation 2 GCs are triggered.</span></span> <span data-ttu-id="ba2f9-197">Если у вас много больших объектов с временным размещением и большая куча маленьких объектов, на сборку мусора может уходить слишком много времени.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-197">If many large objects are allocated on a very temporary basis and you have a large SOH, you could be spending too much time doing GCs.</span></span> <span data-ttu-id="ba2f9-198">Кроме того, затраты на распределение могут нарастать, если вы и дальше будете распределять и освобождать очень большие объекты.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-198">In addition, the allocation cost can really add up if you keep allocating and letting go of really large objects.</span></span>

- <span data-ttu-id="ba2f9-199">Элементы массива со ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-199">Array elements with reference types.</span></span>

  <span data-ttu-id="ba2f9-200">Очень большие объекты в куче обычно являются массивами (очень большие объекты-экземпляры весьма редки).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-200">Very large objects on the LOH are usually arrays (it's very rare to have an instance object that's really large).</span></span> <span data-ttu-id="ba2f9-201">Если элементы массива имеют много ссылок, затраты выше, чем для элементов с небольшим количеством ссылок.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-201">If the elements of an array are reference-rich, it incurs a cost that is not present if the elements are not reference-rich.</span></span> <span data-ttu-id="ba2f9-202">Если элемент не содержит ссылок, сборщику мусора совсем не придется перебирать массив.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-202">If the element doesn’t contain any references, the garbage collector doesn’t need to go through the array at all.</span></span> <span data-ttu-id="ba2f9-203">Например, в случае использования массива для хранения узлов в двоичном дереве одной из возможных реализаций является обозначение узлов справа и слева от узла реальными узлами:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-203">For example, if you use an array to store nodes in a binary tree, one way to implement it is to refer to a node’s right and left node by the actual nodes:</span></span>

  ```csharp
  class Node
  {
     Data d;
     Node left;
     Node right;
  };

  Node[] binary_tr = new Node [num_nodes];
  ```

  <span data-ttu-id="ba2f9-204">Если `num_nodes` является большим, сборщик мусора должен обработать как минимум две ссылки на элемент.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-204">If `num_nodes` is large, the garbage collector needs to go through at least two references per element.</span></span> <span data-ttu-id="ba2f9-205">Другой подход состоит в сохранении индекса правого и левого узла:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-205">An alternative approach is to store the index of the right and the left nodes:</span></span>

  ```csharp
  class Node
  {
     Data d;
     uint left_index;
     uint right_index;
  } ;
  ```

  <span data-ttu-id="ba2f9-206">Ссылка на данные левого узла может выглядеть не как `left.d`, а как `binary_tr[left_index].d`.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-206">Instead of referring the left node’s data as `left.d`, you refer to it as `binary_tr[left_index].d`.</span></span> <span data-ttu-id="ba2f9-207">А сборщику мусора не понадобится просматривать ссылки для левого и правого узлов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-207">And the garbage collector doesn’t need to look at any references for the left and right node.</span></span>

<span data-ttu-id="ba2f9-208">Из трех факторов первые два обычно важнее, чем третий.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-208">Out of the three factors, the first two are usually more significant than the third.</span></span> <span data-ttu-id="ba2f9-209">По этой причине рекомендуется распределять пул больших объектов, которые можно использовать повторно, вместо распределения временных.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-209">Because of this, we recommend that you allocate a pool of large objects that you reuse instead of allocating temporary ones.</span></span>

## <a name="collecting-performance-data-for-the-loh"></a><span data-ttu-id="ba2f9-210">Сбор данных производительности для кучи больших объектов</span><span class="sxs-lookup"><span data-stu-id="ba2f9-210">Collecting performance data for the LOH</span></span>

<span data-ttu-id="ba2f9-211">Прежде чем собирать данные производительности для определенной области, вы должны выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-211">Before you collect performance data for a specific area, you should already have done the following:</span></span>

1. <span data-ttu-id="ba2f9-212">Найти свидетельство, которое нужно учитывать в этой области.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-212">Found evidence that you should be looking at this area.</span></span>

2. <span data-ttu-id="ba2f9-213">Исследовать другие известные области и не найти в них причину проблемы с производительностью.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-213">Exhausted other areas that you know of without finding anything that could explain the performance problem you saw.</span></span>

<span data-ttu-id="ba2f9-214">Дополнительные сведения об основах памяти и ЦП см. в блоге [Понять проблемы, прежде чем пытаться найти решение](https://devblogs.microsoft.com/dotnet/understand-the-problem-before-you-try-to-find-a-solution/).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-214">See the blog [Understand the problem before you try to find a solution](https://devblogs.microsoft.com/dotnet/understand-the-problem-before-you-try-to-find-a-solution/) for more information on the fundamentals of memory and the CPU.</span></span>

<span data-ttu-id="ba2f9-215">Для сбора данных о производительности кучи больших объектов можно использовать следующие средства:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-215">You can use the following tools to collect data on LOH performance:</span></span>

- [<span data-ttu-id="ba2f9-216">Счетчики памяти .NET CLR</span><span class="sxs-lookup"><span data-stu-id="ba2f9-216">.NET CLR memory performance counters</span></span>](#net-clr-memory-performance-counters)

- [<span data-ttu-id="ba2f9-217">События трассировки событий Windows</span><span class="sxs-lookup"><span data-stu-id="ba2f9-217">ETW events</span></span>](#etw-events)

- [<span data-ttu-id="ba2f9-218">Отладчик</span><span class="sxs-lookup"><span data-stu-id="ba2f9-218">A debugger</span></span>](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a><span data-ttu-id="ba2f9-219">Счетчики памяти .NET CLR</span><span class="sxs-lookup"><span data-stu-id="ba2f9-219">.NET CLR Memory Performance counters</span></span>

<span data-ttu-id="ba2f9-220">Использование счетчиков памяти обычно является хорошим первым этапом поиска проблем с производительностью (хотя мы рекомендуем использовать [События трассировки Windows](#etw-events)).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-220">These performance counters are usually a good first step in investigating performance issues (although we recommend that you use [ETW events](#etw-events)).</span></span> <span data-ttu-id="ba2f9-221">Чтобы настроить монитор производительности, добавьте нужные счетчики, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-221">You configure Performance Monitor by adding the counters that you want, as Figure 4 shows.</span></span> <span data-ttu-id="ba2f9-222">К куче больших объектов относятся следующие счетчики:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-222">The ones that are relevant for the LOH are:</span></span>

- <span data-ttu-id="ba2f9-223">**Число сборок мусора поколения 2**</span><span class="sxs-lookup"><span data-stu-id="ba2f9-223">**Gen 2 Collections**</span></span>

   <span data-ttu-id="ba2f9-224">Показывает количество сборок мусора поколения 2 с момента запуска процесса.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-224">Displays the number of times generation 2 GCs have occurred since the process started.</span></span> <span data-ttu-id="ba2f9-225">Этот счетчик увеличивает число в конце сборки мусора поколения 2 (иначе называемой полной сборкой мусора).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-225">The counter is incremented at the end of a generation 2 collection (also called a full garbage collection).</span></span> <span data-ttu-id="ba2f9-226">Этот счетчик отображает последнее значение.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-226">This counter displays the last observed value.</span></span>

- <span data-ttu-id="ba2f9-227">**Размер кучи для массивных объектов**</span><span class="sxs-lookup"><span data-stu-id="ba2f9-227">**Large Object Heap size**</span></span>

   <span data-ttu-id="ba2f9-228">Отображает текущий размер кучи больших объектов в байтах, включая свободное пространство.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-228">Displays the current size, in bytes, including free space, of the LOH.</span></span> <span data-ttu-id="ba2f9-229">Этот счетчик обновляется в конце сборки мусора, не при каждом выделении памяти.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-229">This counter is updated at the end of a garbage collection, not at each allocation.</span></span>

<span data-ttu-id="ba2f9-230">Распространенным средством просмотра счетчиков производительности является монитор производительности (perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-230">A common way to look at performance counters is with Performance Monitor (perfmon.exe).</span></span> <span data-ttu-id="ba2f9-231">Нажмите "Добавить счетчики", чтобы добавить нужный счетчик для интересующих вас процессов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-231">Use “Add Counters” to add the interesting counter for processes that you care about.</span></span> <span data-ttu-id="ba2f9-232">Данные счетчика производительности можно сохранить в файле журнала, как показано на рисунке 4.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-232">You can save the performance counter data to a log file, as Figure 4 shows:</span></span>

<span data-ttu-id="ba2f9-233">![Снимок экрана, демонстрирующий добавление счетчиков производительности.](media/large-object-heap/add-performance-counter.png)</span><span class="sxs-lookup"><span data-stu-id="ba2f9-233">![Screenshot that shows adding performance counters.](media/large-object-heap/add-performance-counter.png)</span></span>
<span data-ttu-id="ba2f9-234">Рис. 4. Куча больших объектов после сборки мусора поколения 2</span><span class="sxs-lookup"><span data-stu-id="ba2f9-234">Figure 4: The LOH after a generation 2 GC</span></span>

<span data-ttu-id="ba2f9-235">Счетчики производительности также можно запросить программно.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-235">Performance counters can also be queried programmatically.</span></span> <span data-ttu-id="ba2f9-236">Многие собирают эти данные таким способом в рамках рутинного процесса тестирования.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-236">Many people collect them this way as part of their routine testing process.</span></span> <span data-ttu-id="ba2f9-237">При обнаружении счетчиков с необычными значениями можно использовать другие способы получения подробностей, чтобы помочь расследованию.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-237">When they spot counters with values that are out of the ordinary, they use other means to get more detailed data to help with the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="ba2f9-238">Рекомендуется использовать события трассировки событий Windows вместо счетчиков производительности, так как трассировка событий Windows предоставляет гораздо больше сведений.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-238">We recommend that you to use ETW events instead of performance counters, because ETW provides much richer information.</span></span>

### <a name="etw-events"></a><span data-ttu-id="ba2f9-239">ETW-события</span><span class="sxs-lookup"><span data-stu-id="ba2f9-239">ETW events</span></span>

<span data-ttu-id="ba2f9-240">Сборщик мусора предоставляет широкий набор событий трассировки событий Windows, помогая разобраться в функциях кучи.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-240">The garbage collector provides a rich set of ETW events to help you understand what the heap is doing and why.</span></span> <span data-ttu-id="ba2f9-241">В следующих записях блога описывается, как собирать и интерпретировать события сборки мусора с помощью трассировки событий Windows:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-241">The following blog posts show how to collect and understand GC events with ETW:</span></span>

- [<span data-ttu-id="ba2f9-242">События сборки мусора в трассировке событий Windows — 1</span><span class="sxs-lookup"><span data-stu-id="ba2f9-242">GC ETW Events - 1</span></span>](https://devblogs.microsoft.com/dotnet/gc-etw-events-1/)

- [<span data-ttu-id="ba2f9-243">События сборки мусора в трассировке событий Windows — 2</span><span class="sxs-lookup"><span data-stu-id="ba2f9-243">GC ETW Events - 2</span></span>](https://devblogs.microsoft.com/dotnet/gc-etw-events-2/)

- [<span data-ttu-id="ba2f9-244">События сборки мусора в трассировке событий Windows — 3</span><span class="sxs-lookup"><span data-stu-id="ba2f9-244">GC ETW Events - 3</span></span>](https://devblogs.microsoft.com/dotnet/gc-etw-events-3/)

- [<span data-ttu-id="ba2f9-245">События сборки мусора в трассировке событий Windows — 4</span><span class="sxs-lookup"><span data-stu-id="ba2f9-245">GC ETW Events - 4</span></span>](https://devblogs.microsoft.com/dotnet/gc-etw-events-4/)

<span data-ttu-id="ba2f9-246">Чтобы выявить чрезмерную сборку мусора поколения 2, вызванную временными распределениями кучи больших объектов, ищите сборку мусора в столбце "Причина активации".</span><span class="sxs-lookup"><span data-stu-id="ba2f9-246">To identify excessive generation 2 GCs caused by temporary LOH allocations, look at the Trigger Reason column for GCs.</span></span> <span data-ttu-id="ba2f9-247">Чтобы провести простой тест и распределить только временные большие объекты, соберите информацию о событиях трассировки событий Windows с помощью следующей командной строки [PerfView](https://www.microsoft.com/download/details.aspx?id=28567):</span><span class="sxs-lookup"><span data-stu-id="ba2f9-247">For a simple test that only allocates temporary large objects, you can collect information on ETW events with the following [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) command line:</span></span>

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="ba2f9-248">Результат будет выглядеть примерно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-248">The result is something like this:</span></span>

<span data-ttu-id="ba2f9-249">![Снимок экрана, показывающий события трассировки событий Windows в PerfView](media/large-object-heap/event-tracing-windows-perfview.png).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-249">![Screenshot that shows ETW events in PerfView.](media/large-object-heap/event-tracing-windows-perfview.png)</span></span>
<span data-ttu-id="ba2f9-250">Рис. 5. События трассировки событий Windows, отображаемые с помощью PerfView</span><span class="sxs-lookup"><span data-stu-id="ba2f9-250">Figure 5: ETW events shown using PerfView</span></span>

<span data-ttu-id="ba2f9-251">Как видите, все сборки мусора относятся к поколению 2 и активируются функцией AllocLarge. Это означает, что эта сборка мусора вызвана распределением большого объекта.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-251">As you can see, all GCs are generation 2 GCs, and they are all triggered by AllocLarge, which means that allocating a large object triggered this GC.</span></span> <span data-ttu-id="ba2f9-252">Мы знаем, что эти распределения являются временными, так как в столбце **% выживания LOH** значится 1 %.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-252">We know that these allocations are temporary because the **LOH Survival Rate %** column says 1%.</span></span>

<span data-ttu-id="ba2f9-253">Можно собирать дополнительные события трассировки событий Windows, которые показывают, кто распределил эти большие объекты.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-253">You can collect additional ETW events that tell you who allocated these large objects.</span></span> <span data-ttu-id="ba2f9-254">Следующая командная строка:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-254">The following command line:</span></span>

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="ba2f9-255">собирает событие AllocationTick, которое возникает примерно каждые 100 000 распределений.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-255">collects an AllocationTick event which is fired approximately every 100k worth of allocations.</span></span> <span data-ttu-id="ba2f9-256">Другими словами, событие возникает при каждом выделении памяти для большого объекта.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-256">In other words, an event is fired each time a large object is allocated.</span></span> <span data-ttu-id="ba2f9-257">Затем вы можете изучить одно из представлений GC Heap Alloc, где отображаются стеки вызовов, распределившие большие объекты:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-257">You can then look at one of the GC Heap Alloc views which show you the callstacks that allocated large objects:</span></span>

<span data-ttu-id="ba2f9-258">![Снимок экрана, показывающий представление кучи сборщика мусора](media/large-object-heap/garbage-collector-heap.png).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-258">![Screenshot that shows a garbage collector heap view.](media/large-object-heap/garbage-collector-heap.png)</span></span>
<span data-ttu-id="ba2f9-259">Рис. 6. Представление GC Heap Alloc</span><span class="sxs-lookup"><span data-stu-id="ba2f9-259">Figure 6: A GC Heap Alloc view</span></span>

<span data-ttu-id="ba2f9-260">Как видите, это очень простой тест, который выделяет память для большого объекта из метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-260">As you can see, this is a very simple test that just allocates large objects from its `Main` method.</span></span>

### <a name="a-debugger"></a><span data-ttu-id="ba2f9-261">Отладчик</span><span class="sxs-lookup"><span data-stu-id="ba2f9-261">A debugger</span></span>

<span data-ttu-id="ba2f9-262">Если у вас есть только дамп памяти и вам нужно увидеть, какие объекты находятся в куче, можно использовать [расширение отладчика SoS](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md), предоставляемое .NET.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-262">If all you have is a memory dump and you need to look at what objects are actually on the LOH, you can use the [SoS debugger extension](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md) provided by .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="ba2f9-263">Команды отладки, описанные в этом разделе, применимы к [отладчикам Windows](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-263">The debugging commands mentioned in this section are applicable to the [Windows Debuggers](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).</span></span>

<span data-ttu-id="ba2f9-264">Ниже приведен пример выходных данных анализа кучи больших объектов:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-264">The following shows sample output from analyzing the LOH:</span></span>

```console
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

<span data-ttu-id="ba2f9-265">Размер кучи больших объектов равен (16 754 224 + 16 699 288 + 16 284 504) = 49 738 016 байт.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-265">The LOH heap size is (16,754,224 + 16,699,288 + 16,284,504) = 49,738,016 bytes.</span></span> <span data-ttu-id="ba2f9-266">Между адресами 023e1000 и 033db630 8 008 736 байт занимает массив объектов <xref:System.Object?displayProperty=nameWithType>, 6 663 696 байт занимает массив объектов <xref:System.Byte?displayProperty=nameWithType> и 2 081 792 байт свободно.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-266">Between addresses 023e1000 and 033db630, 8,008,736 bytes are occupied by an array of <xref:System.Object?displayProperty=nameWithType> objects, 6,663,696 bytes are occupied by an array of <xref:System.Byte?displayProperty=nameWithType>  objects, and 2,081,792 bytes are occupied by free space.</span></span>

<span data-ttu-id="ba2f9-267">Иногда в отладчике общий размер кучи больших объектов менее 85 000 байт.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-267">Sometimes, the debugger shows that the total size of the LOH is less than 85,000 bytes.</span></span> <span data-ttu-id="ba2f9-268">Дело в том, что сама среда выполнения использует кучу больших объектов для размещения некоторых объектов, которые меньше большого объекта.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-268">This happens because the runtime itself uses the LOH to allocate some objects that are smaller than a large object.</span></span>

<span data-ttu-id="ba2f9-269">Поскольку куча больших объектов не сжимается, иногда она считается источником фрагментации.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-269">Because the LOH is not compacted, sometimes the LOH is thought to be the source of fragmentation.</span></span> <span data-ttu-id="ba2f9-270">Фрагментация означает:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-270">Fragmentation means:</span></span>

- <span data-ttu-id="ba2f9-271">Фрагментация управляемой кучи, на которую указывает объем свободного пространства между управляемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-271">Fragmentation of the managed heap, which is indicated by the amount of free space between managed objects.</span></span> <span data-ttu-id="ba2f9-272">В SoS команда `!dumpheap –type Free` отображает объем свободного пространства между управляемыми объектами.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-272">In SoS, the `!dumpheap –type Free` command displays the amount of free space between managed objects.</span></span>

- <span data-ttu-id="ba2f9-273">Фрагментация диапазона адресов виртуальной памяти. Это память, помеченная как `MEM_FREE`.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-273">Fragmentation of the virtual memory (VM) address space, which is the memory marked as `MEM_FREE`.</span></span> <span data-ttu-id="ba2f9-274">Ее можно получить, используя различные команды отладки в windbg.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-274">You can get it by using various debugger commands in windbg.</span></span>

   <span data-ttu-id="ba2f9-275">Ниже приведен пример фрагментации в пространстве виртуальной памяти:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-275">The following example shows fragmentation in the VM space:</span></span>

   ```console
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

<span data-ttu-id="ba2f9-276">Фрагментация виртуальной памяти чаще вызывается временными большими объектами, которые требуют частых сборок мусора для получения новых сегментов управляемой кучи от ОС и возвращения ОС пустых сегментов.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-276">It’s more common to see VM fragmentation caused by temporary large objects that require the garbage collector to frequently acquire new managed heap segments from the OS and to release empty ones back to the OS.</span></span>

<span data-ttu-id="ba2f9-277">Чтобы проверить, вызывается ли фрагментация виртуальной памяти кучей больших объектов, можно установить точку останова на функциях [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) и [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree), чтобы увидеть, кто ее вызывает.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-277">To verify whether the LOH is causing VM fragmentation, you can set a breakpoint on [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) and [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree) to see who call them.</span></span> <span data-ttu-id="ba2f9-278">Например, чтобы узнать, кто пытался выделить блоки виртуальной памяти ОС размером более 8 МБ, можно установить точку останова следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ba2f9-278">For example, to see who tried to allocate virtual memory chunks larger than 8MBB from the OS, you can set a breakpoint like this:</span></span>

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

<span data-ttu-id="ba2f9-279">Эта команда останавливает отладчик и показывает стек вызовов только в том случае, если [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) вызывается с объемом выделенной памяти более 8 МБ (0x800000).</span><span class="sxs-lookup"><span data-stu-id="ba2f9-279">This command breaks into the debugger and shows the call stack only if [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) is called with an allocation size greater than 8MB (0x800000).</span></span>

<span data-ttu-id="ba2f9-280">В CLR 2.0 добавлена функция *накопления виртуальной памяти*, которую можно использовать в случае, когда сегменты (включая кучи больших и маленьких объектов) часто фиксируются и освобождаются.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-280">CLR 2.0 added a feature called *VM Hoarding* that can be useful for scenarios where segments (including on the large and small object heaps) are frequently acquired and released.</span></span> <span data-ttu-id="ba2f9-281">Для настройки накопления виртуальной памяти установите флаг запуска `STARTUP_HOARD_GC_VM` через API размещения.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-281">To specify VM Hoarding, you specify a startup flag called `STARTUP_HOARD_GC_VM` via the hosting API.</span></span> <span data-ttu-id="ba2f9-282">Вместо возвращения пустых сегментов операционной системе CRL освобождает память в этих сегментах и помещает их в список ожидания.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-282">Instead of releasing empty segments back to the OS, the CLR decommits the memory on these segments and puts them on a standby list.</span></span> <span data-ttu-id="ba2f9-283">(Обратите внимание, что среда CLR не выполняет эти действия со слишком большими сегментами.) Позже среда CLR использует эти сегменты для удовлетворения запросов на новый сегмент.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-283">(Note that the CLR doesn't do this for segments that are too large.) The CLR later uses those segments to satisfy new segment requests.</span></span> <span data-ttu-id="ba2f9-284">В следующий раз, когда приложению потребуется новый сегмент, среда CLR возьмет его из списка ожидания, если найдет сегмент подходящего размера.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-284">The next time that your app needs a new segment, the CLR uses one from this standby list if it can find one that’s big enough.</span></span>

<span data-ttu-id="ba2f9-285">Накопление виртуальной памяти удобно использовать для приложений, в которых необходимо закрепить уже полученные сегменты, например некоторых серверных приложений, имеющих приоритет в системе, чтобы избежать исключений нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-285">VM hoarding is also useful for applications that want to hold onto the segments that they already acquired, such as some server apps that are the dominant apps running on the system, to avoid out of memory exceptions.</span></span>

<span data-ttu-id="ba2f9-286">Мы настоятельно рекомендуем тщательно тестировать приложение при использовании этой функции и убедиться, что использование памяти достаточно стабильно.</span><span class="sxs-lookup"><span data-stu-id="ba2f9-286">We strongly recommend that you carefully test your application when you use this feature to ensure your application has fairly stable memory usage.</span></span>
