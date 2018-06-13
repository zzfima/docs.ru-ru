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
ms.openlocfilehash: d7024b8c0682b3351d185e518dd149737beb04bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416362"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>Метод ICorDebugManagedCallback2::CreateConnection
Уведомляет отладчик о том, создания нового соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pProcess`  
 [in] Указатель на объект «ICorDebugProcess», представляет собой процесс, в которой был создан соединения  
  
 `dwConnectionId`  
 [in] Идентификатор нового подключения.  
  
 `pConnName`  
 [in] Указатель на имя нового подключения.  
  
## <a name="remarks"></a>Примечания  
 Объект `CreateConnection` обратный вызов будет запускаться в любом из следующих случаев:  
  
-   Когда отладчик подключается к процессу, содержащий подключения. В этом случае среда выполнения создаст и отправки `CreateConnection` событий и [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) событий для каждого соединения в процессе.  
  
-   Если узел вызывает [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) в [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
