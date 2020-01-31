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
ms.openlocfilehash: 9b96c0a2eca543b9e01ccf92b271b1aa7003c5c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781938"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Метод ICorDebugManagedCallback::DebuggerError
Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 окне Указатель на объект "ICorDebugProcess", представляющий процесс, в котором произошло событие.  
  
 `errorHR`  
 окне Значение HRESULT, возвращенное обработчиком событий.  
  
 `errorCode`  
 окне Целое число, указывающее ошибку CLR.  
  
## <a name="remarks"></a>Заметки  
 Процесс может быть помещен в сквозной режим в зависимости от характера ошибки.  
  
 Обратный вызов `DebugError` указывает, что службы отладки были отключены из-за ошибки, поэтому Отладчики должны сделать сообщение об ошибке доступным для пользователя. [ICorDebugProcess:: GetID](icordebugprocess-getid-method.md) будет использоваться в качестве безопасного вызова, но все остальные методы, включая [ICorDebug:: Terminate](icordebug-terminate-method.md), не должны вызываться. Отладчик должен использовать средства операционной системы для завершения процессов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
