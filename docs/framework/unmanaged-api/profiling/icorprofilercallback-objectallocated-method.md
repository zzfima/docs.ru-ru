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
ms.openlocfilehash: e1c777a2512306c41413377530576fbe8ad8e7ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582295"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="0f851-102">Метод ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="0f851-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="0f851-103">Уведомляет профилировщик о том, что для объекта выделена память в куче.</span><span class="sxs-lookup"><span data-stu-id="0f851-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f851-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f851-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f851-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f851-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="0f851-106">[in] Идентификатор объекта, для которого была выделена память.</span><span class="sxs-lookup"><span data-stu-id="0f851-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="0f851-107">[in] Идентификатор класса, из которых объект является экземпляром.</span><span class="sxs-lookup"><span data-stu-id="0f851-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f851-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f851-108">Remarks</span></span>  
 <span data-ttu-id="0f851-109">`ObjectedAllocated` Метод не вызывается для выделений памяти из стека или неуправляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="0f851-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="0f851-110">`classId` Параметр можно ссылаться на класс в управляемом коде, который еще не загружена.</span><span class="sxs-lookup"><span data-stu-id="0f851-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="0f851-111">Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0f851-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f851-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0f851-112">Requirements</span></span>  
 <span data-ttu-id="0f851-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f851-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f851-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f851-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f851-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f851-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f851-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f851-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f851-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0f851-117">See also</span></span>
- [<span data-ttu-id="0f851-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0f851-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0f851-119">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="0f851-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="0f851-120">Метод ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="0f851-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
