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
ms.openlocfilehash: a2cf80c7e02d706b0b00ea87aa62986107cdd6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689748"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="cea9e-102">Метод ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="cea9e-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="cea9e-103">Уведомляет профилировщик, что среда выполнения была возобновлена все потоки среды выполнения и вернулся к нормальной работе.</span><span class="sxs-lookup"><span data-stu-id="cea9e-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cea9e-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cea9e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="cea9e-105">Remarks</span></span>  
 <span data-ttu-id="cea9e-106">`RuntimeResumeFinished` Обратного вызова не обязательно находиться на том же потоке [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="cea9e-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="cea9e-107">Тем не менее, оно возникает в том же потоке, что [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="cea9e-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea9e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="cea9e-108">Requirements</span></span>  
 <span data-ttu-id="cea9e-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea9e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea9e-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cea9e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cea9e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cea9e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cea9e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea9e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea9e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cea9e-113">See also</span></span>
- [<span data-ttu-id="cea9e-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cea9e-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
