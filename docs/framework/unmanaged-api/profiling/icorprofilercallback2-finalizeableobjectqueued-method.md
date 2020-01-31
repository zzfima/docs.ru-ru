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
ms.openlocfilehash: b9093f920a8c14247bc51471da3682c7e500afa4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865809"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="0fd7e-102">Метод ICorProfilerCallback2::FinalizeableObjectQueued</span><span class="sxs-lookup"><span data-stu-id="0fd7e-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="0fd7e-103">Уведомляет профилировщик кода о том, что объект с методом завершения был помещен в очередь в поток метода завершения для выполнения его `Finalize` метода.</span><span class="sxs-lookup"><span data-stu-id="0fd7e-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fd7e-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fd7e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fd7e-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="0fd7e-106">окне Значение перечисления [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) , описывающее аспекты метода завершения.</span><span class="sxs-lookup"><span data-stu-id="0fd7e-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="0fd7e-107">окне Идентификатор объекта, который был поставлен в очередь.</span><span class="sxs-lookup"><span data-stu-id="0fd7e-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fd7e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0fd7e-108">Requirements</span></span>  
 <span data-ttu-id="0fd7e-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fd7e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fd7e-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fd7e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fd7e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fd7e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fd7e-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fd7e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd7e-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="0fd7e-113">See also</span></span>

- [<span data-ttu-id="0fd7e-114">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0fd7e-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0fd7e-115">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="0fd7e-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
