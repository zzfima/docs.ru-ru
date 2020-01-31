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
ms.openlocfilehash: 3903ebf1ad35bd7eb1ba49b4f1acda9024678423
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862208"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="e993a-102">Метод ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="e993a-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="e993a-103">Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.</span><span class="sxs-lookup"><span data-stu-id="e993a-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="e993a-104">Этот метод заменяет метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="e993a-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e993a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e993a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e993a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e993a-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e993a-107">заполняет Указатель на перечислитель [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e993a-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e993a-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e993a-108">Remarks</span></span>  
 <span data-ttu-id="e993a-109">Этот метод может перекрываться с `JITCompilation` обратными вызовами, такими как метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e993a-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="e993a-110">Возвращаемое перечисление включает значения для поля `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="e993a-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="e993a-111">Метод [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , который заменяет этот метод, не перечисляет идентификаторы, перекомпилированные с помощью JIT-компилятора, поскольку поле `COR_PRF_FUNCTION::reJitId` всегда имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="e993a-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="e993a-112">Метод `ICorProfilerInfo4::EnumJITedFunctions` выполняет перечисление идентификаторов, перекомпилированных с помощью JIT-компилятора, так как поле `COR_PRF_FUNCTION::reJitId` задано правильно.</span><span class="sxs-lookup"><span data-stu-id="e993a-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="e993a-113">Обратите внимание, что метод [метод icorprofilerinfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) может запускать сборку мусора, в то время как [метод ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="e993a-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="e993a-114">Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="e993a-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e993a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e993a-115">Requirements</span></span>  
 <span data-ttu-id="e993a-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e993a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e993a-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e993a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e993a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e993a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e993a-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e993a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e993a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="e993a-120">See also</span></span>

- [<span data-ttu-id="e993a-121">Метод EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="e993a-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="e993a-122">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="e993a-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="e993a-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="e993a-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e993a-124">Профилирование</span><span class="sxs-lookup"><span data-stu-id="e993a-124">Profiling</span></span>](index.md)
