---
title: Перечисление CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2e01a5cf2b2aa25e91ebf0f8e3927858b12bea3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967569"
---
# <a name="cordebugdebugeventkind-enumeration"></a>Перечисление CorDebugDebugEventKind
Указывает тип события, сведения о котором декодированы методом [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|Событие загрузки модуля.|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|Событие выгрузки модуля.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|Первичное исключение.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|Первичное исключение пользователя.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|Исключение, для которого существует обработчик `catch`.|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|Необработанное исключение.|  
  
## <a name="remarks"></a>Примечания  
 Член `CorDebugDebugEventKind` перечисления возвращается путем вызова метода [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
