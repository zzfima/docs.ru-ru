---
title: Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
ms.openlocfilehash: 4068c8fee13a6086bc6b48bcc6d4117357062747
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449783"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="edfe9-102">Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="edfe9-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="edfe9-103">Задает реализованные профилировщиком функции, которые должны вызываться в обновленных версиях обработчиков "Enter", "Leave" и "таилкалл" управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="edfe9-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfe9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edfe9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edfe9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edfe9-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="edfe9-106">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="edfe9-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="edfe9-107">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="edfe9-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="edfe9-108">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="edfe9-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edfe9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="edfe9-109">Remarks</span></span>  
 <span data-ttu-id="edfe9-110">Метод `SetEnterLeaveFunctionHooks2` аналогичен методу [ICorProfilerInfo:: сетентерлеавефунктионхукс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="edfe9-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="edfe9-111">Используйте первое значение для указания функций, которые будут использоваться в качестве новых версий обратных вызовов Enter/Leave/таилкалл, а второй — для указания функций, которые будут использоваться в качестве старых версий обратных вызовов Enter/Leave/таилкалл.</span><span class="sxs-lookup"><span data-stu-id="edfe9-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="edfe9-112">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="edfe9-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="edfe9-113">Таким же, если профилировщик вызывает и `ICorProfilerInfo::SetEnterLeaveFunctionHooks`, и `SetEnterLeaveFunctionHooks2`, используется `SetEnterLeaveFunctionHooks2`.</span><span class="sxs-lookup"><span data-stu-id="edfe9-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="edfe9-114">Метод `SetEnterLeaveFunctionHooks2` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="edfe9-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edfe9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="edfe9-115">Requirements</span></span>  
 <span data-ttu-id="edfe9-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edfe9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edfe9-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edfe9-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edfe9-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edfe9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edfe9-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edfe9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfe9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="edfe9-120">See also</span></span>

- [<span data-ttu-id="edfe9-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="edfe9-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="edfe9-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="edfe9-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
