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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136568"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="940e7-102">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="940e7-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="940e7-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="940e7-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="940e7-104">Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод был собран в мусор и затем выгружен.</span><span class="sxs-lookup"><span data-stu-id="940e7-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="940e7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="940e7-105">Methods</span></span>  
  
|<span data-ttu-id="940e7-106">Метод</span><span class="sxs-lookup"><span data-stu-id="940e7-106">Method</span></span>|<span data-ttu-id="940e7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="940e7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="940e7-108">Метод DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="940e7-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="940e7-109">Уведомляет профилировщик о том, что динамический метод был собран в мусор и затем выгружен.</span><span class="sxs-lookup"><span data-stu-id="940e7-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="940e7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="940e7-110">Requirements</span></span>  
 <span data-ttu-id="940e7-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="940e7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="940e7-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="940e7-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="940e7-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="940e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="940e7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="940e7-114">See also</span></span>

- [<span data-ttu-id="940e7-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="940e7-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="940e7-116">Интерфейс ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="940e7-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="940e7-117">ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод</span><span class="sxs-lookup"><span data-stu-id="940e7-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="940e7-118">ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод</span><span class="sxs-lookup"><span data-stu-id="940e7-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
