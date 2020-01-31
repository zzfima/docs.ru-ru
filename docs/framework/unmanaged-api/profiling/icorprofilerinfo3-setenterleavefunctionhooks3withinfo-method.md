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
ms.openlocfilehash: 4fe18b4f07e6f282571b13faff5ce51b66ce416b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868490"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="af2b1-102">Метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af2b1-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="af2b1-103">Задает реализованные профилировщиком функции, которые будут вызываться для обработчиков [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="af2b1-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af2b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af2b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af2b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="af2b1-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="af2b1-106">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="af2b1-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="af2b1-107">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="af2b1-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="af2b1-108">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="af2b1-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af2b1-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="af2b1-109">Remarks</span></span>  
 <span data-ttu-id="af2b1-110">Обработчики [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) предоставляют кадры стека и проверку аргументов.</span><span class="sxs-lookup"><span data-stu-id="af2b1-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="af2b1-111">Для доступа к этой информации необходимо задать флаги `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`и/или `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="af2b1-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="af2b1-112">Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать метод `SetEnterLeaveFunctionHooks3WithInfo` для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="af2b1-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="af2b1-113">В каждый момент времени активным может быть только один набор обратных вызовов, а последняя версия имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="af2b1-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="af2b1-114">Таким образом, если профилировщик вызывает и [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) , и `SetEnterLeaveFunctionHooks3WithInfo`, используется `SetEnterLeaveFunctionHooks3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="af2b1-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="af2b1-115">Метод `SetEnterLeaveFunctionHooks3WithInfo` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="af2b1-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af2b1-116">Требования</span><span class="sxs-lookup"><span data-stu-id="af2b1-116">Requirements</span></span>  
 <span data-ttu-id="af2b1-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af2b1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af2b1-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="af2b1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="af2b1-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af2b1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af2b1-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af2b1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af2b1-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="af2b1-121">See also</span></span>

- [<span data-ttu-id="af2b1-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="af2b1-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="af2b1-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="af2b1-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="af2b1-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="af2b1-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="af2b1-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="af2b1-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="af2b1-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af2b1-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="af2b1-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af2b1-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="af2b1-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="af2b1-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="af2b1-129">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="af2b1-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="af2b1-130">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="af2b1-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="af2b1-131">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="af2b1-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="af2b1-132">Профилирование</span><span class="sxs-lookup"><span data-stu-id="af2b1-132">Profiling</span></span>](index.md)
