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
ms.openlocfilehash: ad9c5445cbef0be7919570db64b027556d923752
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865575"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="e3278-102">Интерфейс ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="e3278-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="e3278-103">Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о состоянии подключения и отсоединения профилировщику.</span><span class="sxs-lookup"><span data-stu-id="e3278-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3278-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e3278-104">Methods</span></span>  
  
|<span data-ttu-id="e3278-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e3278-105">Method</span></span>|<span data-ttu-id="e3278-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e3278-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3278-107">Метод InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="e3278-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="e3278-108">Вызывается средой CLR, чтобы предоставить профилировщику возможность инициализировать свое состояние после операции присоединения.</span><span class="sxs-lookup"><span data-stu-id="e3278-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="e3278-109">Метод ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="e3278-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="e3278-110">Вызывается средой CLR для указания на то, что профилировщик теперь может вызывать методы перехвата.</span><span class="sxs-lookup"><span data-stu-id="e3278-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="e3278-111">Метод ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="e3278-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="e3278-112">Уведомляет профилировщик о том, что среда CLR намерена выгрузить библиотеку DLL профилировщика.</span><span class="sxs-lookup"><span data-stu-id="e3278-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3278-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="e3278-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3278-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e3278-114">Requirements</span></span>  
 <span data-ttu-id="e3278-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3278-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3278-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3278-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3278-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3278-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3278-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3278-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3278-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3278-119">See also</span></span>

- [<span data-ttu-id="e3278-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="e3278-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e3278-121">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e3278-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e3278-122">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="e3278-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="e3278-123">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="e3278-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
