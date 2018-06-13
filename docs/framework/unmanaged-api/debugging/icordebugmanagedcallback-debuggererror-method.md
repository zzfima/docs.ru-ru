---
title: Метод ICorDebugManagedCallback::DebuggerError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 436be84ad91bb20bfd88a51f2d6c2b760c4a4c3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420141"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Метод ICorDebugManagedCallback::DebuggerError
Уведомляет отладчик о том, что произошла ошибка при попытке обработать событие из общеязыковой среды выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pProcess`  
 [in] Указатель на объект «ICorDebugProcess», который представляет собой процесс, в котором произошло событие.  
  
 `errorHR`  
 [in] Значение HRESULT, возвращенный из обработчика событий.  
  
 `errorCode`  
 [in] Целое число, задающее ошибку среды CLR.  
  
## <a name="remarks"></a>Примечания  
 Процесс может быть переведен в сквозной режим, в зависимости от характера ошибки.  
  
 `DebugError` Обратного вызова указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю. [ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные вызова, а также всех других методов, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не должен вызываться. Для завершения процессов отладчик должен воспользоваться возможностями системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
