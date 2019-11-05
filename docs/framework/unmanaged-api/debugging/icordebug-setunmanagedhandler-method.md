---
title: Метод ICorDebug::SetUnmanagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134050"
---
# <a name="icordebugsetunmanagedhandler-method"></a>Метод ICorDebug::SetUnmanagedHandler
Указывает объект обработчика событий для неуправляемых событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCallback`  
 окне Указатель на объект [икордебугунманажедкаллбакк](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) , представляющий обработчик событий для неуправляемых событий.  
  
## <a name="remarks"></a>Заметки  
 Объект обработчика событий для неуправляемых событий должен быть задан после вызова метода [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) и перед вызовом [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) или [ICorDebug::D ебугактивепроцесс](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Однако для устаревших целей не требуется задавать объект обработчика событий для неуправляемых событий до тех пор, пока не будет вызвано первое собственное событие отладки. В частности, если `ICorDebug::CreateProcess` установлен флаг CREATE_SUSPENDED, события отладки машинного кода не могут быть отправлены, пока основной поток не возобновит работу.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
