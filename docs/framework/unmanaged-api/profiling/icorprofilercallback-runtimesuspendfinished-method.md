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
ms.openlocfilehash: 0b243c507171a4d907ef4594ae0c715a074c965a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452222"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>Метод ICorProfilerCallback::RuntimeSuspendFinished
Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Примечания  
 Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжить выполнение, пока они пытаются заново ввести среды выполнения. В этот момент они также будут приостановлены до возобновления работы среды выполнения. Это справедливо и для новых потоков, выполняющих вход в среду выполнения. Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже такого кода или получают запрос на приостановку по достижении такого кода.  
  
 `RuntimeSuspendFinished` Обратный вызов гарантированно происходит в том же потоке, как [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
