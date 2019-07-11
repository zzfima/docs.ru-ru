---
title: Метод ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b10b94f66a6b5434befeac1cd9562cb8a0f27f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761557"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>Метод ICorDebugManagedCallback::LogMessage
Уведомляет отладчик о том, что нитью среды выполнения (CLR) управляемый язык вызвал метод <xref:System.Diagnostics.EventLog> класс события в журнал.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий управляемый поток, который зафиксировал событие.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, который представляет управляемый поток.  
  
 `lLevel`  
 [in] Значение [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) перечисление, указывающее степень серьезности описательное сообщение, которые были записаны в журнал событий.  
  
 `pLogSwitchName`  
 [in] Указатель на имя переключателя трассировки.  
  
 `pMessage`  
 [in] Указатель на сообщения, которые были записаны в журнал событий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
