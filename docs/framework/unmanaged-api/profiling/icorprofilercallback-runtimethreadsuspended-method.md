---
title: Метод ICorProfilerCallback::RuntimeThreadSuspended
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54d297f6915af59ad5a24dfdad9dca9397489edb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468173"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>Метод ICorProfilerCallback::RuntimeThreadSuspended
Уведомляет профилировщик, что указанный поток был приостановлен или будет приостановлено.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadId`  
 [in] Идентификатор потока, который был приостановлен.  
  
## <a name="remarks"></a>Примечания  
 `RuntimeThreadSuspended` Уведомлений может произойти любое время между [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) и связанным [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы. Уведомления, которые выполняются между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` для потоков, которые были запущены в неуправляемом коде и были приостановлены после входа в среду выполнения.  
  
 Как правило этот обратный вызов происходит только в том случае, после приостановки потока. Тем не менее если текущий выполняемый поток (поток, вызвавший этот обратный вызов) является тот, который приостанавливается, этот обратный вызов возникает непосредственно перед поток приостановлен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
