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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136568"
---
# <a name="icorprofilercallback9-interface"></a>Интерфейс ICorProfilerCallback9
[Поддерживается в .NET Framework 4.7.2 и более поздних версиях]  

 Подкласс [ICorProfilerCallback8](icorprofilercallback8-interface.md) , предоставляющий метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод был собран в мусор и затем выгружен.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Уведомляет профилировщик о том, что динамический метод был собран в мусор и затем выгружен.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback8](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. Динамикмесоджиткомпилатионстартед, метод](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. Динамикмесоджиткомпилатионфинишед, метод](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
