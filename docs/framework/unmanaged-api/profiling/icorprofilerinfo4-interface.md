---
title: "Интерфейс ICorProfilerInfo4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4
helpviewer_keywords: ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db91347ad2c951c28ea7b653336450929d37bdcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="04a5a-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="04a5a-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="04a5a-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) и управления мониторингом событий и сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="04a5a-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="04a5a-104">.</span><span class="sxs-lookup"><span data-stu-id="04a5a-104">.</span></span> <span data-ttu-id="04a5a-105">`ICorProfilerInfo4` Интерфейс является расширением другого `ICorProfilerInfo` интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="04a5a-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="04a5a-106">Он предоставляет новые методы для поддержки перекомпиляцию just-in-time (JIT), добавленные в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04a5a-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04a5a-107">Методы</span><span class="sxs-lookup"><span data-stu-id="04a5a-107">Methods</span></span>  
  
|<span data-ttu-id="04a5a-108">Метод</span><span class="sxs-lookup"><span data-stu-id="04a5a-108">Method</span></span>|<span data-ttu-id="04a5a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="04a5a-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04a5a-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="04a5a-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="04a5a-111">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции и перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="04a5a-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="04a5a-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="04a5a-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="04a5a-113">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="04a5a-113">Gets an enumerator that that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="04a5a-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="04a5a-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="04a5a-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="04a5a-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="04a5a-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="04a5a-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="04a5a-117">Сопоставляется указатель инструкции управляемого кода JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="04a5a-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="04a5a-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="04a5a-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="04a5a-119">Получает сопоставление из смещений промежуточного языка MSIL в собственные смещения для кода, содержащегося в версии указанной функции с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="04a5a-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="04a5a-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="04a5a-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="04a5a-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="04a5a-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="04a5a-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="04a5a-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="04a5a-123">Возвращает массив идентификаторов, определяющих все JIT-компилятора версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="04a5a-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="04a5a-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="04a5a-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="04a5a-125">Инициализирует текущий поток до последующих вызовов API в том же потоке, поэтому можно избежать, взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="04a5a-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="04a5a-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="04a5a-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="04a5a-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="04a5a-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="04a5a-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="04a5a-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="04a5a-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="04a5a-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04a5a-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="04a5a-130">Remarks</span></span>  
 <span data-ttu-id="04a5a-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="04a5a-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="04a5a-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="04a5a-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="04a5a-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="04a5a-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04a5a-134">Требования</span><span class="sxs-lookup"><span data-stu-id="04a5a-134">Requirements</span></span>  
 <span data-ttu-id="04a5a-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04a5a-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04a5a-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04a5a-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04a5a-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04a5a-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04a5a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a5a-139">См. также</span><span class="sxs-lookup"><span data-stu-id="04a5a-139">See Also</span></span>  
 [<span data-ttu-id="04a5a-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="04a5a-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="04a5a-141">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="04a5a-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
