---
title: ICorProfilerCallback9::DynamicMethodUnloaded Метод
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177037"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="59836-102">ICorProfilerCallback9::DynamicMethodUnloaded Метод</span><span class="sxs-lookup"><span data-stu-id="59836-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="59836-103">«Поддерживается в рамках .NET 4.7.2 и более поздних версиях»</span><span class="sxs-lookup"><span data-stu-id="59836-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="59836-104">Уведомляет профайлера всякий раз, когда динамический метод собирается и впоследствии выгружается.</span><span class="sxs-lookup"><span data-stu-id="59836-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59836-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59836-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59836-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="59836-106">Parameters</span></span>  
<span data-ttu-id="59836-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="59836-107">[in] `functionId`</span></span>  
<span data-ttu-id="59836-108">Идентификатор функции в памяти, которая была собрана и выгружена.</span><span class="sxs-lookup"><span data-stu-id="59836-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="59836-109">Требования</span><span class="sxs-lookup"><span data-stu-id="59836-109">Requirements</span></span>  
 <span data-ttu-id="59836-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59836-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59836-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59836-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59836-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59836-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59836-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59836-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59836-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59836-114">See also</span></span>

- [<span data-ttu-id="59836-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Метод</span><span class="sxs-lookup"><span data-stu-id="59836-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="59836-116">ICorProfilerCallback8.DynamicMethodJITCompil</span><span class="sxs-lookup"><span data-stu-id="59836-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="59836-117">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="59836-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="59836-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="59836-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
