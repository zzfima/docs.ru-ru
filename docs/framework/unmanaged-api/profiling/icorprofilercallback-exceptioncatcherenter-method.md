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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450834"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="c78bf-102">Метод ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="c78bf-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="c78bf-103">Уведомляет профилировщик, управление передается соответствующему `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="c78bf-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c78bf-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c78bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c78bf-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c78bf-106">[in] Функция, содержащая идентификатор `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="c78bf-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="c78bf-107">[in] Идентификатор обрабатываемое исключение.</span><span class="sxs-lookup"><span data-stu-id="c78bf-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c78bf-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c78bf-108">Remarks</span></span>  
 <span data-ttu-id="c78bf-109">`ExceptionCatcherEnter` Метод вызывается только в том случае, если точка catch находится в коде, скомпилированном с помощью время JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="c78bf-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="c78bf-110">Исключение, которое будет перехвачено в неуправляемый код или во внутреннем коде среды выполнения не будет вызывать это уведомление.</span><span class="sxs-lookup"><span data-stu-id="c78bf-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="c78bf-111">`objectId` Значение передается еще раз с момента сбора мусора может перемещен объект с момента `ExceptionThrown` уведомления.</span><span class="sxs-lookup"><span data-stu-id="c78bf-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="c78bf-112">Профилировщик не должен блокироваться при реализации этого метода, так как стек может находиться в состоянии, допускающем сборку мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="c78bf-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c78bf-113">Если здесь профилировщик блокируется и выполняется сборка мусора, среда выполнения будет блокироваться до возвращает этот обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="c78bf-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c78bf-114">Реализация этого метода профилировщика не должны вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="c78bf-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78bf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c78bf-115">Requirements</span></span>  
 <span data-ttu-id="c78bf-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c78bf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c78bf-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c78bf-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c78bf-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c78bf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c78bf-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78bf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78bf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c78bf-120">See Also</span></span>  
 [<span data-ttu-id="c78bf-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c78bf-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c78bf-122">Метод ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="c78bf-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
