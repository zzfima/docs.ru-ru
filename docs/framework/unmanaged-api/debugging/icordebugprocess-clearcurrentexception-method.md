---
title: Метод ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f014f9213a4b9a2d5119af9a6dceebb9a9d54b52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473477"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>Метод ICorDebugProcess::ClearCurrentException
Очищает текущее неуправляемое исключение в данном потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 [in] Идентификатор потока, на котором будет очищен текущее неуправляемое исключение.  
  
## <a name="remarks"></a>Примечания  
 Вызовите этот метод перед вызовом [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) когда поток сообщил неуправляемые исключения, которое следует игнорировать при отладке. Это приведет к устранению диапазона (IB) и события (OOB)-каналу в данном потоке. Все точки останова OOB и одношаговые исключения автоматически очищается.  
  
 Используйте [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) для перехвата текущего управляемые исключения в потоке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
