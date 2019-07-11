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
ms.openlocfilehash: 5b4464c72e8d189cea4831cb641b9ff05063ce25
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747216"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="9f845-102">Метод ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="9f845-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="9f845-103">Уведомляет профилировщик о том, что указанный поток возобновлен после приостановки.</span><span class="sxs-lookup"><span data-stu-id="9f845-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f845-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f845-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f845-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f845-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="9f845-106">[in] Идентификатор потока, который было возобновлено.</span><span class="sxs-lookup"><span data-stu-id="9f845-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f845-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9f845-107">Requirements</span></span>  
 <span data-ttu-id="9f845-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f845-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f845-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f845-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f845-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f845-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f845-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f845-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f845-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9f845-112">See also</span></span>

- [<span data-ttu-id="9f845-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9f845-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9f845-114">Метод RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="9f845-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
