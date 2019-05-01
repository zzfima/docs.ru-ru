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
ms.openlocfilehash: cf83124af5ced7bb6458564430ceb319ce7d680a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995180"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>Метод ICorDebugManagedCallback::LogMessage
Уведомляет отладчик о том, что нитью среды выполнения (CLR) управляемый язык вызвал метод <xref:System.Diagnostics.EventLog> класс события в журнал.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
