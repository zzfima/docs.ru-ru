---
title: Метод ICorDebugManagedCallback2::ChangeConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 4558074bc23334bd697461a00ccb31db3e3fe397
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130599"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>Метод ICorDebugManagedCallback2::ChangeConnection
Уведомляет отладчик о том, что набор задач, связанных с указанным соединением, изменился.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 окне Указатель на объект "ICorDebugProcess", представляющий процесс, содержащий измененное соединение.  
  
 `dwConnectionId`  
 окне Идентификатор измененного соединения.  
  
## <a name="remarks"></a>Заметки  
 Обратный вызов `ChangeConnection` будет срабатывать в одном из следующих случаев.  
  
- При присоединении отладчика к процессу, который содержит соединения. В этом случае среда выполнения создаст и отправит событие [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) и событие `ChangeConnection` для каждого соединения в процессе. Событие `ChangeConnection` создается для каждого существующего соединения независимо от того, изменился ли набор задач этого соединения с момента его создания.  
  
- Когда узел вызывает [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 Отладчик должен проверить все потоки в процессе, чтобы получить новые изменения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
