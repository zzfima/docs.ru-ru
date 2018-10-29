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
ms.openlocfilehash: 27cce8a77d4236829124b45650d5d0ac32a5150c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198007"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="5b433-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="5b433-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="5b433-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) для управления отслеживанием событий и сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="5b433-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="5b433-104">.</span><span class="sxs-lookup"><span data-stu-id="5b433-104">.</span></span> <span data-ttu-id="5b433-105">`ICorProfilerInfo4` Интерфейс является расширением другой `ICorProfilerInfo` интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="5b433-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="5b433-106">Он предоставляет новые методы для поддержки повторная компиляция just-in-time (JIT), добавленные в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b433-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b433-107">Методы</span><span class="sxs-lookup"><span data-stu-id="5b433-107">Methods</span></span>  
  
|<span data-ttu-id="5b433-108">Метод</span><span class="sxs-lookup"><span data-stu-id="5b433-108">Method</span></span>|<span data-ttu-id="5b433-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5b433-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b433-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="5b433-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="5b433-111">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции и перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="5b433-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="5b433-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="5b433-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="5b433-113">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="5b433-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="5b433-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="5b433-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="5b433-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="5b433-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="5b433-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="5b433-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="5b433-117">Сопоставляет указатель инструкции управляемого кода для перекомпиляции JIT версию указанной функции.</span><span class="sxs-lookup"><span data-stu-id="5b433-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="5b433-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="5b433-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="5b433-119">Получает сопоставление из смещений промежуточного языка MSIL в собственные смещения для кода, содержащегося в перекомпиляции JIT версию указанной функции.</span><span class="sxs-lookup"><span data-stu-id="5b433-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="5b433-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="5b433-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="5b433-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="5b433-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="5b433-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="5b433-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="5b433-123">Возвращает массив идентификаторов, определяющих все перекомпиляции JIT версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="5b433-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="5b433-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="5b433-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="5b433-125">Инициализирует текущий поток до последующих вызовов API в одном потоке, поэтому можно избежать этой взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="5b433-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="5b433-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="5b433-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="5b433-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="5b433-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="5b433-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="5b433-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="5b433-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="5b433-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b433-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b433-130">Remarks</span></span>  
 <span data-ttu-id="5b433-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="5b433-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="5b433-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="5b433-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="5b433-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="5b433-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b433-134">Требования</span><span class="sxs-lookup"><span data-stu-id="5b433-134">Requirements</span></span>  
 <span data-ttu-id="5b433-135">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b433-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b433-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b433-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b433-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b433-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b433-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b433-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b433-139">См. также</span><span class="sxs-lookup"><span data-stu-id="5b433-139">See Also</span></span>  
 [<span data-ttu-id="5b433-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5b433-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="5b433-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5b433-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
