---
title: Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb07fb7d5dfaad8623c269a86d2e1182b200cb61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780905"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="a8ccf-102">Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a8ccf-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="a8ccf-103">Задает реализуемые профилировщиком функции, которые будут вызываться в [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) обработчиков управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ccf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8ccf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ccf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8ccf-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="a8ccf-106">[in] Указатель на реализацию для использования в качестве `FunctionEnter3WithInfo` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="a8ccf-107">[in] Указатель на реализацию для использования в качестве `FunctionLeave3WithInfo` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="a8ccf-108">[in] Указатель на реализацию для использования в качестве `FunctionTailcall3WithInfo` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8ccf-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8ccf-109">Remarks</span></span>  
 <span data-ttu-id="a8ccf-110">[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), и [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) обработчики предоставляют стека кадра и проверка аргументов.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="a8ccf-111">Доступ к этим сведениям `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, и/или `COR_PRF_ENABLE_FRAME_INFO` флаги должны быть заданы.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="a8ccf-112">Можно использовать профилировщик [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод, чтобы задать флаги событий, а затем используйте `SetEnterLeaveFunctionHooks3WithInfo` метода для регистрации вашей реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a8ccf-113">Одновременно может быть активным только один набор обратных вызовов, и новая версия имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="a8ccf-114">Таким образом Если профилировщик вызывает оба [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) и `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` используется.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="a8ccf-115">`SetEnterLeaveFunctionHooks3WithInfo` Метод может вызываться только из профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a8ccf-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8ccf-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a8ccf-116">Requirements</span></span>  
 <span data-ttu-id="a8ccf-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ccf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ccf-118">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8ccf-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8ccf-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8ccf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8ccf-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ccf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ccf-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a8ccf-121">See also</span></span>

- [<span data-ttu-id="a8ccf-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="a8ccf-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="a8ccf-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="a8ccf-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="a8ccf-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a8ccf-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="a8ccf-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="a8ccf-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="a8ccf-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a8ccf-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="a8ccf-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a8ccf-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="a8ccf-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a8ccf-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a8ccf-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="a8ccf-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="a8ccf-130">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="a8ccf-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a8ccf-131">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="a8ccf-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a8ccf-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="a8ccf-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
