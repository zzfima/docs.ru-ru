---
title: Метод ICorProfilerCallback::ThreadCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a26faf4f648107e7062a723663877b5b6a8e76e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497162"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="bc63a-102">Метод ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="bc63a-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="bc63a-103">Уведомляет профилировщик о том, что был создан поток.</span><span class="sxs-lookup"><span data-stu-id="bc63a-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc63a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc63a-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="bc63a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc63a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="bc63a-106">[in] Идентификатор потока, который был создан.</span><span class="sxs-lookup"><span data-stu-id="bc63a-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc63a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc63a-107">Remarks</span></span>  
 <span data-ttu-id="bc63a-108">`threadId` Значение немедленно допустимо.</span><span class="sxs-lookup"><span data-stu-id="bc63a-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc63a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bc63a-109">Requirements</span></span>  
 <span data-ttu-id="bc63a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc63a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc63a-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc63a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc63a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc63a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc63a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc63a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc63a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bc63a-114">See also</span></span>
- [<span data-ttu-id="bc63a-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="bc63a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bc63a-116">Метод ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="bc63a-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
