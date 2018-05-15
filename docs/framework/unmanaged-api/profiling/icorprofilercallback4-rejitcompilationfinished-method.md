---
title: Метод ICorProfilerCallback4::ReJITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf2e1be735150dfb006e2274c79c25649d0271d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="140ff-102">Метод ICorProfilerCallback4::ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="140ff-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="140ff-103">Уведомляет профилировщик о завершении повторной компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="140ff-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="140ff-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="140ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="140ff-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="140ff-106">[in] Идентификатор функции, который был перекомпилирован.</span><span class="sxs-lookup"><span data-stu-id="140ff-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="140ff-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="140ff-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="140ff-108">[in] Значение, указывающее, успешно ли выполнено перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="140ff-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="140ff-109">[in] `true` для указания, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="140ff-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="140ff-110">Значение `true` не представляет угрозы для среды выполнения, но может повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="140ff-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140ff-111">Требования</span><span class="sxs-lookup"><span data-stu-id="140ff-111">Requirements</span></span>  
 <span data-ttu-id="140ff-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="140ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140ff-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="140ff-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="140ff-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="140ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="140ff-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140ff-116">См. также</span><span class="sxs-lookup"><span data-stu-id="140ff-116">See Also</span></span>  
 [<span data-ttu-id="140ff-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="140ff-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="140ff-118">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="140ff-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="140ff-119">Метод JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="140ff-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="140ff-120">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="140ff-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
