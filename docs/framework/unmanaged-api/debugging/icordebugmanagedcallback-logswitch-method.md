---
title: Метод ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130697"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>Метод ICorDebugManagedCallback::LogSwitch
Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в классе <xref:System.Diagnostics.Switch> для создания, изменения или удаления переключателя отладки или трассировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Параметры  
 `PAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который создал, изменил или удалил параметр отладки/трассировки.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий управляемый поток.  
  
 `lLevel`  
 окне Значение, указывающее степень серьезности описательного сообщения, записанного в журнал событий.  
  
 `ulReason`  
 окне Значение перечисления [логсвитчкаллреасон](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) , указывающее операцию, выполняемую с переключателем "Отладка/трассировка".  
  
 `pLogSwitchName`  
 окне Указатель на имя переключателя отладки/трассировки.  
  
 `pParentName`  
 окне Указатель на имя родителя переключателя "Отладка/трассировка".  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
