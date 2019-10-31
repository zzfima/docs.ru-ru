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
ms.openlocfilehash: a81842132769934a6f5f34e6dc462bba77b3854a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138691"
---
# <a name="icordebugthread2getconnectionid-method"></a>Метод ICorDebugThread2::GetConnectionID
Возвращает идентификатор соединения для этого объекта ICorDebugThread2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pdwConnectionId`  
 заполняет `CONNID`, представляющий идентификатор соединения.  
  
## <a name="remarks"></a>Заметки  
 Метод `GetConnectionID` возвращает ноль в параметре `pdwConnectionId`, если этот поток не является частью соединения.  
  
 Если этот поток подключен к экземпляру Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` сопоставляется с идентификатором серверного процесса (SPID).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
