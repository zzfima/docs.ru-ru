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
ms.openlocfilehash: fd7909b94343b1fb83836f5c369ddc1993f049d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191178"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Метод ICorDebugManagedCallback::DebuggerError
Уведомляет отладчик о том, что произошла ошибка при попытке обработать события из общеязыковой среды выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 [in] Указатель на объект «ICorDebugProcess», представляющий процесс, в котором произошло событие.  
  
 `errorHR`  
 [in] Значение HRESULT, который был возвращен из обработчика событий.  
  
 `errorCode`  
 [in] Целое число, задающее ошибку среды CLR.  
  
## <a name="remarks"></a>Примечания  
 Процесс может размещаться в сквозном режиме, в зависимости от типа ошибки.  
  
 `DebugError` Обратный вызов указывает, что службы отладки были отключены из-за ошибки, поэтому отладчики должны предоставить сообщение об ошибке доступны пользователю. [ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) безопасные для вызова, но все другие методы, включая [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), не следует вызывать. Отладчик должен воспользоваться возможностями системы для завершения процессов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
