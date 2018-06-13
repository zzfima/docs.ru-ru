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
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455287"
---
# <a name="icorprofilercallback8-interface"></a>Интерфейс ICorProfilerCallback8
[Поддерживается в .NET Framework 4.7 и более поздних версиях]  

 Подкласс [ICorProfilerCallback7](icorprofilercallback7-interface.md) , предоставляющий методы обратного вызова, используемые средой CLR для уведомления профилировщика, запуска и завершения JIT-компиляции динамического метода. 
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Уведомляет профилировщик о начале JIT-компиляции динамического метода.|  
|[Метод DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Уведомляет профилировщик об окончании JIT-компиляции динамического метода.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
**Версии платформы .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также  
[Интерфейсы профилирования](profiling-interfaces.md)   
[Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md)
