---
title: Метод ICorDebugThread2::GetConnectionID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc4963dcf686fe62f473aea1af86868df03718df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768968"
---
# <a name="icordebugthread2getconnectionid-method"></a>Метод ICorDebugThread2::GetConnectionID
Получает идентификатор подключения для этого объекта ICorDebugThread2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pdwConnectionId`  
 [out] Объект `CONNID` , представляющий идентификатор соединения.  
  
## <a name="remarks"></a>Примечания  
 `GetConnectionID` Метод возвращает нуль в `pdwConnectionId` параметра, если этот поток не является частью подключения.  
  
 Если этот поток был подключен к экземпляру из Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` сопоставляется идентификатор серверного процесса (SPID).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
