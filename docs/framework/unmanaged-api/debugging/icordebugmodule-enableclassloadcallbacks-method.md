---
title: Метод ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139218"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>Метод ICorDebugModule::EnableClassLoadCallbacks
Определяет, вызываются ли для этого модуля обратные вызовы [ICorDebugManagedCallback:: loadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bClassLoadCallbacks`  
 окне Присвойте этому параметру значение `true`, чтобы среда CLR вызывала методы `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` при возникновении связанных с ними событий.  
  
 Значение по умолчанию — `false` для модулей, не являющихся динамическими. Значение всегда `true` для динамических модулей и не может быть изменено.  
  
## <a name="remarks"></a>Заметки  
 Обратные вызовы `ICorDebugManagedCallback::LoadClass` и `ICorDebugManagedCallback::UnloadClass` всегда включены для динамических модулей и не могут быть отключены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
