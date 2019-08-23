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
ms.openlocfilehash: 01e407b726ce4426f3b58bc29854b30bd6add257
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953873"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="e0970-102">Метод ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="e0970-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="e0970-103">Уведомляет профилировщик о том, что было создано исключение.</span><span class="sxs-lookup"><span data-stu-id="e0970-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0970-104">Эта функция вызывается, только если исключение достигает управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e0970-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0970-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0970-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0970-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0970-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="e0970-107">окне Идентификатор объекта, который вызвал исключение.</span><span class="sxs-lookup"><span data-stu-id="e0970-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0970-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0970-108">Remarks</span></span>  
 <span data-ttu-id="e0970-109">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="e0970-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e0970-110">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="e0970-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e0970-111">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="e0970-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0970-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e0970-112">Requirements</span></span>  
 <span data-ttu-id="e0970-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0970-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0970-114">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="e0970-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0970-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="e0970-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0970-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0970-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0970-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e0970-117">See also</span></span>

- [<span data-ttu-id="e0970-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e0970-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
