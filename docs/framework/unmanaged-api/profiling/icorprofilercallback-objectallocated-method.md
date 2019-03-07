---
title: Метод ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0deadc3783663fe595d8217a167d18e6916c6be9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466002"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="fb605-102">Метод ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="fb605-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="fb605-103">Уведомляет профилировщик о том, что для объекта выделена память в куче.</span><span class="sxs-lookup"><span data-stu-id="fb605-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb605-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb605-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb605-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb605-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="fb605-106">[in] Идентификатор объекта, для которого была выделена память.</span><span class="sxs-lookup"><span data-stu-id="fb605-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="fb605-107">[in] Идентификатор класса, из которых объект является экземпляром.</span><span class="sxs-lookup"><span data-stu-id="fb605-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb605-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb605-108">Remarks</span></span>  
 <span data-ttu-id="fb605-109">`ObjectedAllocated` Метод не вызывается для выделений памяти из стека или неуправляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="fb605-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="fb605-110">`classId` Параметр можно ссылаться на класс в управляемом коде, который еще не загружена.</span><span class="sxs-lookup"><span data-stu-id="fb605-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="fb605-111">Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="fb605-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb605-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fb605-112">Requirements</span></span>  
 <span data-ttu-id="fb605-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb605-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb605-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb605-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb605-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb605-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb605-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb605-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb605-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fb605-117">See also</span></span>
- [<span data-ttu-id="fb605-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fb605-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fb605-119">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="fb605-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="fb605-120">Метод ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="fb605-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
