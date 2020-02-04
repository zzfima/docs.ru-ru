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
ms.openlocfilehash: 90ddb30c3d27d5f431c355abd3a6f792564e616d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866055"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>Метод ICorProfilerCallback::RemotingClientInvocationFinished
Уведомляет профилировщик о том, что вызов удаленного взаимодействия был выполнен до завершения на клиенте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Заметки  
 Если вызов удаленного взаимодействия был синхронным, он также выполняется до завершения на сервере. Если вызов удаленного взаимодействия был асинхронным, то при обработке вызова может быть по-прежнему ожидаемый ответ. Если ожидается ответ, он будет выполняться как вызов метода [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) и дополнительный вызов `RemotingClientInvocationFinished` для указания необходимой дополнительной обработки асинхронного вызова.  
  
 Каждая из следующих пар обратных вызовов будет выполняться в одном потоке:  
  
- `RemotingClientInvocationStarted` и [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) и [ICorProfilerCallback:: ремотингклиентинвокатионфинишед](icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) и [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)  
  
 При использовании обратных вызовов удаленного взаимодействия следует учитывать следующие моменты.  
  
- Выполнение функции удаленного взаимодействия не отражается API-интерфейсом профилировщика, поэтому уведомления для функций, которые вызываются из клиента и выполняются на сервере, не получаются должным образом. Фактический вызов происходит через прокси-объект; для профилировщика отображается, что определенные функции JIT-скомпилированы, но никогда не используются.  
  
- Профилировщик не получает точные уведомления о событиях асинхронного удаленного взаимодействия.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
