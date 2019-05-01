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
ms.openlocfilehash: 177e5ef8054f408dc8ec3475c56043394a636bc0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049457"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="85ca8-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="85ca8-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="85ca8-103">Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) для управления отслеживанием событий и сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="85ca8-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="85ca8-104">.</span><span class="sxs-lookup"><span data-stu-id="85ca8-104">.</span></span> <span data-ttu-id="85ca8-105">`ICorProfilerInfo4` Интерфейс является расширением другой `ICorProfilerInfo` интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="85ca8-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="85ca8-106">Он предоставляет новые методы для поддержки повторная компиляция just-in-time (JIT), добавленные в [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85ca8-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85ca8-107">Методы</span><span class="sxs-lookup"><span data-stu-id="85ca8-107">Methods</span></span>  
  
|<span data-ttu-id="85ca8-108">Метод</span><span class="sxs-lookup"><span data-stu-id="85ca8-108">Method</span></span>|<span data-ttu-id="85ca8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="85ca8-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85ca8-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="85ca8-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="85ca8-111">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции и перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="85ca8-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="85ca8-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="85ca8-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="85ca8-113">Возвращает перечислитель, который предоставляет методы для последовательного перебора коллекции все управляемые потоки в процессе профилирования.</span><span class="sxs-lookup"><span data-stu-id="85ca8-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="85ca8-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="85ca8-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="85ca8-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="85ca8-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="85ca8-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="85ca8-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="85ca8-117">Сопоставляет указатель инструкции управляемого кода для перекомпиляции JIT версию указанной функции.</span><span class="sxs-lookup"><span data-stu-id="85ca8-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="85ca8-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="85ca8-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="85ca8-119">Получает сопоставление из смещений промежуточного языка MSIL в собственные смещения для кода, содержащегося в перекомпиляции JIT версию указанной функции.</span><span class="sxs-lookup"><span data-stu-id="85ca8-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="85ca8-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="85ca8-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="85ca8-121">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="85ca8-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="85ca8-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="85ca8-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="85ca8-123">Возвращает массив идентификаторов, определяющих все перекомпиляции JIT версии указанной функции, по-прежнему выделяются.</span><span class="sxs-lookup"><span data-stu-id="85ca8-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="85ca8-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="85ca8-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="85ca8-125">Инициализирует текущий поток до последующих вызовов API в одном потоке, поэтому можно избежать этой взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="85ca8-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="85ca8-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="85ca8-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="85ca8-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="85ca8-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="85ca8-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="85ca8-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="85ca8-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="85ca8-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85ca8-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="85ca8-130">Remarks</span></span>  
 <span data-ttu-id="85ca8-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="85ca8-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="85ca8-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="85ca8-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="85ca8-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="85ca8-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ca8-134">Требования</span><span class="sxs-lookup"><span data-stu-id="85ca8-134">Requirements</span></span>  
 <span data-ttu-id="85ca8-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ca8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ca8-136">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85ca8-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85ca8-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85ca8-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85ca8-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85ca8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ca8-139">См. также</span><span class="sxs-lookup"><span data-stu-id="85ca8-139">See also</span></span>

- [<span data-ttu-id="85ca8-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="85ca8-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="85ca8-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="85ca8-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
