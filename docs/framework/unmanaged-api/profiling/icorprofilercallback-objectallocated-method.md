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
ms.openlocfilehash: 38d9e83e9fa0e9cd0586fb10a6fd79c29bead4a6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866108"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="be3fe-102">Метод ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="be3fe-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="be3fe-103">Уведомляет профилировщик о том, что для объекта выделена память в куче.</span><span class="sxs-lookup"><span data-stu-id="be3fe-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be3fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be3fe-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be3fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be3fe-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="be3fe-106">окне Идентификатор объекта, для которого была выделена память.</span><span class="sxs-lookup"><span data-stu-id="be3fe-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="be3fe-107">окне Идентификатор класса, экземпляр которого является объектом.</span><span class="sxs-lookup"><span data-stu-id="be3fe-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be3fe-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="be3fe-108">Remarks</span></span>  
 <span data-ttu-id="be3fe-109">Метод `ObjectedAllocated` не вызывается для выделений из стека или неуправляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="be3fe-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="be3fe-110">Параметр `classId` может ссылаться на класс в управляемом коде, который еще не был загружен.</span><span class="sxs-lookup"><span data-stu-id="be3fe-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="be3fe-111">Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="be3fe-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be3fe-112">Требования</span><span class="sxs-lookup"><span data-stu-id="be3fe-112">Requirements</span></span>  
 <span data-ttu-id="be3fe-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be3fe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be3fe-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be3fe-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be3fe-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be3fe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be3fe-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be3fe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be3fe-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="be3fe-117">See also</span></span>

- [<span data-ttu-id="be3fe-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="be3fe-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="be3fe-119">Метод ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="be3fe-119">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="be3fe-120">Метод ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="be3fe-120">ClassLoadFinished Method</span></span>](icorprofilercallback-classloadfinished-method.md)
