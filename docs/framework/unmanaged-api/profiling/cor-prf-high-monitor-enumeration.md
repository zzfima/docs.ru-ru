---
title: Перечисление COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 72324fd434f3f37f723988345514c8aaada07ca9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867156"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="1bc2f-102">Перечисление COR_PRF_HIGH_MONITOR</span><span class="sxs-lookup"><span data-stu-id="1bc2f-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="1bc2f-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="1bc2f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="1bc2f-104">Предоставляет флаги в дополнение к тем, которые находятся в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) , которые профилировщик может указать в методе [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) при загрузке.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc2f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bc2f-105">Syntax</span></span>  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="1bc2f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="1bc2f-106">Members</span></span>  
  
|<span data-ttu-id="1bc2f-107">Член</span><span class="sxs-lookup"><span data-stu-id="1bc2f-107">Member</span></span>|<span data-ttu-id="1bc2f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1bc2f-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="1bc2f-109">Флаги не установлены.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="1bc2f-110">Управляет обратным вызовом [ICorProfilerCallback6:: жетассемблиреференце](icorprofilercallback6-getassemblyreferences-method.md) для добавления ссылок на сборки во время анализа закрытия ссылок на сборки CLR.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="1bc2f-111">Управляет обратным вызовом [ICorProfilerCallback7:: модулеинмеморисимболсупдатед](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) для обновлений потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="1bc2f-112">Управляет обратным вызовом [ICorProfilerCallback9::D инамикмесодунлоадед](icorprofilercallback9-dynamicmethodunloaded-method.md) для указания, когда динамический метод был собран и выгружен.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="1bc2f-113">Только .NET Core 3,0 и более поздние версии: отключает [многоуровневую компиляцию](../../../core/whats-new/dotnet-core-3-0.md) для профилировщиков.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="1bc2f-114">Только для .NET Core 3,0 и более поздних версий: предоставляет возможность использования упрощенного профилирования GC по сравнению с [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1bc2f-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="1bc2f-115">Управляет только обратными вызовами [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)и [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1bc2f-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="1bc2f-116">В отличие от флага `COR_PRF_MONITOR_GC`, `COR_PRF_HIGH_BASIC_GC` не отключает параллельную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="1bc2f-117">Только для .NET Core 3,0 и более поздних версий: включает обратные вызовы [MovedReferences](icorprofilercallback-movedreferences-method.md) и [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) для сжатия GC.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="1bc2f-118">.NET Core 3,0 и более поздние версии: аналогично [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), но предоставляет сведения о выделении объектов для кучи больших объектов (LOH).</span><span class="sxs-lookup"><span data-stu-id="1bc2f-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="1bc2f-119">Представляет все флаги `COR_PRF_HIGH_MONITOR`, для которых необходимы улучшенные профилировщиком изображения.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="1bc2f-120">Он соответствует флагу `COR_PRF_REQUIRE_PROFILE_IMAGE` в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1bc2f-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="1bc2f-121">Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="1bc2f-122">Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены только во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="1bc2f-123">Попытка изменить какой-нибудь из этих флагов в другом месте вызовет значение `HRESULT`, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bc2f-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="1bc2f-124">Remarks</span></span>

<span data-ttu-id="1bc2f-125">Флаги `COR_PRF_HIGH_MONITOR` используются с параметром `pdwEventsHigh` методов [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) и [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1bc2f-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="1bc2f-126">Начиная с .NET Framework 4.6.1 значение `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` изменилось с 0 на `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="1bc2f-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="1bc2f-127">Начиная с .NET Framework 4.7.2, его значение изменилось с `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` на `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="1bc2f-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` должен быть битовой маской, представляющей все флаги, которые могут быть установлены только во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="1bc2f-129">Попытка изменить любой из этих флагов в других случаях приведет к неудачной `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1bc2f-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1bc2f-130">Требования</span><span class="sxs-lookup"><span data-stu-id="1bc2f-130">Requirements</span></span>

<span data-ttu-id="1bc2f-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bc2f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="1bc2f-132">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1bc2f-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="1bc2f-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bc2f-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="1bc2f-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bc2f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc2f-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="1bc2f-135">See also</span></span>

- [<span data-ttu-id="1bc2f-136">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="1bc2f-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="1bc2f-137">Перечисление COR_PRF_MONITOR</span><span class="sxs-lookup"><span data-stu-id="1bc2f-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="1bc2f-138">Интерфейс ICorProfilerInfo5</span><span class="sxs-lookup"><span data-stu-id="1bc2f-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
