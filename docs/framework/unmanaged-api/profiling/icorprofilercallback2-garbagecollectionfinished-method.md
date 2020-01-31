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
ms.openlocfilehash: 30f2e675532848c2dbb1f055a0f1489cf3b2baa1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865796"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="92561-102">Метод ICorProfilerCallback2::GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="92561-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="92561-103">Уведомляет профилировщик о завершении сборки мусора и выдает для него все обратные вызовы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="92561-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92561-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92561-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="92561-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="92561-105">Remarks</span></span>  
 <span data-ttu-id="92561-106">Профилировщик может быть защищен для проверки объектов в их конечном расположении при вызове метода `GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="92561-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92561-107">Требования</span><span class="sxs-lookup"><span data-stu-id="92561-107">Requirements</span></span>  
 <span data-ttu-id="92561-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92561-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92561-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92561-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92561-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92561-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92561-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92561-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92561-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="92561-112">See also</span></span>

- [<span data-ttu-id="92561-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="92561-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="92561-114">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="92561-114">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
