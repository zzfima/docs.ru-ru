---
title: Метод ICorProfilerCallback::RuntimeResumeStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70e687f0645fdb68d95effe6fdd52178b92c08e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="4bfb1-102">Метод ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="4bfb1-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="4bfb1-103">Уведомляет профилировщик о том, что среда выполнения возобновляет работу всех потоков во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4bfb1-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bfb1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4bfb1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="4bfb1-105">Requirements</span></span>  
 <span data-ttu-id="4bfb1-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bfb1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bfb1-107">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4bfb1-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4bfb1-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bfb1-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bfb1-109">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bfb1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfb1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4bfb1-110">See Also</span></span>  
 [<span data-ttu-id="4bfb1-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4bfb1-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4bfb1-112">Метод RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="4bfb1-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
