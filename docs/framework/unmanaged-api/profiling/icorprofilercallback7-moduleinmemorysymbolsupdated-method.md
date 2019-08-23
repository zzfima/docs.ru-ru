---
title: 'Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 860ecde22dead112a42b6ac868e34f0e9cd3531d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916197"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="7c9ff-102">Метод ICorProfilerCallback7:: Модулеинмеморисимболсупдатед</span><span class="sxs-lookup"><span data-stu-id="7c9ff-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="7c9ff-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="7c9ff-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7c9ff-104">Уведомляет профилировщик каждый раз, когда поток символов, связанный с модулем в памяти, обновляется.</span><span class="sxs-lookup"><span data-stu-id="7c9ff-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9ff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c9ff-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c9ff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c9ff-106">Parameters</span></span>  
 <span data-ttu-id="7c9ff-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="7c9ff-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="7c9ff-108">Идентификатор модуля в памяти, чей поток символов обновлен.</span><span class="sxs-lookup"><span data-stu-id="7c9ff-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c9ff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c9ff-109">Remarks</span></span>  
 <span data-ttu-id="7c9ff-110">Этот обратный вызов контролируется путем установки флага маски событий [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) при вызове метода [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7c9ff-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c9ff-111">Это событие в данный момент не вызывается для неявного создания или <xref:System.Reflection.Emit> изменения символов через API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="7c9ff-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="7c9ff-112">Даже если символы предоставляются перед вызовом одной из перегрузок управляемых <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> методов, которые `rawSymbolStore` включают аргумент для указания символов для сборки, среда выполнения может не связать символьные данные с модулем. до появления обратного вызова [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7c9ff-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="7c9ff-113">Это событие предоставляет более позднюю возможность собираются символы для таких модулей.</span><span class="sxs-lookup"><span data-stu-id="7c9ff-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c9ff-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7c9ff-114">Requirements</span></span>  
 <span data-ttu-id="7c9ff-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c9ff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c9ff-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="7c9ff-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c9ff-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="7c9ff-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c9ff-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c9ff-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9ff-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7c9ff-119">See also</span></span>

- [<span data-ttu-id="7c9ff-120">Метод ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="7c9ff-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="7c9ff-121">Метод SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="7c9ff-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="7c9ff-122">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="7c9ff-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
