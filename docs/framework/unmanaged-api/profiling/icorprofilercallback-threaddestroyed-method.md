---
title: Метод ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 35b87b3a2c0230b26fb68af44dc1aa864a6449e0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439938"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="22d03-102">Метод ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="22d03-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="22d03-103">Notifies the profiler that a thread has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="22d03-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22d03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22d03-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22d03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22d03-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="22d03-106">[in] The ID of the thread that has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="22d03-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22d03-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="22d03-107">Remarks</span></span>  
 <span data-ttu-id="22d03-108">The `threadId` value is no longer valid at the time of this call.</span><span class="sxs-lookup"><span data-stu-id="22d03-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d03-109">Требования</span><span class="sxs-lookup"><span data-stu-id="22d03-109">Requirements</span></span>  
 <span data-ttu-id="22d03-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22d03-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d03-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22d03-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="22d03-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22d03-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22d03-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d03-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d03-114">См. также</span><span class="sxs-lookup"><span data-stu-id="22d03-114">See also</span></span>

- [<span data-ttu-id="22d03-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="22d03-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="22d03-116">Метод ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="22d03-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
