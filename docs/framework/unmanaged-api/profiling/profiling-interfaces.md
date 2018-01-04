---
title: "Профилирующие интерфейсы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f8c2a5ce5e1231c55f598e48d14bec896a4b5f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-interfaces"></a><span data-ttu-id="65222-102">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="65222-102">Profiling Interfaces</span></span>
<span data-ttu-id="65222-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие профилировать программу, выполняемую в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="65222-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65222-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="65222-104">In This Section</span></span>  
 [<span data-ttu-id="65222-105">Интерфейс ICLRProfiling</span><span class="sxs-lookup"><span data-stu-id="65222-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="65222-106">Предоставляет [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) метод, который позволяет профилировщику для присоединения к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="65222-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="65222-107">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="65222-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="65222-108">Позволяет профилировщику информировать среду CLR ссылки на сборки, которые профилировщик добавит в [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="65222-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="65222-109">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="65222-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="65222-110">Предоставляет методы, используемые средой CLR для уведомления профилировщика кода при событиях, на которые подписан профилировщик.</span><span class="sxs-lookup"><span data-stu-id="65222-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="65222-111">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="65222-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="65222-112">Расширяет интерфейс `ICorProfilerCallback` обратными вызовами, поддерживаемыми платформой .NET Framework 2.0 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="65222-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="65222-113">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="65222-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="65222-114">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о подключенном и отключенном состоянии профилировщику.</span><span class="sxs-lookup"><span data-stu-id="65222-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="65222-115">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="65222-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="65222-116">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений профилировщику.</span><span class="sxs-lookup"><span data-stu-id="65222-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="65222-117">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="65222-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="65222-118">Предоставляет метод, идентифицирующий транзитивное замыкание объектов, на которые ссылаются корни сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="65222-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="65222-119">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="65222-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="65222-120">Предоставляет метод обратного вызова, который используется средой CLR для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="65222-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="65222-121">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="65222-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="65222-122">Предоставляет метод обратного вызова, который общеязыковая среда выполнения использует для уведомления профилировщика о том, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="65222-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
 [<span data-ttu-id="65222-123">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="65222-123">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="65222-124">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="65222-124">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="65222-125">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="65222-125">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="65222-126">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="65222-126">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="65222-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="65222-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="65222-128">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="65222-128">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="65222-129">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="65222-129">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="65222-130">Расширяет интерфейс `ICorProfilerInfo` методами, поддерживаемыми платформой .NET Framework 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="65222-130">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="65222-131">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="65222-131">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="65222-132">Расширяет интерфейс `ICorProfilerInfo2` методами, поддерживаемыми платформой [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="65222-132">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="65222-133">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="65222-133">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="65222-134">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="65222-134">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="65222-135">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="65222-135">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="65222-136">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий.</span><span class="sxs-lookup"><span data-stu-id="65222-136">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="65222-137">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="65222-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="65222-138">Предоставляет перечислитель для всех методов, принадлежащих данного модуля NGen, и, встраиваются в основной части данного метода.</span><span class="sxs-lookup"><span data-stu-id="65222-138">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="65222-139">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="65222-139">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="65222-140">Предоставляет метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ к поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="65222-140">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="65222-141">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="65222-141">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="65222-142">Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="65222-142">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="65222-143">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="65222-143">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="65222-144">Предоставляет методы для последовательного перебора коллекции замороженный объектов, создаваемых [Ngen.exe (генератор образов в машинном)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="65222-144">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="65222-145">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="65222-145">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="65222-146">Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="65222-146">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="65222-147">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="65222-147">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="65222-148">Предоставляет [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) метод выделения памяти для нового тела функции промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="65222-148">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="65222-149">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="65222-149">Related Sections</span></span>  
 [<span data-ttu-id="65222-150">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="65222-150">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="65222-151">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="65222-151">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="65222-152">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="65222-152">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="65222-153">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="65222-153">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
