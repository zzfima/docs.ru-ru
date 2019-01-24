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
ms.openlocfilehash: dc0d0e6094d5c4668126714b36915cfa4512c1b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517634"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="1952e-102">Метод ICorProfilerCallback::RuntimeResumeStarted</span><span class="sxs-lookup"><span data-stu-id="1952e-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="1952e-103">Уведомляет профилировщик о том, что среда выполнения возобновляет работу всех потоков во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1952e-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1952e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1952e-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1952e-105">Требования</span><span class="sxs-lookup"><span data-stu-id="1952e-105">Requirements</span></span>  
 <span data-ttu-id="1952e-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1952e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1952e-107">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1952e-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1952e-108">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1952e-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1952e-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1952e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1952e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="1952e-110">See also</span></span>
- [<span data-ttu-id="1952e-111">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1952e-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1952e-112">Метод RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="1952e-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
