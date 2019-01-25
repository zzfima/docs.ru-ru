---
title: Метод ICorProfilerCallback::ExceptionThrown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aec3ddc8b2a0fd527a5cf9b48286f0e8bca14636
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618991"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="be10d-102">Метод ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="be10d-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="be10d-103">Уведомляет профилировщик, что возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="be10d-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be10d-104">Эта функция вызывается только в том случае, если исключение достигнет управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="be10d-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be10d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be10d-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be10d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="be10d-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="be10d-107">[in] Идентификатор объекта, вызвавшего исключение.</span><span class="sxs-lookup"><span data-stu-id="be10d-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be10d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="be10d-108">Remarks</span></span>  
 <span data-ttu-id="be10d-109">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="be10d-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="be10d-110">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="be10d-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="be10d-111">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="be10d-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be10d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="be10d-112">Requirements</span></span>  
 <span data-ttu-id="be10d-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be10d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be10d-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be10d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be10d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be10d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be10d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be10d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be10d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="be10d-117">See also</span></span>
- [<span data-ttu-id="be10d-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="be10d-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
