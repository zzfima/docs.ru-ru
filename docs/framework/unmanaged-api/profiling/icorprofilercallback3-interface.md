---
title: "Интерфейс ICorProfilerCallback3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3
helpviewer_keywords: ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c62dfb9b44999309ab2be7dfdcdfba3bb5dde29c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="30cea-102">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="30cea-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="30cea-103">Предоставляет методы обратного вызова общеязыковой среды выполнения (CLR), используемые для связи, присоединение и отсоединение профилировщику сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="30cea-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30cea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="30cea-104">Methods</span></span>  
  
|<span data-ttu-id="30cea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="30cea-105">Method</span></span>|<span data-ttu-id="30cea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="30cea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30cea-107">Метод InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="30cea-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="30cea-108">Вызывается средой CLR, чтобы предоставить профилировщику возможность инициализировать свое состояние после операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="30cea-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="30cea-109">Метод ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="30cea-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="30cea-110">Вызывается средой CLR, чтобы указать, что теперь профилировщик может вызывать дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="30cea-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="30cea-111">Метод ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="30cea-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="30cea-112">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="30cea-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30cea-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="30cea-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30cea-114">Требования</span><span class="sxs-lookup"><span data-stu-id="30cea-114">Requirements</span></span>  
 <span data-ttu-id="30cea-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30cea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30cea-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30cea-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30cea-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30cea-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30cea-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30cea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30cea-119">См. также</span><span class="sxs-lookup"><span data-stu-id="30cea-119">See Also</span></span>  
 [<span data-ttu-id="30cea-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="30cea-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="30cea-121">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="30cea-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="30cea-122">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="30cea-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="30cea-123">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="30cea-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
