---
title: Метод ICorProfilerCallback::RuntimeThreadResumed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228865"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="c1e79-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="c1e79-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="c1e79-103">Уведомляет профилировщик о том, что указанный поток возобновлен после приостановки.</span><span class="sxs-lookup"><span data-stu-id="c1e79-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1e79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1e79-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1e79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1e79-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="c1e79-106">[in] Идентификатор потока, который было возобновлено.</span><span class="sxs-lookup"><span data-stu-id="c1e79-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1e79-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c1e79-107">Requirements</span></span>  
 <span data-ttu-id="c1e79-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1e79-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1e79-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1e79-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1e79-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1e79-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1e79-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1e79-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e79-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c1e79-112">See also</span></span>

- [<span data-ttu-id="c1e79-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c1e79-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c1e79-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="c1e79-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
