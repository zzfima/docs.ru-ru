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
ms.openlocfilehash: ab7c8cbc41967af04c4c9a8813f32b9b1f01c6a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866355"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="e82cd-102">Метод ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="e82cd-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="e82cd-103">Уведомляет профилировщик о том, что фаза очистки при обработке исключений вводит `finally` предложение, содержащееся в указанной функции.</span><span class="sxs-lookup"><span data-stu-id="e82cd-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e82cd-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e82cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e82cd-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="e82cd-106">\[в] идентификатор функции, которая содержит предложение `finally`.</span><span class="sxs-lookup"><span data-stu-id="e82cd-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="e82cd-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e82cd-107">Remarks</span></span>  
 <span data-ttu-id="e82cd-108">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="e82cd-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e82cd-109">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="e82cd-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e82cd-110">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="e82cd-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e82cd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e82cd-111">Requirements</span></span>  
 <span data-ttu-id="e82cd-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e82cd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e82cd-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e82cd-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e82cd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e82cd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e82cd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e82cd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82cd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e82cd-116">See also</span></span>

- [<span data-ttu-id="e82cd-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e82cd-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e82cd-118">Метод GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="e82cd-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="e82cd-119">Метод ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="e82cd-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
