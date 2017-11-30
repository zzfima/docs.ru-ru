---
title: "Перечисление COR_PRF_HIGH_MONITOR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1df931796b32b6bea49e8b69da02d39e6a4803e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="ad907-102">Перечисление COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="ad907-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="ad907-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ad907-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ad907-104">Предоставляет флаги в дополнение к найденным в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления, которое профилировщик может указать в [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метода при его загрузке.</span><span class="sxs-lookup"><span data-stu-id="ad907-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad907-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad907-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES     = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED     = 0x00000002,     
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE       = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH      = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE           = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="ad907-106">Члены</span><span class="sxs-lookup"><span data-stu-id="ad907-106">Members</span></span>  
  
|<span data-ttu-id="ad907-107">Член</span><span class="sxs-lookup"><span data-stu-id="ad907-107">Member</span></span>|<span data-ttu-id="ad907-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ad907-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="ad907-109">Флаги не установлены.</span><span class="sxs-lookup"><span data-stu-id="ad907-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="ad907-110">Элементы управления [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратный вызов для добавления ссылок на сборку при обходе замыкания ссылки сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ad907-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="ad907-111">Элементы управления [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) обратный вызов для обновления поток символ, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="ad907-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="ad907-112">Представляет все флаги `COR_PRF_HIGH_MONITOR`, для которых необходимы улучшенные профилировщиком изображения.</span><span class="sxs-lookup"><span data-stu-id="ad907-112">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="ad907-113">Он соответствует `COR_PRF_REQUIRE_PROFILE_IMAGE` флаг в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="ad907-113">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="ad907-114">Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.</span><span class="sxs-lookup"><span data-stu-id="ad907-114">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="ad907-115">Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены только во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="ad907-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="ad907-116">Попытка изменить какой-нибудь из этих флагов в другом месте вызовет значение `HRESULT`, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="ad907-116">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad907-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad907-117">Remarks</span></span>  
 <span data-ttu-id="ad907-118">`COR_PRF_HIGH_MONITOR` Флаги используются с `pdwEventsHigh` параметр [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) и [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="ad907-118">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
 <span data-ttu-id="ad907-119">Начиная с [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], значение `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` изменения от 0 до `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="ad907-119">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad907-120">Требования</span><span class="sxs-lookup"><span data-stu-id="ad907-120">Requirements</span></span>  
 <span data-ttu-id="ad907-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad907-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad907-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad907-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad907-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad907-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad907-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad907-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad907-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ad907-125">See Also</span></span>  
 [<span data-ttu-id="ad907-126">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="ad907-126">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="ad907-127">Перечисление COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="ad907-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [<span data-ttu-id="ad907-128">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="ad907-128">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
