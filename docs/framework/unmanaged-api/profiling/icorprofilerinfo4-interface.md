---
title: Интерфейс ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f452a3324365fb23e1affc11dbdb2ede15346010
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462446"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="f78cc-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="f78cc-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="f78cc-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) и управления мониторингом событий и сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="f78cc-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="f78cc-104">.</span><span class="sxs-lookup"><span data-stu-id="f78cc-104">.</span></span> <span data-ttu-id="f78cc-105">`ICorProfilerInfo4` Интерфейс является расширением другого `ICorProfilerInfo` интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f78cc-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="f78cc-106">Он предоставляет новые методы для поддержки перекомпиляцию just-in-time (JIT), добавленные в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f78cc-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f78cc-107">Методы</span><span class="sxs-lookup"><span data-stu-id="f78cc-107">Methods</span></span>  
  
|<span data-ttu-id="f78cc-108">Метод</span><span class="sxs-lookup"><span data-stu-id="f78cc-108">Method</span></span>|<span data-ttu-id="f78cc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f78cc-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f78cc-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="f78cc-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="f78cc-111">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции и перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="f78cc-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="f78cc-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="f78cc-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="f78cc-113">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="f78cc-113">Gets an enumerator that that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="f78cc-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="f78cc-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="f78cc-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="f78cc-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="f78cc-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="f78cc-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="f78cc-117">Сопоставляется указатель инструкции управляемого кода JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="f78cc-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="f78cc-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="f78cc-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="f78cc-119">Получает сопоставление из смещений промежуточного языка MSIL в собственные смещения для кода, содержащегося в версии указанной функции с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="f78cc-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="f78cc-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="f78cc-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="f78cc-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="f78cc-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="f78cc-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="f78cc-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="f78cc-123">Возвращает массив идентификаторов, определяющих все JIT-компилятора версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="f78cc-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="f78cc-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="f78cc-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="f78cc-125">Инициализирует текущий поток до последующих вызовов API в том же потоке, поэтому можно избежать, взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="f78cc-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="f78cc-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="f78cc-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="f78cc-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="f78cc-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="f78cc-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="f78cc-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="f78cc-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="f78cc-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f78cc-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="f78cc-130">Remarks</span></span>  
 <span data-ttu-id="f78cc-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="f78cc-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="f78cc-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="f78cc-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="f78cc-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="f78cc-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f78cc-134">Требования</span><span class="sxs-lookup"><span data-stu-id="f78cc-134">Requirements</span></span>  
 <span data-ttu-id="f78cc-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f78cc-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f78cc-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f78cc-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f78cc-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f78cc-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f78cc-138">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f78cc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f78cc-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f78cc-139">See Also</span></span>  
 [<span data-ttu-id="f78cc-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="f78cc-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f78cc-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f78cc-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
