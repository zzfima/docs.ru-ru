---
title: Метод ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4f0bbef1ce0e6e4a2a0e904bfe8ebb997d5f4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586596"
---
# <a name="icordebugmanagedcallbackexception-method"></a>Метод ICorDebugManagedCallback::Exception
Уведомляет отладчик о том, что исключение выдавалось из управляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pAppDomain`  
 [in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, в котором возникло исключение.  
  
 `pThread`  
 [in] Указатель на объект ICorDebugThread, представляющий поток, в котором возникло исключение.  
  
 `unhandled`  
 [in] Если это значение равно `false`, исключение еще не был обработан элементом приложения; в противном случае, исключение остается необработанным и завершает процесс.  
  
## <a name="remarks"></a>Примечания  
 Конкретное исключение можно получить из объекта потока.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
