---
title: Интерфейс ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049730"
---
# <a name="icorprofilercallback8-interface"></a>Интерфейс ICorProfilerCallback8
[Поддерживается в .NET Framework 4.7 и более поздних версиях]  

 Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, среда CLR, используемый для уведомления профилировщика о началась и завершения JIT-компиляция динамического метода. 
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Уведомляет профилировщик о начале JIT-компиляция динамического метода.|  
|[Метод DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Уведомляет профилировщик об окончании JIT-компиляция динамического метода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md)
