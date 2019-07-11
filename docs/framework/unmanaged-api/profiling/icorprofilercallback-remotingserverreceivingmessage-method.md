---
title: Метод ICorProfilerCallback::RemotingServerReceivingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2bc3e48185c3bc289a4f7bfd865f69d9c06a720c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750511"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>Метод ICorProfilerCallback::RemotingServerReceivingMessage
Уведомляет профилировщик, что процесс получил запрос или активации с помощью вызова удаленного метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCookie`  
 [in] Значение, будет соответствовать со значением в [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) в этих условиях:  
  
- Файлы cookie для GUID удаленного взаимодействия активны.  
  
- Каналу удалось передать сообщение.  
  
- Файлы cookie GUID активны на процесс на стороне клиента.  
  
 Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.  
  
 `fIsAsync`  
 [in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Если запрос сообщения является асинхронным, запрос может обслуживаться произвольным потоком.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
