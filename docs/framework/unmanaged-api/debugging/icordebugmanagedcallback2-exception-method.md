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
ms.openlocfilehash: f40030a2034057e83de51a21655a686f30b9ee88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137452"
---
# <a name="icordebugmanagedcallback2exception-method"></a>Метод ICorDebugManagedCallback2::Exception
Уведомляет отладчик о запуске поиска обработчика исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором было создано исключение.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.  
  
 `pFrame`  
 окне Указатель на объект ICorDebugFrame, представляющий кадр, как определено параметром `dwEventType`. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `nOffset`  
 окне Целое число, задающее смещение, определяемое параметром `dwEventType`. Дополнительные сведения см. в таблице в разделе "Примечания".  
  
 `dwEventType`  
 окне Значение перечисления CorDebugExceptionCallbackType, указывающее тип этого обратного вызова исключения.  
  
 `dwFlags`  
 окне Значение перечисления [кордебужексцептионфлагс](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) , которое указывает дополнительные сведения об исключении  
  
## <a name="remarks"></a>Заметки  
 Обратный вызов `Exception` вызывается в различных точках на этапе поиска процесса обработки исключений. То есть он может быть вызван более одного раза при очистке исключения.  
  
 Обрабатываемое исключение может быть получено из объекта ICorDebugThread, на который ссылается параметр `pThread`.  
  
 Конкретный кадр и смещение определяются параметром `dwEventType` следующим образом:  
  
|Значение `dwEventType`|Значение `pFrame`|Значение `nOffset`|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|Кадр, вызвавший исключение.|Указатель инструкции в кадре.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|Кадр пользовательского кода, ближайший к точке вызванного исключения.|Указатель инструкции в кадре.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Кадр, содержащий обработчик catch.|Смещение на языке MSIL, начинающееся с начала обработчика catch.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|Определено.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
