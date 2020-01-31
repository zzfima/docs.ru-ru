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
ms.openlocfilehash: 7eac42e1d8132ca9e6d6c6b43efd43b88c1e5d3d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868589"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="1fcba-102">Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="1fcba-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="1fcba-103">Задает реализованные профилировщиком функции, которые должны вызываться в обновленных версиях обработчиков "Enter", "Leave" и "таилкалл" управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="1fcba-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fcba-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fcba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fcba-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="1fcba-106">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1fcba-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="1fcba-107">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1fcba-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="1fcba-108">окне Указатель на реализацию, которая будет использоваться в качестве обратного вызова [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1fcba-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fcba-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="1fcba-109">Remarks</span></span>  
 <span data-ttu-id="1fcba-110">Метод `SetEnterLeaveFunctionHooks2` аналогичен методу [ICorProfilerInfo:: сетентерлеавефунктионхукс](icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1fcba-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="1fcba-111">Используйте первое значение для указания функций, которые будут использоваться в качестве новых версий обратных вызовов Enter/Leave/таилкалл, а второй — для указания функций, которые будут использоваться в качестве старых версий обратных вызовов Enter/Leave/таилкалл.</span><span class="sxs-lookup"><span data-stu-id="1fcba-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="1fcba-112">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="1fcba-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="1fcba-113">Таким же, если профилировщик вызывает и `ICorProfilerInfo::SetEnterLeaveFunctionHooks`, и `SetEnterLeaveFunctionHooks2`, используется `SetEnterLeaveFunctionHooks2`.</span><span class="sxs-lookup"><span data-stu-id="1fcba-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="1fcba-114">Метод `SetEnterLeaveFunctionHooks2` может быть вызван только из обратного вызова [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) профилировщика.</span><span class="sxs-lookup"><span data-stu-id="1fcba-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fcba-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1fcba-115">Requirements</span></span>  
 <span data-ttu-id="1fcba-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fcba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fcba-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fcba-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fcba-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fcba-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fcba-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcba-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="1fcba-120">See also</span></span>

- [<span data-ttu-id="1fcba-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1fcba-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1fcba-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="1fcba-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
