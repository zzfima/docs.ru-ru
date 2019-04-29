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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598887"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="7c5ff-102">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="7c5ff-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="7c5ff-103">Предоставляет методы обратного вызова, среда CLR (CLR), используемые для связи, присоединение и отсоединение сведения о состоянии профилировщику.</span><span class="sxs-lookup"><span data-stu-id="7c5ff-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c5ff-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7c5ff-104">Methods</span></span>  
  
|<span data-ttu-id="7c5ff-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7c5ff-105">Method</span></span>|<span data-ttu-id="7c5ff-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7c5ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c5ff-107">Метод InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="7c5ff-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="7c5ff-108">Вызывается средой CLR, чтобы предоставить профилировщику возможность инициализировать свое состояние после операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="7c5ff-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="7c5ff-109">Метод ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="7c5ff-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="7c5ff-110">Вызывается средой CLR, чтобы указать, что теперь профилировщик может вызывать дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="7c5ff-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="7c5ff-111">Метод ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="7c5ff-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="7c5ff-112">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="7c5ff-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c5ff-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c5ff-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c5ff-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7c5ff-114">Requirements</span></span>  
 <span data-ttu-id="7c5ff-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c5ff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c5ff-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c5ff-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c5ff-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c5ff-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c5ff-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c5ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5ff-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7c5ff-119">See also</span></span>

- [<span data-ttu-id="7c5ff-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="7c5ff-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="7c5ff-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7c5ff-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="7c5ff-122">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7c5ff-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="7c5ff-123">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="7c5ff-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
