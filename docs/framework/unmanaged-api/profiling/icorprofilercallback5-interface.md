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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 114d97e02b0a6b80c46f971ed74a24dc3c397f1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072653"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="c4d5f-102">Интерфейс ICorProfilerCallback5</span><span class="sxs-lookup"><span data-stu-id="c4d5f-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="c4d5f-103">Дополняет информацию, чтобы помочь профилировщику идентифицировать полное замыкание используемых объектов, при использовании либо [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) или [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)метод вместе с [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) и [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="c4d5f-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 `ICorProfilerCallback5` <span data-ttu-id="c4d5f-104">должен быть реализован для подписки на уведомления, связанные с зависимыми дескрипторами профилировщик управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="c4d5f-104">must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4d5f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4d5f-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4d5f-106">Методы</span><span class="sxs-lookup"><span data-stu-id="c4d5f-106">Methods</span></span>  
  
|<span data-ttu-id="c4d5f-107">Метод</span><span class="sxs-lookup"><span data-stu-id="c4d5f-107">Method</span></span>|<span data-ttu-id="c4d5f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c4d5f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4d5f-109">Метод ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="c4d5f-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="c4d5f-110">Идентифицирует транзитивное замыкание объектов, на которые ссылаются эти корневые элементы как через прямые ссылки на поля члена, так и через зависимости `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="c4d5f-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4d5f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c4d5f-111">Requirements</span></span>  
 <span data-ttu-id="c4d5f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4d5f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4d5f-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4d5f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="c4d5f-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c4d5f-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4d5f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c4d5f-115">See also</span></span>

- [<span data-ttu-id="c4d5f-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="c4d5f-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c4d5f-117">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="c4d5f-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
