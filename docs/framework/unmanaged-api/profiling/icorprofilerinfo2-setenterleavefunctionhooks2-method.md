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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb7c8fa40d260e45ae536f1b58c6ab360f35448e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550647"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="87594-102">Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="87594-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="87594-103">Задает реализуемые профилировщиком функции, вызываемого на обновленные версии «enter», «проверить» и «tailcall» обработчиков управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="87594-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87594-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87594-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87594-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="87594-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="87594-106">[in] Указатель на реализацию для использования в качестве [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="87594-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="87594-107">[in] Указатель на реализацию для использования в качестве [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="87594-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="87594-108">[in] Указатель на реализацию для использования в качестве [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="87594-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87594-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="87594-109">Remarks</span></span>  
 <span data-ttu-id="87594-110">`SetEnterLeaveFunctionHooks2` Метод аналогичен методу [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="87594-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="87594-111">Первый вариант используется для указания функции для использования в качестве более новых версиях enter/leave/tailcall обратные вызовы, а второй – для указания функции для использования в качестве более старых версиях enter/leave/tailcall обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="87594-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="87594-112">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="87594-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="87594-113">Таким образом Если профилировщик вызывает оба `ICorProfilerInfo::SetEnterLeaveFunctionHooks` и `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` используется.</span><span class="sxs-lookup"><span data-stu-id="87594-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="87594-114">`SetEnterLeaveFunctionHooks2` Метод может вызываться только из профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="87594-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87594-115">Требования</span><span class="sxs-lookup"><span data-stu-id="87594-115">Requirements</span></span>  
 <span data-ttu-id="87594-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87594-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87594-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87594-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87594-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87594-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87594-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87594-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87594-120">См. также</span><span class="sxs-lookup"><span data-stu-id="87594-120">See also</span></span>
- [<span data-ttu-id="87594-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="87594-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="87594-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="87594-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
