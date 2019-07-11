---
title: Метод ICorProfilerCallback::RuntimeResumeFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 883e226042225b63097acf731b13abd69cc757ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750418"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="eeb7a-102">Метод ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="eeb7a-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="eeb7a-103">Уведомляет профилировщик, что среда выполнения была возобновлена все потоки среды выполнения и вернулся к нормальной работе.</span><span class="sxs-lookup"><span data-stu-id="eeb7a-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eeb7a-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eeb7a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="eeb7a-105">Remarks</span></span>  
 <span data-ttu-id="eeb7a-106">`RuntimeResumeFinished` Обратного вызова не обязательно находиться на том же потоке [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="eeb7a-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="eeb7a-107">Тем не менее, оно возникает в том же потоке, что [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="eeb7a-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb7a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="eeb7a-108">Requirements</span></span>  
 <span data-ttu-id="eeb7a-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeb7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb7a-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eeb7a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eeb7a-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeb7a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeb7a-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb7a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eeb7a-113">See also</span></span>

- [<span data-ttu-id="eeb7a-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="eeb7a-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
