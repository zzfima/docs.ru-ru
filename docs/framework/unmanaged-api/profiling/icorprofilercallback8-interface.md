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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175100"
---
# <a name="icorprofilercallback8-interface"></a>Интерфейс ICorProfilerCallback8
«Поддерживается в рамках .NET 4.7 и более поздних версиях»  

 Подкласс [ICorProfilerCallback7,](icorprofilercallback7-interface.md) который предоставляет методы обратного отработки, используемые общим временем выполнения языка, чтобы уведомить профайлера о том, что компиляция JIT динамического метода запущена и закончена.
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Уведомляет профайлера о том, что jIT начал компиляцию динамического метода.|  
|[Метод DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Уведомляет профайлера о завершении компиляции динамического метода JIT.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md)
