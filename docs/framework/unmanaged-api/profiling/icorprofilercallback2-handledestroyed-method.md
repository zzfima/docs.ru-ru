---
title: Метод ICorProfilerCallback2::HandleDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
ms.openlocfilehash: 2ad1eb765c435244389a671c74026539fa3590cf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439757"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="ce098-102">Метод ICorProfilerCallback2::HandleDestroyed</span><span class="sxs-lookup"><span data-stu-id="ce098-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="ce098-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="ce098-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce098-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce098-104">Syntax</span></span>  
  
```cpp  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce098-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce098-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="ce098-106">[in] The ID of the handle for the garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ce098-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce098-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ce098-107">Requirements</span></span>  
 <span data-ttu-id="ce098-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce098-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce098-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ce098-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ce098-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce098-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce098-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce098-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce098-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ce098-112">See also</span></span>

- [<span data-ttu-id="ce098-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ce098-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ce098-114">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="ce098-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
