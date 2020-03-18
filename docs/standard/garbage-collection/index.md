---
title: Сборка мусора
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: 846df5ecb1e681e8d0440e627586a681bf071efa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160148"
---
# <a name="garbage-collection"></a><span data-ttu-id="0c077-102">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="0c077-102">Garbage Collection</span></span>
<span data-ttu-id="0c077-103">Сборщик мусора .NET управляет выделением и освобождением памяти для приложения.</span><span class="sxs-lookup"><span data-stu-id="0c077-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="0c077-104">При каждом создании объекта среда CLR выделяет память для объекта из управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="0c077-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="0c077-105">Пока в управляемой куче есть доступное адресное пространство, среда выполнения продолжает выделять пространство для новых объектов.</span><span class="sxs-lookup"><span data-stu-id="0c077-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="0c077-106">Тем не менее ресурсы памяти не безграничны.</span><span class="sxs-lookup"><span data-stu-id="0c077-106">However, memory is not infinite.</span></span> <span data-ttu-id="0c077-107">В конечном счете сборщику мусора необходимо выполнить сбор, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="0c077-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="0c077-108">Механизм оптимизации сборщика мусора определяет наилучшее время для выполнения сбора, основываясь на выполненных операциях выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="0c077-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="0c077-109">Когда сборщик мусора выполняет сборку, он проверяет наличие объектов в управляемой куче, которые больше не используются приложением, а затем выполняет необходимые операции, чтобы освободить память.</span><span class="sxs-lookup"><span data-stu-id="0c077-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="0c077-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c077-110">Related Topics</span></span>  
  
|<span data-ttu-id="0c077-111">Название</span><span class="sxs-lookup"><span data-stu-id="0c077-111">Title</span></span>|<span data-ttu-id="0c077-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="0c077-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0c077-113">Основы сборки мусора</span><span class="sxs-lookup"><span data-stu-id="0c077-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="0c077-114">Описание работы сборки мусора, выделения объектов в управляемой куче и других базовых понятий.</span><span class="sxs-lookup"><span data-stu-id="0c077-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="0c077-115">Сборка мусора и производительность</span><span class="sxs-lookup"><span data-stu-id="0c077-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="0c077-116">Проверки производительности, которые можно использовать для диагностики проблем со сборкой мусора и производительностью.</span><span class="sxs-lookup"><span data-stu-id="0c077-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="0c077-117">Индуцированные коллекции</span><span class="sxs-lookup"><span data-stu-id="0c077-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="0c077-118">Описание выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0c077-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="0c077-119">Режимы задержки</span><span class="sxs-lookup"><span data-stu-id="0c077-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="0c077-120">Описание режимов, которые определяют степень вмешательства сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="0c077-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="0c077-121">Оптимизация совместного размещения веб-сайтов</span><span class="sxs-lookup"><span data-stu-id="0c077-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="0c077-122">Способы оптимизации сборки мусора на серверах, совместно используемыми небольшими веб-узлами.</span><span class="sxs-lookup"><span data-stu-id="0c077-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="0c077-123">Уведомления о сборке мусора</span><span class="sxs-lookup"><span data-stu-id="0c077-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="0c077-124">Определение необходимости полной сборки мусора и времени завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="0c077-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="0c077-125">Отслеживание ресурсов домена приложения</span><span class="sxs-lookup"><span data-stu-id="0c077-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="0c077-126">Способы наблюдения за использованием ЦП и памяти доменом приложения.</span><span class="sxs-lookup"><span data-stu-id="0c077-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="0c077-127">Слабые ссылки</span><span class="sxs-lookup"><span data-stu-id="0c077-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="0c077-128">Описание функциональных возможностей, которые позволяют сборщику мусора обрабатывать объект, разрешая при этом приложению получать доступ к этому объекту.</span><span class="sxs-lookup"><span data-stu-id="0c077-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="0c077-129">Справочник</span><span class="sxs-lookup"><span data-stu-id="0c077-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="0c077-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0c077-130">See also</span></span>

- [<span data-ttu-id="0c077-131">Очистка неуправляемых ресурсов</span><span class="sxs-lookup"><span data-stu-id="0c077-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
