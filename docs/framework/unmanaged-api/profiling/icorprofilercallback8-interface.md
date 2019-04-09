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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125571"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="9694c-102">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="9694c-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="9694c-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="9694c-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="9694c-104">Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, среда CLR, используемый для уведомления профилировщика о началась и завершения JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="9694c-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="9694c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9694c-105">Methods</span></span>  
  
|<span data-ttu-id="9694c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9694c-106">Method</span></span>|<span data-ttu-id="9694c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9694c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9694c-108">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="9694c-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="9694c-109">Уведомляет профилировщик о начале JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="9694c-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="9694c-110">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="9694c-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="9694c-111">Уведомляет профилировщик об окончании JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="9694c-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9694c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9694c-112">Requirements</span></span>  
 <span data-ttu-id="9694c-113">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9694c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9694c-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9694c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
**<span data-ttu-id="9694c-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9694c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="9694c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9694c-116">See also</span></span>

- [<span data-ttu-id="9694c-117">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="9694c-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9694c-118">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="9694c-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
