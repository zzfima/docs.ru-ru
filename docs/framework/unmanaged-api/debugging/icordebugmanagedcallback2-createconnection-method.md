---
title: Метод ICorDebugManagedCallback2::CreateConnection
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10d0fc0c65d6c479ee4bf7bf527ee33615d53084
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761165"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>Метод ICorDebugManagedCallback2::CreateConnection
Уведомляет отладчик для создания нового соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 [in] Указатель на объект «ICorDebugProcess», представляющий процесс, в котором был создан соединения  
  
 `dwConnectionId`  
 [in] Идентификатор нового подключения.  
  
 `pConnName`  
 [in] Указатель на имя нового подключения.  
  
## <a name="remarks"></a>Примечания  
 Объект `CreateConnection` обратного вызова будет запускаться в любом из следующих случаев:  
  
- Когда отладчик подключается к процессу, который содержит соединения. В этом случае среда выполнения создаст и диспетчеризации `CreateConnection` событий и [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) событий для каждого соединения в процессе.  
  
- Если узел вызывает [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
