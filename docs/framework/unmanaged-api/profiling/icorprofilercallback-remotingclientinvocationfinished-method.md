---
title: Метод ICorProfilerCallback::RemotingClientInvocationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: c9a750b941b29047206c98410d4b4673d1101a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445834"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>Метод ICorProfilerCallback::RemotingClientInvocationFinished
Уведомляет профилировщик о том, что вызов удаленного взаимодействия был выполнен до завершения на клиенте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Примечания  
 Если вызов удаленного взаимодействия был синхронным, он также выполняется до завершения на сервере. Если вызов удаленного взаимодействия был асинхронным, то при обработке вызова может быть по-прежнему ожидаемый ответ. Если ожидается ответ, он будет выполняться как вызов метода [ICorProfilerCallback:: ремотингклиентрецеивингрепли](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) и дополнительный вызов `RemotingClientInvocationFinished` для указания необходимой дополнительной обработки асинхронного вызова.  
  
 Каждая из следующих пар обратных вызовов будет выполняться в одном потоке:  
  
- `RemotingClientInvocationStarted` и [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: ремотингклиентрецеивингрепли](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback:: ремотингклиентинвокатионфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 При использовании обратных вызовов удаленного взаимодействия следует учитывать следующие моменты.  
  
- Выполнение функции удаленного взаимодействия не отражается API-интерфейсом профилировщика, поэтому уведомления для функций, которые вызываются из клиента и выполняются на сервере, не получаются должным образом. Фактический вызов происходит через прокси-объект; для профилировщика отображается, что определенные функции JIT-скомпилированы, но никогда не используются.  
  
- Профилировщик не получает точные уведомления о событиях асинхронного удаленного взаимодействия.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
