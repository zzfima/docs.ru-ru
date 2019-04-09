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
ms.openlocfilehash: a9b47e1d1bfa1d8f6c970e95fe25f62a690d3b91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143875"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="37cbb-102">Метод ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="37cbb-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="37cbb-103">Уведомляет профилировщик, что управление передается соответствующему блоку `catch`.</span><span class="sxs-lookup"><span data-stu-id="37cbb-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37cbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37cbb-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37cbb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37cbb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="37cbb-106">[in] Функция, содержащая идентификатор `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="37cbb-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="37cbb-107">[in] Идентификатор обрабатываемое исключение.</span><span class="sxs-lookup"><span data-stu-id="37cbb-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37cbb-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="37cbb-108">Remarks</span></span>  
 <span data-ttu-id="37cbb-109">`ExceptionCatcherEnter` Метод вызывается только в том случае, если точка catch находится в коде, скомпилированном с помощью компилятора just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="37cbb-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="37cbb-110">Это уведомление не вызывает исключения, перехваченные в неуправляемом коде, или во внутреннем коде среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="37cbb-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="37cbb-111">`objectId` Значение передается снова, поскольку сбор мусора может перемещена объекта с момента `ExceptionThrown` уведомлений.</span><span class="sxs-lookup"><span data-stu-id="37cbb-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="37cbb-112">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="37cbb-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="37cbb-113">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="37cbb-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="37cbb-114">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="37cbb-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37cbb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="37cbb-115">Requirements</span></span>  
 <span data-ttu-id="37cbb-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37cbb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37cbb-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37cbb-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37cbb-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37cbb-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="37cbb-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="37cbb-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37cbb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="37cbb-120">See also</span></span>

- [<span data-ttu-id="37cbb-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="37cbb-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="37cbb-122">Метод ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="37cbb-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
