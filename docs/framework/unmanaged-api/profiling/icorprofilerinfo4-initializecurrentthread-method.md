---
title: Метод ICorProfilerInfo4::InitializeCurrentThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 990ae316a780af9be96f6b91900f33cbb2db4f36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727980"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="90183-102">Метод ICorProfilerInfo4::InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="90183-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="90183-103">Инициализирует текущий поток до последующих вызовов API в одном потоке, поэтому можно избежать этой взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="90183-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90183-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90183-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="90183-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="90183-105">Remarks</span></span>  
 <span data-ttu-id="90183-106">Мы рекомендуем вызывать `InitializeCurrentThread` в любом потоке, который будет вызывать профилировщик API, несмотря на наличие приостановки потоков.</span><span class="sxs-lookup"><span data-stu-id="90183-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="90183-107">Этот метод обычно используется выборочными профилировщиками, которые создают собственные потоку на вызов метода [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) способ выполнения стека проходит, когда целевой поток приостановлен.</span><span class="sxs-lookup"><span data-stu-id="90183-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="90183-108">Путем вызова `InitializeCurrentThread` после Когда профилировщик сначала создает поток выборки, средства профилирования можно обеспечить инициализации отложенной поток, в противном случае среда CLR выполнит во время первого вызова `DoStackSnapshot` теперь можно выполнять безопасно когда нет других потоков, Состояние приостановки.</span><span class="sxs-lookup"><span data-stu-id="90183-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90183-109">`InitializeCurrentThread` производит инициализацию заранее, чтобы завершить задачи, которые принимают блокировок и может принимать участие во взаимоблокировке.</span><span class="sxs-lookup"><span data-stu-id="90183-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="90183-110">Вызовите `InitializeCurrentThread` только в том случае, если нет приостановленных потоков.</span><span class="sxs-lookup"><span data-stu-id="90183-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90183-111">Требования</span><span class="sxs-lookup"><span data-stu-id="90183-111">Requirements</span></span>  
 <span data-ttu-id="90183-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90183-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90183-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90183-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90183-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90183-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90183-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90183-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90183-116">См. также</span><span class="sxs-lookup"><span data-stu-id="90183-116">See also</span></span>
- [<span data-ttu-id="90183-117">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="90183-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="90183-118">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="90183-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="90183-119">Профилирование</span><span class="sxs-lookup"><span data-stu-id="90183-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
