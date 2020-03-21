---
title: Перечисление COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175217"
---
# <a name="cor_prf_high_monitor-enumeration"></a>Перечисление COR_PRF_HIGH_MONITOR

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
Предоставляет флаги в дополнение к тем, которые находятся в [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) перечислении, которые профайлер может указать на [метод ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) метод при загрузке.  
  
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
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Флаги не установлены.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Контролирует [ICorProfilerCallback6::GetAssemblyReference обратный](icorprofilercallback6-getassemblyreferences-method.md) вызов для добавления ссылок на сборку во время прогулки по закрытию ссылки на сборку CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Управляет [ICorProfilerCallback7::ModuleInMemoryСимволыОбновленный](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) обратный вызов для обновления потока символов, связанных с модулем в памяти.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Контролирует [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) обратный вызов для указания, когда динамический метод был собран и выгружен. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|.NET Core 3.0 и только более поздние версии: [Уровень разъяснений](../../../core/whats-new/dotnet-core-3-0.md) для профилировщиков.|
|`COR_PRF_HIGH_BASIC_GC`|.NET Core 3.0 и только более поздние версии: обеспечивает легкий вариант профилирования GC по сравнению [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md)с . Контролирует только [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), и [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) обратных вызовов. В `COR_PRF_MONITOR_GC` отличие `COR_PRF_HIGH_BASIC_GC` от флага, не отменяет параллельный сбор мусора.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|.NET Core 3.0 и только более поздние версии: Включает в себя [передвижныессылки](icorprofilercallback-movedreferences-method.md) и [перемещенныеобратные обратные вызовы](icorprofilercallback4-movedreferences2-method.md) только для уплотнения GCs.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|.NET Core 3.0 и только [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)более поздние версии: Похожи ена, но предоставляет информацию о распределении объектов только для большой объектной кучи (LOH).|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, для которых необходимы улучшенные профилировщиком изображения. Это соответствует флагу `COR_PRF_REQUIRE_PROFILE_IMAGE` в [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) перечислении.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены только во время инициализации. Попытка изменить какой-нибудь из этих флагов в другом месте вызовет значение `HRESULT`, указывающее на сбой.|  
  
## <a name="remarks"></a>Remarks

Флаги `COR_PRF_HIGH_MONITOR` используются `pdwEventsHigh` по параметру методов [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) и [ICorProfilerInfo5::SetEventMask2.](icorprofilerinfo5-seteventmask2-method.md)  
  
Начиная с .NET Framework 4.6.1, `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` значение измененного `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` от 0 до (0x0000000002). Начиная с .NET Framework 4.7.2, `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` его `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`значение изменилось с .

`COR_PRF_HIGH_MONITOR_IMMUTABLE`предназначен для битной маски, которая представляет все флаги, которые могут быть установлены только во время инициализации. Попытка изменить любой из этих флагов `HRESULT`в другом месте приводит к неудаче .

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
**Заголовок:** CorProf.idl, CorProf.h  
  
**Библиотека:** CorGuids.lib  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления профилирования](profiling-enumerations.md)
- [Перечисление COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)
- [Интерфейс ICorProfilerInfo5](icorprofilerinfo5-interface.md)
