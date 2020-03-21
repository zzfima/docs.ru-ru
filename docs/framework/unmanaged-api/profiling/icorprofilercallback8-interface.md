---
title: Интерфейс ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175100"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="021d8-102">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="021d8-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="021d8-103">«Поддерживается в рамках .NET 4.7 и более поздних версиях»</span><span class="sxs-lookup"><span data-stu-id="021d8-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="021d8-104">Подкласс [ICorProfilerCallback7,](icorprofilercallback7-interface.md) который предоставляет методы обратного отработки, используемые общим временем выполнения языка, чтобы уведомить профайлера о том, что компиляция JIT динамического метода запущена и закончена.</span><span class="sxs-lookup"><span data-stu-id="021d8-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="021d8-105">Методы</span><span class="sxs-lookup"><span data-stu-id="021d8-105">Methods</span></span>  
  
|<span data-ttu-id="021d8-106">Метод</span><span class="sxs-lookup"><span data-stu-id="021d8-106">Method</span></span>|<span data-ttu-id="021d8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="021d8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="021d8-108">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="021d8-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="021d8-109">Уведомляет профайлера о том, что jIT начал компиляцию динамического метода.</span><span class="sxs-lookup"><span data-stu-id="021d8-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="021d8-110">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="021d8-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="021d8-111">Уведомляет профайлера о завершении компиляции динамического метода JIT.</span><span class="sxs-lookup"><span data-stu-id="021d8-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="021d8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="021d8-112">Requirements</span></span>  
 <span data-ttu-id="021d8-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="021d8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="021d8-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="021d8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="021d8-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="021d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="021d8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="021d8-116">See also</span></span>

- [<span data-ttu-id="021d8-117">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="021d8-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="021d8-118">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="021d8-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
