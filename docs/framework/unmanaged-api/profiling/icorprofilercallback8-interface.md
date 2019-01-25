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
ms.openlocfilehash: a3bdf79582619777a22c80caac5b4e90d603f3a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675019"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="b1da0-102">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="b1da0-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="b1da0-103">[Поддерживается в .NET Framework 4.7 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="b1da0-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="b1da0-104">Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, среда CLR, используемый для уведомления профилировщика о началась и завершения JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="b1da0-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="b1da0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="b1da0-105">Methods</span></span>  
  
|<span data-ttu-id="b1da0-106">Метод</span><span class="sxs-lookup"><span data-stu-id="b1da0-106">Method</span></span>|<span data-ttu-id="b1da0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b1da0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1da0-108">Метод DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="b1da0-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="b1da0-109">Уведомляет профилировщик о начале JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="b1da0-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="b1da0-110">Метод DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="b1da0-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="b1da0-111">Уведомляет профилировщик об окончании JIT-компиляция динамического метода.</span><span class="sxs-lookup"><span data-stu-id="b1da0-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1da0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b1da0-112">Requirements</span></span>  
 <span data-ttu-id="b1da0-113">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1da0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1da0-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1da0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="b1da0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b1da0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b1da0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b1da0-116">See also</span></span>
- [<span data-ttu-id="b1da0-117">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b1da0-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b1da0-118">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="b1da0-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
