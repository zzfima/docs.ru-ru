---
title: Метод ICorProfilerCallback::RemotingServerSendingReply
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865978"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>Метод ICorProfilerCallback::RemotingServerSendingReply
Уведомляет профилировщик о том, что процесс завершил обработку запроса удаленного вызова метода и собирается передать ответ через канал.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCookie`  
 окне Указатель на идентификатор GUID, который будет соответствовать значению, указанному в параметре [ICorProfilerCallback:: ремотингклиентрецеивингрепли](icorprofilercallback-remotingclientreceivingreply-method.md) в следующих условиях:  
  
- Файлы Cookie GUID удаленного взаимодействия активны.  
  
- Канал проходит успешную передачу сообщения.  
  
- Файлы Cookie GUID активны в процессе на стороне клиента.  
  
 Это позволяет легко связывать вызовы удаленного взаимодействия и создавать логические стеки вызовов.  
  
 `fIsAsync`  
 окне Значение, которое `true`, если вызов является асинхронным; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
