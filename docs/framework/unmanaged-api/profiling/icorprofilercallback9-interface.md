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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227760"
---
# <a name="icorprofilercallback9-interface"></a>Интерфейс ICorProfilerCallback9
[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]  

 Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, среда CLR, используемый для уведомления профилировщика успешного мусора собираются и впоследствии выгружен динамического метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Уведомляет профилировщик о динамический метод сборки мусора, которые собираются и впоследствии выгружен.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback9-interface.md)
- [Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
