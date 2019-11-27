---
title: Метод ICorProfilerCallback::RuntimeSuspendFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446972"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>Метод ICorProfilerCallback::RuntimeSuspendFinished
Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Примечания  
 Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения. На этом этапе они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу. Это также относится к новым потокам, которые вводят среду выполнения. Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже находятся в коде для преобразования, либо если они запросят приостановить работу в случае, если они достигают кода источника.  
  
 Обратный вызов `RuntimeSuspendFinished` будет гарантированно выполняться в том же потоке, что и обратный вызов [ICorProfilerCallback:: рунтимесуспендстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
