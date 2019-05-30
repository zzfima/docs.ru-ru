---
title: Перечисление COR_PRF_HIGH_MONITOR
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e365dff7c56ddca1d05f2e16605078ef46e4e2af
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251156"
---
# <a name="corprfhighmonitor-enumeration"></a>Перечисление COR_PRF_HIGH_MONITOR
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Предоставляет флаги в дополнение к найденным в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления, которое профилировщик может указать [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) метода при его загрузке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|Флаги не установлены.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Элементы управления [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) обратный вызов для добавления ссылки на сборки во время обхода замыкания сборки среды CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Элементы управления [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) обратный вызов для обновления в поток символ, связанный с модулем в памяти.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Элементы управления [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) обратного вызова, указывающий, когда динамический метод был мусора собираются и выгрузки. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, для которых необходимы улучшенные профилировщиком изображения. Он соответствует `COR_PRF_REQUIRE_PROFILE_IMAGE` флаг в [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Представляет все флаги `COR_PRF_HIGH_MONITOR`, которые могут быть установлены только во время инициализации. Попытка изменить какой-нибудь из этих флагов в другом месте вызовет значение `HRESULT`, указывающее на сбой.|  
  
## <a name="remarks"></a>Примечания  
 `COR_PRF_HIGH_MONITOR` Флаги используются с `pdwEventsHigh` параметр [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) и [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) методы.  
  
Начиная с .NET Framework 4.6.1, значение `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` изменить от 0 до `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). Начиная с .NET Framework 4.7.2, его значение изменилось с `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` для `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` должен быть битовой маской, который представляет все флаги, которые можно задать только во время инициализации. Попытка изменить какие-либо из этих флагов в другом месте вызовет сбой `HRESULT`.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Перечисление COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [Интерфейс ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
