---
title: Метод ICorProfilerCallback9::DynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452407"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="72d4c-102">Метод ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="72d4c-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="72d4c-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="72d4c-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="72d4c-104">Уведомляет профилировщик, каждый раз, когда динамический метод является мусором, собираются и впоследствии выгружен.</span><span class="sxs-lookup"><span data-stu-id="72d4c-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d4c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72d4c-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72d4c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="72d4c-106">Parameters</span></span>  
<span data-ttu-id="72d4c-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="72d4c-107">[in] `functionId`</span></span>  
<span data-ttu-id="72d4c-108">Идентификатор функции в памяти, которая была мусора собираются и выгрузки.</span><span class="sxs-lookup"><span data-stu-id="72d4c-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="72d4c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="72d4c-109">Requirements</span></span>  
 <span data-ttu-id="72d4c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d4c-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72d4c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72d4c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72d4c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72d4c-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="72d4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d4c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="72d4c-114">See Also</span></span>  
[<span data-ttu-id="72d4c-115">Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="72d4c-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="72d4c-116">Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="72d4c-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="72d4c-117">[Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="72d4c-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="72d4c-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="72d4c-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
