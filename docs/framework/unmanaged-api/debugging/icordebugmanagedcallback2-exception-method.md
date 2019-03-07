---
title: Метод ICorDebugManagedCallback2::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f776f20f163df91d65509e5dbab31fe9c29a965
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492105"
---
# <a name="icordebugmanagedcallback2exception-method"></a>Метод ICorDebugManagedCallback2::Exception
Уведомляет отладчик о начале поиска обработчика исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, на котором возникло исключение.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, представляющий поток, на котором возникло исключение.  
  
 `pFrame`  
 [in] Указатель на интерфейс ICorDebugFrame объект, представляющий кадр, что определяется `dwEventType` параметра. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `nOffset`  
 [in] Целое число, указывающее смещение, определяемое `dwEventType` параметра. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `dwEventType`  
 [in] Значение перечисления CorDebugExceptionCallbackType, которое указывает тип этого обратного вызова исключения.  
  
 `dwFlags`  
 [in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисление, содержащее дополнительные сведения об исключении  
  
## <a name="remarks"></a>Примечания  
 `Exception` Обратный вызов выполняется в различных точках этапа поиска процесса обработки исключений. То есть он может быть вызван больше, чем один раз во время очистки исключения.  
  
 Исключение обрабатывается можно получить из объекта ICorDebugThread ссылается `pThread` параметра.  
  
 Определенный кадр и смещение определяется `dwEventType` параметр следующим образом:  
  
|Значение `dwEventType`|Значение `pFrame`|Значение `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Фрейма, вызвавшего исключение.|Указатель инструкций в кадре.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Фрейма пользовательского кода, ближайшего к точке вызванного исключения.|Указатель инструкций в кадре.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Кадр, содержащего обработчик catch.|Смещение промежуточного языка MSIL Microsoft начале обработчика catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Не определено.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
