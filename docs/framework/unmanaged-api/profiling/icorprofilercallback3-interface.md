---
title: Интерфейс ICorProfilerCallback3
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66e6a67ce022365fa8c9e1005dfecbe4b23abd10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158389"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="56e50-102">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="56e50-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="56e50-103">Предоставляет методы обратного вызова, среда CLR (CLR), используемые для связи, присоединение и отсоединение сведения о состоянии профилировщику.</span><span class="sxs-lookup"><span data-stu-id="56e50-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56e50-104">Методы</span><span class="sxs-lookup"><span data-stu-id="56e50-104">Methods</span></span>  
  
|<span data-ttu-id="56e50-105">Метод</span><span class="sxs-lookup"><span data-stu-id="56e50-105">Method</span></span>|<span data-ttu-id="56e50-106">Описание</span><span class="sxs-lookup"><span data-stu-id="56e50-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56e50-107">Метод InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="56e50-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="56e50-108">Вызывается средой CLR, чтобы предоставить профилировщику возможность инициализировать свое состояние после операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="56e50-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="56e50-109">Метод ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="56e50-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="56e50-110">Вызывается средой CLR, чтобы указать, что теперь профилировщик может вызывать дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="56e50-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="56e50-111">Метод ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="56e50-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="56e50-112">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="56e50-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56e50-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="56e50-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e50-114">Требования</span><span class="sxs-lookup"><span data-stu-id="56e50-114">Requirements</span></span>  
 <span data-ttu-id="56e50-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e50-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e50-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56e50-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56e50-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56e50-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="56e50-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56e50-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56e50-119">См. также</span><span class="sxs-lookup"><span data-stu-id="56e50-119">See also</span></span>

- [<span data-ttu-id="56e50-120">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="56e50-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="56e50-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="56e50-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="56e50-122">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="56e50-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="56e50-123">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="56e50-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
