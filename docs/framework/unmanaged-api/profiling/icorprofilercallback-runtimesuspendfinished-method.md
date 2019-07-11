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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6412f31417ead963e987e0c50ad46c78a77d367f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750867"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>Метод ICorProfilerCallback::RuntimeSuspendFinished
Уведомляет профилировщика о том, что среда выполнения завершила приостановку всех потоков среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Примечания  
 Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжать выполняться, пока они пытаются повторно ввести среды выполнения. В этот момент они также будут приостановлены до среду выполнения. Это также относится к новых потоков, выполняющих вход в среду выполнения. Все потоки в среде выполнения, либо приостановлен немедленно, если они уже такого кода или получают запрос на приостановку по достижении такого кода.  
  
 `RuntimeSuspendFinished` Обратный вызов гарантированно происходит в том же потоке, что [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
