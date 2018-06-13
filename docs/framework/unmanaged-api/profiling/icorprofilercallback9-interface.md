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
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452381"
---
# <a name="icorprofilercallback9-interface"></a>Интерфейс ICorProfilerCallback9
[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]  

 Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемые средой CLR для уведомления профилировщика успешного мусора собираются и впоследствии выгружен динамического метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Уведомляет профилировщик о динамический метод сборки мусора, которые собираются и впоследствии выгружен.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
**Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также  
[Интерфейсы профилирования](profiling-interfaces.md)   
[Интерфейс ICorProfilerCallback8](icorprofilercallback9-interface.md)   
[Метод ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)   
[Метод ICorProfilerCallback8.DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
