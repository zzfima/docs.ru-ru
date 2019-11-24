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
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448004"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="5faf7-102">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="5faf7-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="5faf7-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span><span class="sxs-lookup"><span data-stu-id="5faf7-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="5faf7-104">.</span><span class="sxs-lookup"><span data-stu-id="5faf7-104">.</span></span> <span data-ttu-id="5faf7-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="5faf7-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="5faf7-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="5faf7-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5faf7-107">Методы</span><span class="sxs-lookup"><span data-stu-id="5faf7-107">Methods</span></span>  
  
|<span data-ttu-id="5faf7-108">Метод</span><span class="sxs-lookup"><span data-stu-id="5faf7-108">Method</span></span>|<span data-ttu-id="5faf7-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5faf7-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5faf7-110">Метод EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="5faf7-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="5faf7-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span><span class="sxs-lookup"><span data-stu-id="5faf7-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="5faf7-112">Метод EnumThreads</span><span class="sxs-lookup"><span data-stu-id="5faf7-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="5faf7-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span><span class="sxs-lookup"><span data-stu-id="5faf7-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="5faf7-114">Метод GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="5faf7-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="5faf7-115">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="5faf7-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="5faf7-116">Метод GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="5faf7-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="5faf7-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span><span class="sxs-lookup"><span data-stu-id="5faf7-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="5faf7-118">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="5faf7-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="5faf7-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span><span class="sxs-lookup"><span data-stu-id="5faf7-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="5faf7-120">Метод GetObjectSize2</span><span class="sxs-lookup"><span data-stu-id="5faf7-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="5faf7-121">Returns the size of a specified object.</span><span class="sxs-lookup"><span data-stu-id="5faf7-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="5faf7-122">Метод GetReJITIDs</span><span class="sxs-lookup"><span data-stu-id="5faf7-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="5faf7-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span><span class="sxs-lookup"><span data-stu-id="5faf7-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="5faf7-124">Метод InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="5faf7-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="5faf7-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span><span class="sxs-lookup"><span data-stu-id="5faf7-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="5faf7-126">Метод RequestReJIT</span><span class="sxs-lookup"><span data-stu-id="5faf7-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="5faf7-127">Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="5faf7-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="5faf7-128">Метод RequestRevert</span><span class="sxs-lookup"><span data-stu-id="5faf7-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="5faf7-129">Восстанавливает исходные версии всех экземпляров указанных функций.</span><span class="sxs-lookup"><span data-stu-id="5faf7-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5faf7-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="5faf7-130">Remarks</span></span>  
 <span data-ttu-id="5faf7-131">Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков.</span><span class="sxs-lookup"><span data-stu-id="5faf7-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="5faf7-132">Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой.</span><span class="sxs-lookup"><span data-stu-id="5faf7-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="5faf7-133">Список возможных кодов возврата см. в файле CorError.h.</span><span class="sxs-lookup"><span data-stu-id="5faf7-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5faf7-134">Требования</span><span class="sxs-lookup"><span data-stu-id="5faf7-134">Requirements</span></span>  
 <span data-ttu-id="5faf7-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5faf7-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5faf7-136">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5faf7-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5faf7-137">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5faf7-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5faf7-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5faf7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5faf7-139">См. также</span><span class="sxs-lookup"><span data-stu-id="5faf7-139">See also</span></span>

- [<span data-ttu-id="5faf7-140">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="5faf7-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5faf7-141">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5faf7-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
