---
title: Метод ICorProfilerCallback2::FinalizeableObjectQueued
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dcfdb417cb43c819f21f66611129135ad0beb42b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746915"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="43154-102">Метод ICorProfilerCallback2::FinalizeableObjectQueued</span><span class="sxs-lookup"><span data-stu-id="43154-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="43154-103">Уведомляет профилировщик кода, что объект с финализатором поставлен поток метода завершения для выполнения его `Finalize` метод.</span><span class="sxs-lookup"><span data-stu-id="43154-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43154-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43154-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43154-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43154-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="43154-106">[in] Значение [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) перечисление, описывающее аспекты метода завершения.</span><span class="sxs-lookup"><span data-stu-id="43154-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="43154-107">[in] Идентификатор объекта, который находится в очереди.</span><span class="sxs-lookup"><span data-stu-id="43154-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43154-108">Требования</span><span class="sxs-lookup"><span data-stu-id="43154-108">Requirements</span></span>  
 <span data-ttu-id="43154-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43154-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43154-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43154-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43154-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43154-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43154-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43154-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43154-113">См. также</span><span class="sxs-lookup"><span data-stu-id="43154-113">See also</span></span>

- [<span data-ttu-id="43154-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="43154-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="43154-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="43154-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
