---
title: Метод ICorProfilerCallback::ExceptionUnwindFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 305c8c7abf778ea68efe06f3bdb57af001ea1b9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227727"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="f8f61-102">Метод ICorProfilerCallback::ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="f8f61-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="f8f61-103">Уведомляет профилировщик об окончании этапа очистки во время обработки исключений в функции.</span><span class="sxs-lookup"><span data-stu-id="f8f61-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f61-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8f61-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f8f61-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8f61-105">Remarks</span></span>  
 <span data-ttu-id="f8f61-106">Когда `ExceptionUnwindFunctionLeave` вызывается метод, экземпляр функции и ее данных стека удаляются из стека.</span><span class="sxs-lookup"><span data-stu-id="f8f61-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="f8f61-107">Профилировщик не должен блокироваться во время данного вызова, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="f8f61-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f8f61-108">Если предпринимается в блоках профилировщика и сбор мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f8f61-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f8f61-109">Кроме того во время этого вызова профилировщик не должна вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="f8f61-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f61-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f8f61-110">Requirements</span></span>  
 <span data-ttu-id="f8f61-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8f61-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f61-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8f61-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8f61-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8f61-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f8f61-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f8f61-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8f61-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f8f61-115">See also</span></span>

- [<span data-ttu-id="f8f61-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f8f61-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f8f61-117">Метод ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="f8f61-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
