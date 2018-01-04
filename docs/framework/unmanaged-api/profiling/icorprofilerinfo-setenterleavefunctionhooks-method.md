---
title: "Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e41fdf02f299d118fce025e2a5a3314feb134971
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="4d146-102">Метод ICorProfilerInfo::SetEnterLeaveFunctionHooks</span><span class="sxs-lookup"><span data-stu-id="4d146-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="4d146-103">Задает реализуемые профилировщиком функции, вызываемого при «введите», «оставьте» и «tailcall» обработчиках управляемых функций.</span><span class="sxs-lookup"><span data-stu-id="4d146-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d146-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d146-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d146-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4d146-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="4d146-106">[in] Указатель на реализацию для использования в качестве [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4d146-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="4d146-107">[in] Указатель на реализацию для использования в качестве [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4d146-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="4d146-108">[in] Указатель на реализацию для использования в качестве [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4d146-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d146-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d146-109">Remarks</span></span>  
 <span data-ttu-id="4d146-110">В платформе .NET Framework версии 1.0 каждого указателя функции может быть null, чтобы отключить соответствующие ответного вызова.</span><span class="sxs-lookup"><span data-stu-id="4d146-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="4d146-111">Одновременно может быть активной только один набор обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="4d146-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="4d146-112">Таким образом Если профилировщик вызывает оба `SetEnterLeaveFunctionHooks` и [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), затем `SetEnterLeaveFunctionHooks2` имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="4d146-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="4d146-113">`SetEnterLeaveFunctionHooks` Метод может вызываться только из профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4d146-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d146-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4d146-114">Requirements</span></span>  
 <span data-ttu-id="4d146-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d146-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d146-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d146-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d146-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d146-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d146-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d146-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d146-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4d146-119">See Also</span></span>  
 [<span data-ttu-id="4d146-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="4d146-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
