---
title: Перечисление CorDebugUserState
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: d0394d511197c8d0aaa366ce7b791216a3d226bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120192"
---
# <a name="cordebuguserstate-enumeration"></a>Перечисление CorDebugUserState
Указывает состояние пользователя потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Члены  
  
|значения|Описание|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Запрошено завершение потока.|  
|`USER_SUSPEND_REQUESTED`|Запрошена приостановка потока.|  
|`USER_BACKGROUND`|Поток выполняется в фоновом режиме.|  
|`USER_UNSTARTED`|Поток не начал выполнять.|  
|`USER_STOPPED`|Поток был завершен.|  
|`USER_WAIT_SLEEP_JOIN`|Поток ожидает завершения задачи другим потоком.|  
|`USER_SUSPENDED`|Поток был приостановлен.|  
|`USER_UNSAFE_POINT`|Поток находится в ненадежной точке. Это значит, что поток находится в точке выполнения, где он может блокировать сборку мусора.<br /><br /> События отладки могут быть отправлены из ненадежных точек, но приостановка потока в незащищенной точке, скорее всего, вызовет взаимоблокировку до возобновления потока. Надежные и незащищенные точки определяются реализацией JIT и сборки мусора.|  
|`USER_THREADPOOL`|Поток из пула потоков.|  
  
## <a name="remarks"></a>Заметки  
 Пользовательское состояние потока — это состояние, которое поток имеет при его проверке отладчиком. Поток может иметь сочетание пользовательских состояний.  
  
 Чтобы получить состояние пользователя потока, используйте метод [ICorDebugThread:: жетусерстате](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
