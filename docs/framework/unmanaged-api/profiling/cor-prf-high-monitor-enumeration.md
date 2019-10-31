---
title: Перечисление COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 03fa33e0e2b4175d9f82bc6021731d58805da258
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123985"
---
# <a name="cor_prf_high_monitor-enumeration"></a>Перечисление COR_PRF_HIGH_MONITOR
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет флаги в дополнение к тем, которые находятся в перечислении [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) , которые профилировщик может указать в методе [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) при загрузке.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Флаги не установлены.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Управляет обратным вызовом [ICorProfilerCallback6:: жетассемблиреференце](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) для добавления ссылок на сборки во время анализа закрытия ссылок на сборки CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Управляет обратным вызовом [ICorProfilerCallback7:: модулеинмеморисимболсупдатед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) для обновлений потока символов, связанного с модулем в памяти.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Управляет обратным вызовом [ICorProfilerCallback9::D инамикмесодунлоадед](icorprofilercallback9-dynamicmethodunloaded-method.md) для указания, когда динамический метод был собран и выгружен. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|Только .NET Core 3,0 и более поздние версии: отключает [многоуровневую компиляцию](../../../core/whats-new/dotnet-core-3-0.md) для профилировщиков.|
|`COR_PRF_HIGH_BASIC_GC`|Только для .NET Core 3,0 и более поздних версий: предоставляет возможность использования упрощенного профилирования GC по сравнению с [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md). Управляет только обратными вызовами [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)и [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) . В отличие от флага `COR_PRF_MONITOR_GC`, `COR_PRF_HIGH_BASIC_GC` не отключает параллельную сборку мусора.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|Только для .NET Core 3,0 и более поздних версий: включает обратные вызовы [MovedReferences](icorprofilercallback-movedreferences-method.md) и [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) для сжатия GC.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3,0 и более поздние версии: аналогично [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), но предоставляет сведения о выделении объектов для кучи больших объектов (LOH).|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, для которых необходимы улучшенные профилировщиком изображения. Он соответствует флагу `COR_PRF_REQUIRE_PROFILE_IMAGE` в перечислении [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены только во время инициализации. Попытка изменить какой-нибудь из этих флагов в другом месте вызовет значение `HRESULT`, указывающее на сбой.|  
  
## <a name="remarks"></a>Заметки  
 Флаги `COR_PRF_HIGH_MONITOR` используются с параметром `pdwEventsHigh` методов [ICorProfilerInfo5:: GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) и [ICorProfilerInfo5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .  
  
Начиная с .NET Framework 4.6.1 значение `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` изменилось с 0 на `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). Начиная с .NET Framework 4.7.2, его значение изменилось с `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` на `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` должен быть битовой маской, представляющей все флаги, которые могут быть установлены только во время инициализации. Попытка изменить любой из этих флагов в других случаях приведет к неудачной `HRESULT`.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Перечисление COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [Интерфейс ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
