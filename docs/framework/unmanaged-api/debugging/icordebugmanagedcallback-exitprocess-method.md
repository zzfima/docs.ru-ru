---
title: Метод ICorDebugManagedCallback::ExitProcess
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130777"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>Метод ICorDebugManagedCallback::ExitProcess
Уведомляет отладчик о завершении процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pProcess`  
 окне Указатель на объект ICorDebugProcess, представляющий процесс.  
  
## <a name="remarks"></a>Заметки  
 Невозможно продолжить выполнение события `ExitProcess`. Это событие может вызываться асинхронно для других событий, пока процесс остановлен. Это может произойти, если процесс завершается при остановке, обычно из-за некоторой внешней силы.  
  
 Если общеязыковая среда выполнения (CLR) уже передает управляемый обратный вызов, это событие будет отложено до тех пор, пока этот обратный вызов не вернется.  
  
 Событие `ExitProcess` является единственным событием выхода и выгрузки, которое гарантированно вызывается при завершении работы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
