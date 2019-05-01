---
title: Метод ICorProfilerCallback::RemotingClientSendingMessage
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61a36ff23bf9deac25983f06387b2bbbfd49546b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041903"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>Метод ICorProfilerCallback::RemotingClientSendingMessage
Уведомляет профилировщик о том, что клиент отправляет запрос к серверу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCookie`  
 [in] Значение, которое соответствует со значением в [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) в этих условиях:  
  
- Файлы cookie для GUID удаленного взаимодействия активны.  
  
- Каналу удалось передать сообщение.  
  
- Файлы cookie GUID активны на процесс на стороне сервера.  
  
 Это позволяет легко создавать пары вызовов удаленного взаимодействия и Создание логического стека вызовов.  
  
 `fIsAsync`  
 [in] Значение, которое является `true` Если вызов выполняется асинхронно; в противном случае — значение `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
