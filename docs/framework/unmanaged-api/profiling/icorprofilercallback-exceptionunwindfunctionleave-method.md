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
ms.openlocfilehash: 556048be66a7c60dd82a8d51391a86655db6802a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755927"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="bc39c-102">Метод ICorProfilerCallback::ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="bc39c-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="bc39c-103">Уведомляет профилировщик об окончании этапа очистки во время обработки исключений в функции.</span><span class="sxs-lookup"><span data-stu-id="bc39c-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc39c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc39c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bc39c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc39c-105">Remarks</span></span>  
 <span data-ttu-id="bc39c-106">Когда `ExceptionUnwindFunctionLeave` вызывается метод, экземпляр функции и ее данных стека удаляются из стека.</span><span class="sxs-lookup"><span data-stu-id="bc39c-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="bc39c-107">Профилировщик не должен блокироваться во время данного вызова, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="bc39c-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bc39c-108">Если предпринимается в блоках профилировщика и сбор мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bc39c-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bc39c-109">Кроме того во время этого вызова профилировщик не должна вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="bc39c-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc39c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bc39c-110">Requirements</span></span>  
 <span data-ttu-id="bc39c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc39c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc39c-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc39c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc39c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc39c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc39c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc39c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc39c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bc39c-115">See also</span></span>

- [<span data-ttu-id="bc39c-116">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bc39c-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bc39c-117">Метод ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="bc39c-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
