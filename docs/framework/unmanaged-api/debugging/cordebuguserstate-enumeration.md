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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54b2af6e7a200db89bfd7335868a629d7a886fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141314"
---
# <a name="cordebuguserstate-enumeration"></a>Перечисление CorDebugUserState
Указывает состояние пользователя потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Значение|Описание|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Запрошено завершение выполнения потока.|  
|`USER_SUSPEND_REQUESTED`|Приостановка потока был запрошен.|  
|`USER_BACKGROUND`|Поток выполняется в фоновом режиме.|  
|`USER_UNSTARTED`|Поток не начали выполняться.|  
|`USER_STOPPED`|Поток был завершен.|  
|`USER_WAIT_SLEEP_JOIN`|Поток ожидает другого потока для выполнения задачи.|  
|`USER_SUSPENDED`|Поток был приостановлен.|  
|`USER_UNSAFE_POINT`|Поток находится в небезопасной точке. То есть поток находится в точке выполнения, в которой он может блокировать сбора мусора.<br /><br /> Отладка событий могут доставляться в небезопасных точках, но приостановка потока в такой точке вероятнее всего вызовет взаимоблокировку до возобновления потока. Безопасные и небезопасные точки определяются just-in-time (JIT) и реализации сбора мусора.|  
|`USER_THREADPOOL`|Поток может из пула потоков.|  
  
## <a name="remarks"></a>Примечания  
 Пользовательское состояние потока — используется состояние с потока при его анализа отладчиком. Поток может иметь сочетание пользовательских состояний.  
  
 Используйте [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) метод для извлечения состояния пользователя потока.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
