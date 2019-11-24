---
title: Метод ICorProfilerCallback::ExceptionCatcherLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: 7d61a6db8f42398a0d6e0d818605592f4fe71cf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445008"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="2f785-102">Метод ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="2f785-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="2f785-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span><span class="sxs-lookup"><span data-stu-id="2f785-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f785-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f785-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2f785-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="2f785-105">Remarks</span></span>  
 <span data-ttu-id="2f785-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="2f785-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="2f785-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="2f785-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="2f785-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="2f785-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f785-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2f785-109">Requirements</span></span>  
 <span data-ttu-id="2f785-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f785-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f785-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f785-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f785-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f785-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f785-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f785-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f785-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2f785-114">See also</span></span>

- [<span data-ttu-id="2f785-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2f785-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2f785-116">Метод ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="2f785-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
