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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228865"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="0f056-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="0f056-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="0f056-103">Уведомляет профилировщик о том, что указанный поток возобновлен после приостановки.</span><span class="sxs-lookup"><span data-stu-id="0f056-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f056-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f056-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f056-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f056-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0f056-106">[in] Идентификатор потока, который было возобновлено.</span><span class="sxs-lookup"><span data-stu-id="0f056-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f056-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0f056-107">Requirements</span></span>  
 <span data-ttu-id="0f056-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f056-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f056-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f056-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f056-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f056-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0f056-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0f056-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f056-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0f056-112">See also</span></span>

- [<span data-ttu-id="0f056-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0f056-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0f056-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="0f056-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
