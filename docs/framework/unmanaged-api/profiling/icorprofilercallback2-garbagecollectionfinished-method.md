---
title: Метод ICorProfilerCallback2::GarbageCollectionFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231101"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="526e2-102">Метод ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="526e2-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="526e2-103">Уведомляет профилировщик, что для завершения сборки мусора, так и для всех обратных вызовов, выданные для него.</span><span class="sxs-lookup"><span data-stu-id="526e2-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526e2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="526e2-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="526e2-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="526e2-105">Remarks</span></span>  
 <span data-ttu-id="526e2-106">Безопасно для профилировщика для проверки объектов в соответствующих расположениях при `GarbageCollectionFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="526e2-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="526e2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="526e2-107">Requirements</span></span>  
 <span data-ttu-id="526e2-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="526e2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="526e2-109">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="526e2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="526e2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="526e2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="526e2-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="526e2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526e2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="526e2-112">See also</span></span>

- [<span data-ttu-id="526e2-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="526e2-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="526e2-114">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="526e2-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
