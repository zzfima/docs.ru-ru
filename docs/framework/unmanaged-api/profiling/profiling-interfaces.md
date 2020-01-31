---
title: Интерфейсы профилирования
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868152"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="8b254-102">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="8b254-102">Profiling Interfaces</span></span>
<span data-ttu-id="8b254-103">В этом разделе описываются неуправляемые интерфейсы, позволяющие профилировать программу, выполняемую в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8b254-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b254-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8b254-104">In This Section</span></span>  
 [<span data-ttu-id="8b254-105">Интерфейс ICLRProfiling</span><span class="sxs-lookup"><span data-stu-id="8b254-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="8b254-106">Предоставляет метод [AttachProfiler](iclrprofiling-attachprofiler-method.md) , который позволяет профилировщику присоединяться к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="8b254-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="8b254-107">Интерфейс ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="8b254-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="8b254-108">Позволяет профилировщику сообщать о CLR ссылок на сборки, которые профилировщик будет добавлять в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8b254-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="8b254-109">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8b254-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="8b254-110">Предоставляет методы, используемые средой CLR для уведомления профилировщика кода при событиях, на которые подписан профилировщик.</span><span class="sxs-lookup"><span data-stu-id="8b254-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="8b254-111">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="8b254-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="8b254-112">Расширяет интерфейс `ICorProfilerCallback` обратными вызовами, поддерживаемыми платформой .NET Framework 2.0 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8b254-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="8b254-113">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="8b254-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="8b254-114">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о подключенном и отключенном состоянии профилировщику.</span><span class="sxs-lookup"><span data-stu-id="8b254-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="8b254-115">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="8b254-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="8b254-116">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений профилировщику.</span><span class="sxs-lookup"><span data-stu-id="8b254-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="8b254-117">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="8b254-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="8b254-118">Предоставляет метод, идентифицирующий транзитивное замыкание объектов, на которые ссылаются корни сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8b254-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="8b254-119">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="8b254-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="8b254-120">Предоставляет метод обратного вызова, который используется средой CLR для уведомления профилировщика о загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="8b254-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="8b254-121">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="8b254-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="8b254-122">Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что поток символов, связанный с модулем в памяти, обновлен.</span><span class="sxs-lookup"><span data-stu-id="8b254-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="8b254-123">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="8b254-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="8b254-124">Предоставляет методы обратного вызова, используемые средой CLR для уведомления профилировщика о начале и завершении JIT-компиляции динамического метода.</span><span class="sxs-lookup"><span data-stu-id="8b254-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="8b254-125">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="8b254-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="8b254-126">Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод уничтожается сборщиком мусора и затем выгружается.</span><span class="sxs-lookup"><span data-stu-id="8b254-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="8b254-127">Интерфейс ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="8b254-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="8b254-128">Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.</span><span class="sxs-lookup"><span data-stu-id="8b254-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="8b254-129">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="8b254-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="8b254-130">Предоставляет методы для последовательного перебора коллекции функций в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8b254-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="8b254-131">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="8b254-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="8b254-132">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="8b254-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="8b254-133">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="8b254-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="8b254-134">Расширяет интерфейс `ICorProfilerInfo` методами, поддерживаемыми платформой .NET Framework 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8b254-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="8b254-135">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="8b254-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="8b254-136">Расширяет интерфейс `ICorProfilerInfo2` с помощью методов, поддерживаемых в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="8b254-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="8b254-137">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="8b254-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="8b254-138">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.</span><span class="sxs-lookup"><span data-stu-id="8b254-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="8b254-139">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="8b254-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="8b254-140">Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий.</span><span class="sxs-lookup"><span data-stu-id="8b254-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="8b254-141">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="8b254-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="8b254-142">Предоставляет перечислитель для всех методов, принадлежащих заданному модулю NGen и встроенных в тело данного метода.</span><span class="sxs-lookup"><span data-stu-id="8b254-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="8b254-143">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="8b254-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="8b254-144">Предоставляет метод для применения новых заданных метаданных к модулю и предоставляет доступ к потоку символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="8b254-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="8b254-145">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="8b254-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="8b254-146">Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="8b254-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="8b254-147">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="8b254-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="8b254-148">Предоставляет методы для последовательного прохода по коллекции замороженных объектов, созданных [Ngen. exe (генератор образов в машинном кодах)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="8b254-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="8b254-149">Интерфейс ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="8b254-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="8b254-150">Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="8b254-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="8b254-151">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="8b254-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="8b254-152">Предоставляет метод [выделения](imethodmalloc-alloc-method.md) для выделения памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="8b254-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b254-153">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8b254-153">Related Sections</span></span>  
 [<span data-ttu-id="8b254-154">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="8b254-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="8b254-155">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="8b254-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="8b254-156">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="8b254-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="8b254-157">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="8b254-157">Profiling Structures</span></span>](profiling-structures.md)
