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
ms.openlocfilehash: 3b25ae535bfe50d216ca64a2e8163c0e6df58535
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755974"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="36f5b-102">Метод ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="36f5b-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="36f5b-103">Уведомляет профилировщик, фазы перемотки исключения вводит обработки `finally` предложение, содержащиеся в указанной функции.</span><span class="sxs-lookup"><span data-stu-id="36f5b-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36f5b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36f5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36f5b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="36f5b-106">[in] Идентификатор функции, которая содержит `finally` предложение.</span><span class="sxs-lookup"><span data-stu-id="36f5b-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36f5b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="36f5b-107">Remarks</span></span>  
 <span data-ttu-id="36f5b-108">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="36f5b-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="36f5b-109">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="36f5b-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="36f5b-110">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="36f5b-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36f5b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="36f5b-111">Requirements</span></span>  
 <span data-ttu-id="36f5b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36f5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36f5b-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36f5b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36f5b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36f5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36f5b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36f5b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f5b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="36f5b-116">See also</span></span>

- [<span data-ttu-id="36f5b-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="36f5b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="36f5b-118">Метод GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="36f5b-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="36f5b-119">Метод ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="36f5b-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
