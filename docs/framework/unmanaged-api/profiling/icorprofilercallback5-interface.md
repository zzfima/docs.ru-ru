---
title: Интерфейс ICorProfilerCallback5
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: ce34d43091cdee0bca88f94711e49072fa4fd08c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430065"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="8ac2b-102">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="8ac2b-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="8ac2b-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="8ac2b-104">Для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти должен реализовать `ICorProfilerCallback5`.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ac2b-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="8ac2b-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ac2b-106">Методы</span><span class="sxs-lookup"><span data-stu-id="8ac2b-106">Methods</span></span>  
  
|<span data-ttu-id="8ac2b-107">Метод</span><span class="sxs-lookup"><span data-stu-id="8ac2b-107">Method</span></span>|<span data-ttu-id="8ac2b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8ac2b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ac2b-109">Метод ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="8ac2b-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="8ac2b-110">Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="8ac2b-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ac2b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8ac2b-111">Requirements</span></span>  
 <span data-ttu-id="8ac2b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ac2b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac2b-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ac2b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ac2b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac2b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac2b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8ac2b-115">See also</span></span>

- [<span data-ttu-id="8ac2b-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="8ac2b-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="8ac2b-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="8ac2b-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
