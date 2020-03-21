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
ms.openlocfilehash: 7fb58c0eb2446253bd658434fc9d68bb857fe0e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175126"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="f257b-102">Метод ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f257b-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="f257b-103">Уведомляет профайлера о том, что поток был создан.</span><span class="sxs-lookup"><span data-stu-id="f257b-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f257b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f257b-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="f257b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f257b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f257b-106">(в) Идентификатор созданного потока.</span><span class="sxs-lookup"><span data-stu-id="f257b-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f257b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f257b-107">Remarks</span></span>  
 <span data-ttu-id="f257b-108">Значение `threadId` немедленно действительно.</span><span class="sxs-lookup"><span data-stu-id="f257b-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f257b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f257b-109">Requirements</span></span>  
 <span data-ttu-id="f257b-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f257b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f257b-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f257b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f257b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f257b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f257b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f257b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f257b-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f257b-114">See also</span></span>

- [<span data-ttu-id="f257b-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f257b-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f257b-116">Метод ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="f257b-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
