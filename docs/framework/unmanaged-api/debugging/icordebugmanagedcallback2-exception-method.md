---
title: "Метод ICorDebugManagedCallback2::Exception"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 79a8fa4709aeb04164bd1c2da07607435b76fff5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exception-method"></a>Метод ICorDebugManagedCallback2::Exception
Уведомляет отладчик о начале поиска для обработчика исключений.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, содержащий поток, в котором возникло исключение.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, представляющий поток, в котором возникло исключение.  
  
 `pFrame`  
 [in] Указатель на объект ICorDebugFrame, который представляет кадр, что определяется `dwEventType` параметра. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `nOffset`  
 [in] Целое число, определяющее смещение определяется `dwEventType` параметра. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `dwEventType`  
 [in] Значение перечисления CorDebugExceptionCallbackType, которое указывает тип обратного вызова, это исключение.  
  
 `dwFlags`  
 [in] Значение [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) перечисления, в котором указываются дополнительные сведения об исключении  
  
## <a name="remarks"></a>Примечания  
 `Exception` Обратного вызова вызывается в различных точках этапа поиска процесса обработки исключений. То есть он может быть вызван больше, чем один раз во время очистки исключения.  
  
 Исключение обрабатывается могут быть получены из ICorDebugThread объект, упоминаемый в `pThread` параметра.  
  
 Определенный кадр и смещение определяются `dwEventType` параметр следующим образом:  
  
|Значение `dwEventType`|Значение `pFrame`|Значение `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Кадр, который вызвал исключение.|Указатель инструкций в кадре.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Фрейма пользовательского кода, ближайшего к точке вызванного исключения.|Указатель инструкций в кадре.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Кадр, содержащего обработчик catch.|Смещение промежуточного языка MSIL Корпорация Майкрософт начала обработчика блока catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Не определено.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
