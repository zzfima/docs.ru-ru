---
title: 'ICorProfilerCallback9: метод:D Инамикмесодунлоадед'
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 05a788179ff40a6889ed613b5f8659dd3f8e066f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196322"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="a869b-102">ICorProfilerCallback9: метод:D Инамикмесодунлоадед</span><span class="sxs-lookup"><span data-stu-id="a869b-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="a869b-103">[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="a869b-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="a869b-104">Уведомляет профилировщик каждый раз, когда динамический метод уничтожается сборщиком мусора и затем выгружается.</span><span class="sxs-lookup"><span data-stu-id="a869b-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a869b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a869b-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a869b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a869b-106">Parameters</span></span>  
<span data-ttu-id="a869b-107">[входной] `functionId`</span><span class="sxs-lookup"><span data-stu-id="a869b-107">[in] `functionId`</span></span>  
<span data-ttu-id="a869b-108">Идентификатор функции в памяти, которая была собрана и выгружена сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="a869b-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="a869b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a869b-109">Requirements</span></span>  
 <span data-ttu-id="a869b-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a869b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a869b-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a869b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a869b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a869b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a869b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a869b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a869b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a869b-114">See also</span></span>

- [<span data-ttu-id="a869b-115">ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод</span><span class="sxs-lookup"><span data-stu-id="a869b-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="a869b-116">ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод</span><span class="sxs-lookup"><span data-stu-id="a869b-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="a869b-117">Интерфейс ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="a869b-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="a869b-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="a869b-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
