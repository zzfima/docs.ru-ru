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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024b1f3f7e08dc21582789de7f3899e8e44d5e39
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162689"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>Метод ICorProfilerCallback::RemotingServerSendingReply
Уведомляет профилировщик, что процесс завершил обработку запроса вызова удаленного метода и собирается передачи ответа по каналу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCookie`  
 [in] Указатель на идентификатор GUID, которое соответствует значение, указанное в [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) в этих условиях:  
  
-   Файлы cookie для GUID удаленного взаимодействия активны.  
  
-   Каналу удалось передать сообщение.  
  
-   Файлы cookie GUID активны на процесс на стороне клиента.  
  
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
