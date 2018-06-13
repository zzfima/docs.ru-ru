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
ms.openlocfilehash: 4f971c5175307c1e1df6890c136b306860e54d23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452713"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="a72fe-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="a72fe-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="a72fe-103">Уведомляет профилировщик о том, что указанный поток возобновлен после приостановки.</span><span class="sxs-lookup"><span data-stu-id="a72fe-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a72fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a72fe-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a72fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a72fe-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a72fe-106">[in] Идентификатор потока, возобновлено.</span><span class="sxs-lookup"><span data-stu-id="a72fe-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a72fe-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a72fe-107">Requirements</span></span>  
 <span data-ttu-id="a72fe-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a72fe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a72fe-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a72fe-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a72fe-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a72fe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a72fe-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a72fe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72fe-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a72fe-112">See Also</span></span>  
 [<span data-ttu-id="a72fe-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a72fe-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a72fe-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="a72fe-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
