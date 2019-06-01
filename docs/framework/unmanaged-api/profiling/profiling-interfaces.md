---
title: Профилирующие интерфейсы
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97960a43e1d7ce625d96755a7c597a0425d0911
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457458"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="235b6-102">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="235b6-102">Profiling Interfaces</span></span>
<span data-ttu-id="235b6-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие профилировать программу, выполняемую в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="235b6-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="235b6-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="235b6-104">In This Section</span></span>  
 [<span data-ttu-id="235b6-105">Интерфейс ICLRProfiling</span><span class="sxs-lookup"><span data-stu-id="235b6-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="235b6-106">Предоставляет [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) метод, который позволяет присоединить профилировщик к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="235b6-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="235b6-107">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="235b6-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="235b6-108">Позволяет профилировщику сообщать среде CLR о ссылках на сборку, которые профилировщик добавит в [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="235b6-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="235b6-109">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="235b6-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="235b6-110">Предоставляет методы, используемые средой CLR для уведомления профилировщика кода при событиях, на которые подписан профилировщик.</span><span class="sxs-lookup"><span data-stu-id="235b6-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="235b6-111">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="235b6-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="235b6-112">Расширяет интерфейс `ICorProfilerCallback` обратными вызовами, поддерживаемыми платформой .NET Framework 2.0 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="235b6-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="235b6-113">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="235b6-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="235b6-114">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о подключенном и отключенном состоянии профилировщику.</span><span class="sxs-lookup"><span data-stu-id="235b6-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="235b6-115">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="235b6-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="235b6-116">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений профилировщику.</span><span class="sxs-lookup"><span data-stu-id="235b6-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="235b6-117">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="235b6-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="235b6-118">Предоставляет метод, идентифицирующий транзитивное замыкание объектов, на которые ссылаются корни сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="235b6-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="235b6-119">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="235b6-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="235b6-120">Предоставляет метод обратного вызова, который используется средой CLR для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="235b6-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="235b6-121">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="235b6-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="235b6-122">Предоставляет метод обратного вызова, который среда CLR использует для уведомления профилировщика о том, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="235b6-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="235b6-123">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="235b6-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="235b6-124">Предоставляет методы обратного вызова, среда CLR использует для уведомления профилировщика о началась и завершения JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="235b6-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="235b6-125">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="235b6-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="235b6-126">Предоставляет метод обратного вызова, который среда CLR использует для уведомления профилировщика о динамический метод является мусором собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="235b6-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="235b6-127">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="235b6-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="235b6-128">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="235b6-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="235b6-129">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="235b6-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="235b6-130">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="235b6-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="235b6-131">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="235b6-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="235b6-132">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="235b6-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="235b6-133">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="235b6-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="235b6-134">Расширяет интерфейс `ICorProfilerInfo` методами, поддерживаемыми платформой .NET Framework 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="235b6-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="235b6-135">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="235b6-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="235b6-136">Расширяет `ICorProfilerInfo2` интерфейса с помощью методов, поддерживаемых в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="235b6-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="235b6-137">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="235b6-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="235b6-138">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="235b6-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="235b6-139">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="235b6-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="235b6-140">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий.</span><span class="sxs-lookup"><span data-stu-id="235b6-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="235b6-141">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="235b6-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="235b6-142">Предоставляет перечислитель для всех методов, которые принадлежат данного модуля NGen и, встраиваются в тексте данного метода.</span><span class="sxs-lookup"><span data-stu-id="235b6-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="235b6-143">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="235b6-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="235b6-144">Предоставляет метод для применения вновь определен метаданных для модуля и, обеспечивающий доступ в поток символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="235b6-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="235b6-145">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="235b6-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="235b6-146">Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="235b6-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="235b6-147">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="235b6-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="235b6-148">Предоставляет методы для последовательного перебора коллекции зафиксированных объектов, создаваемых [Ngen.exe (генератор образов в машинном)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="235b6-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="235b6-149">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="235b6-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="235b6-150">Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="235b6-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="235b6-151">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="235b6-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="235b6-152">Предоставляет [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) метод выделить память для нового тела функции промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="235b6-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="235b6-153">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="235b6-153">Related Sections</span></span>  
 [<span data-ttu-id="235b6-154">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="235b6-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="235b6-155">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="235b6-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="235b6-156">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="235b6-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="235b6-157">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="235b6-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
