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
ms.openlocfilehash: f5a4a6bc7b1e79068b11b099352cec64dd09f301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459457"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="6c46e-102">Метод ICorProfilerInfo4::InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="6c46e-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="6c46e-103">Инициализирует текущий поток до последующих вызовов API в том же потоке, поэтому можно избежать, взаимоблокировки профилировщика.</span><span class="sxs-lookup"><span data-stu-id="6c46e-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c46e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c46e-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6c46e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c46e-105">Remarks</span></span>  
 <span data-ttu-id="6c46e-106">Рекомендуется вызывать `InitializeCurrentThread` на любой поток, который будет вызывать профилировщик API, пока имеются приостановлена потоков.</span><span class="sxs-lookup"><span data-stu-id="6c46e-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="6c46e-107">Этот метод обычно используется профилировщиками выборки, которые создают свои собственные потока для вызова [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) способ выполнения стека проходит, когда целевой поток приостановлен.</span><span class="sxs-lookup"><span data-stu-id="6c46e-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="6c46e-108">Путем вызова `InitializeCurrentThread` после Когда профилировщик сначала создает поток выборки, профилировщики можно обеспечить инициализации отложенной потока, в противном случае среда CLR выполнит во время первого вызова `DoStackSnapshot` может теперь появляются безопасно при, отсутствие других потоков Приостановить.</span><span class="sxs-lookup"><span data-stu-id="6c46e-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c46e-109">`InitializeCurrentThread` производит инициализацию заранее, чтобы завершить задачи, которые принимают блокировок и может произойти взаимоблокировка.</span><span class="sxs-lookup"><span data-stu-id="6c46e-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="6c46e-110">Вызовите `InitializeCurrentThread` только в том случае, если нет приостановленных потоков.</span><span class="sxs-lookup"><span data-stu-id="6c46e-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c46e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6c46e-111">Requirements</span></span>  
 <span data-ttu-id="6c46e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c46e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c46e-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c46e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c46e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c46e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c46e-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c46e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c46e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6c46e-116">See Also</span></span>  
 [<span data-ttu-id="6c46e-117">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="6c46e-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="6c46e-118">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="6c46e-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6c46e-119">Профилирование</span><span class="sxs-lookup"><span data-stu-id="6c46e-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
