---
title: "Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c460cfd24a83ca2a6c75e061b7a797c8f455bc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="edb96-102">Метод ICorProfilerInfo2::SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="edb96-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="edb96-103">Задает реализуемые профилировщиком функции, должен быть вызван в обновленных версий «ввод», «оставьте» и «tailcall» обработчиках управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="edb96-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edb96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edb96-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="edb96-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="edb96-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="edb96-106">[in] Указатель на реализацию для использования в качестве [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="edb96-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="edb96-107">[in] Указатель на реализацию для использования в качестве [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="edb96-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="edb96-108">[in] Указатель на реализацию для использования в качестве [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="edb96-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edb96-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="edb96-109">Remarks</span></span>  
 <span data-ttu-id="edb96-110">`SetEnterLeaveFunctionHooks2` Аналогичен методу [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="edb96-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="edb96-111">Позволяет указать функции для использования в качестве новых версий обратных вызовов enter/leave/tailcall, а второй для указания функции для использования в качестве более старых версий обратных вызовов enter/leave/tailcall первый из них.</span><span class="sxs-lookup"><span data-stu-id="edb96-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="edb96-112">Одновременно может быть активным только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="edb96-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="edb96-113">Таким образом Если профилировщик вызывает оба `ICorProfilerInfo::SetEnterLeaveFunctionHooks` и `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` используется.</span><span class="sxs-lookup"><span data-stu-id="edb96-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="edb96-114">`SetEnterLeaveFunctionHooks2` Метод может вызываться только из профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="edb96-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edb96-115">Требования</span><span class="sxs-lookup"><span data-stu-id="edb96-115">Requirements</span></span>  
 <span data-ttu-id="edb96-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edb96-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edb96-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edb96-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edb96-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edb96-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edb96-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edb96-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb96-120">См. также</span><span class="sxs-lookup"><span data-stu-id="edb96-120">See Also</span></span>  
 [<span data-ttu-id="edb96-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="edb96-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="edb96-122">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="edb96-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
