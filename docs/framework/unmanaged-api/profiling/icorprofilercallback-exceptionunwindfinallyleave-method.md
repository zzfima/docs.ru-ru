---
title: "Метод ICorProfilerCallback::ExceptionUnwindFinallyLeave"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf373872ada8364fe755162597dc9baf5c527f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="9d914-102">Метод ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="9d914-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="9d914-103">Уведомляет профилировщик, фазы перемотки исключения покинул обработки `finally` предложения.</span><span class="sxs-lookup"><span data-stu-id="9d914-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d914-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d914-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9d914-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d914-105">Remarks</span></span>  
 <span data-ttu-id="9d914-106">Профилировщик не должен блокироваться во время данного вызова, так как стек может находиться в состоянии, допускающем сборку мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="9d914-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="9d914-107">При попытке здесь профилировщик блокируется и сбора мусора, среда выполнения будет блокироваться, пока не возвращает этот обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="9d914-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="9d914-108">Кроме того во время данного вызова профилировщик не должна вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="9d914-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d914-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9d914-109">Requirements</span></span>  
 <span data-ttu-id="9d914-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d914-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d914-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d914-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d914-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d914-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d914-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d914-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d914-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9d914-114">See Also</span></span>  
 [<span data-ttu-id="9d914-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9d914-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9d914-116">Метод ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="9d914-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
