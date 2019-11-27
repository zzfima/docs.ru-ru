---
title: Метод ICorProfilerInfo4::EnumJITedFunctions2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 09d273a81ed4f956508e4fadb628b28e18d00f90
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449566"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="d0a4f-102">Метод ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="d0a4f-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="d0a4f-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="d0a4f-104">Этот метод заменяет метод [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) , который не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a4f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0a4f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0a4f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0a4f-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d0a4f-107">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d0a4f-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0a4f-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="d0a4f-108">Remarks</span></span>  
 <span data-ttu-id="d0a4f-109">Этот метод может перекрываться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d0a4f-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="d0a4f-110">Возвращаемое перечисление включает значения для поля `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="d0a4f-111">Метод [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) , который заменяет этот метод, не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора, поскольку поле `COR_PRF_FUNCTION::reJitId` всегда имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="d0a4f-112">Метод `ICorProfilerInfo4::EnumJITedFunctions` выполняет перечисление идентификаторов, перекомпилированных с помощью JIT-компилятора, так как поле `COR_PRF_FUNCTION::reJitId` задано правильно.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="d0a4f-113">Обратите внимание, что метод [метод icorprofilerinfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) может запускать сборку мусора, в то время как [метод ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="d0a4f-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="d0a4f-114">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="d0a4f-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0a4f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d0a4f-115">Requirements</span></span>  
 <span data-ttu-id="d0a4f-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0a4f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0a4f-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0a4f-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0a4f-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0a4f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0a4f-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a4f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a4f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d0a4f-120">See also</span></span>

- [<span data-ttu-id="d0a4f-121">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="d0a4f-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="d0a4f-122">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="d0a4f-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="d0a4f-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="d0a4f-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d0a4f-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="d0a4f-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
