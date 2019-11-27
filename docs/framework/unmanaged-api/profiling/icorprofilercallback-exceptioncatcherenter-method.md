---
title: Метод ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 9c9cd0b042dc22f35c38e349ab8881dafc602731
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445018"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="a8bfa-102">Метод ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="a8bfa-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="a8bfa-103">Уведомляет профилировщик о том, что управление передается соответствующему блоку `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8bfa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8bfa-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a8bfa-106">окне Идентификатор функции, содержащей блок `catch`.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="a8bfa-107">окне Идентификатор обрабатываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8bfa-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a8bfa-108">Remarks</span></span>  
 <span data-ttu-id="a8bfa-109">Метод `ExceptionCatcherEnter` вызывается, только если точка перехвата находится в коде, скомпилированном в JIT-компиляторе.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="a8bfa-110">Исключение, перехваченное в неуправляемом коде или во внутреннем коде среды выполнения, не будет вызывать это уведомление.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="a8bfa-111">Значение `objectId` передается снова, так как сборщик мусора мог переместить объект с момента `ExceptionThrown` уведомления.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="a8bfa-112">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a8bfa-113">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a8bfa-114">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="a8bfa-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bfa-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a8bfa-115">Requirements</span></span>  
 <span data-ttu-id="a8bfa-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bfa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bfa-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8bfa-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8bfa-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8bfa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8bfa-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bfa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bfa-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a8bfa-120">See also</span></span>

- [<span data-ttu-id="a8bfa-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a8bfa-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a8bfa-122">Метод ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="a8bfa-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
