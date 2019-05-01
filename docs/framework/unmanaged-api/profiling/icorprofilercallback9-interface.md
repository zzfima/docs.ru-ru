---
title: Интерфейс ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991995"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="28e02-102">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="28e02-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="28e02-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="28e02-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="28e02-104">Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, среда CLR, используемый для уведомления профилировщика успешного мусора собираются и впоследствии выгружен динамического метода.</span><span class="sxs-lookup"><span data-stu-id="28e02-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28e02-105">Методы</span><span class="sxs-lookup"><span data-stu-id="28e02-105">Methods</span></span>  
  
|<span data-ttu-id="28e02-106">Метод</span><span class="sxs-lookup"><span data-stu-id="28e02-106">Method</span></span>|<span data-ttu-id="28e02-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28e02-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28e02-108">Метод DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="28e02-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="28e02-109">Уведомляет профилировщик о динамический метод сборки мусора, которые собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="28e02-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28e02-110">Требования</span><span class="sxs-lookup"><span data-stu-id="28e02-110">Requirements</span></span>  
 <span data-ttu-id="28e02-111">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e02-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e02-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28e02-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="28e02-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="28e02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="28e02-114">См. также</span><span class="sxs-lookup"><span data-stu-id="28e02-114">See also</span></span>

- [<span data-ttu-id="28e02-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="28e02-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="28e02-116">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="28e02-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="28e02-117">Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="28e02-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="28e02-118">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="28e02-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
