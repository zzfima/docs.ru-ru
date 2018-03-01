---
title: "Метод ICorProfilerInfo4::EnumJITedFunctions2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7dc381848307ea0606f6989d6946c11aa5ef9a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="47050-102">Метод ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="47050-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="47050-103">Возвращает перечислитель для всех функций, которые были ранее JIT-компиляции и перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="47050-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="47050-104">Этот метод заменяет [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) метод, который не перечислить идентификаторы с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="47050-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47050-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47050-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47050-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="47050-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="47050-107">[out] Указатель на [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) перечислителя.</span><span class="sxs-lookup"><span data-stu-id="47050-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47050-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="47050-108">Remarks</span></span>  
 <span data-ttu-id="47050-109">Этот метод может перекрывать `JITCompilation` обратных вызовов, таких как [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="47050-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="47050-110">Возвращенного перечисления включают значения для `COR_PRF_FUNCTION::reJitId` поля.</span><span class="sxs-lookup"><span data-stu-id="47050-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="47050-111">[ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) метод, который заменяет этот метод, не перечислить идентификаторы с помощью JIT-компилятора, потому что `COR_PRF_FUNCTION::reJitId` всегда равно 0.</span><span class="sxs-lookup"><span data-stu-id="47050-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="47050-112">`ICorProfilerInfo4::EnumJITedFunctions` Метод перечисления идентификаторов с помощью JIT-компилятора, потому что `COR_PRF_FUNCTION::reJitId` поле задано правильно.</span><span class="sxs-lookup"><span data-stu-id="47050-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="47050-113">Обратите внимание, что [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) метод может инициировать сборку мусора, тогда как [метод ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="47050-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="47050-114">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="47050-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47050-115">Требования</span><span class="sxs-lookup"><span data-stu-id="47050-115">Requirements</span></span>  
 <span data-ttu-id="47050-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47050-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47050-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47050-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47050-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47050-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47050-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47050-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47050-120">См. также</span><span class="sxs-lookup"><span data-stu-id="47050-120">See Also</span></span>  
 [<span data-ttu-id="47050-121">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="47050-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)  
 [<span data-ttu-id="47050-122">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="47050-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="47050-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="47050-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="47050-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="47050-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
