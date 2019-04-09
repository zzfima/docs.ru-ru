---
title: Метод ICorProfilerCallback::ExceptionUnwindFinallyEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfc0d763fa1ea14c55a0c61fbf63db65fefe02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137869"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="d4c8d-102">Метод ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="d4c8d-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="d4c8d-103">Уведомляет профилировщик, фазы перемотки исключения вводит обработки `finally` предложение, содержащиеся в указанной функции.</span><span class="sxs-lookup"><span data-stu-id="d4c8d-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4c8d-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4c8d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4c8d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d4c8d-106">[in] Идентификатор функции, которая содержит `finally` предложение.</span><span class="sxs-lookup"><span data-stu-id="d4c8d-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4c8d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4c8d-107">Remarks</span></span>  
 <span data-ttu-id="d4c8d-108">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="d4c8d-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d4c8d-109">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="d4c8d-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d4c8d-110">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="d4c8d-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c8d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d4c8d-111">Requirements</span></span>  
 <span data-ttu-id="d4c8d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c8d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c8d-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4c8d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4c8d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4c8d-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d4c8d-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d4c8d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4c8d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d4c8d-116">See also</span></span>

- [<span data-ttu-id="d4c8d-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d4c8d-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d4c8d-118">Метод GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="d4c8d-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="d4c8d-119">Метод ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="d4c8d-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
