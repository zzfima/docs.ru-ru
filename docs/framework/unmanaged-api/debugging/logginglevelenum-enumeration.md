---
title: Перечисление LoggingLevelEnum
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 01e1eafd9955a0876f77e34eb73c2a3fc6d815c2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139207"
---
# <a name="logginglevelenum-enumeration"></a>Перечисление LoggingLevelEnum
Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`LTraceLevel0`|Сообщение является уровнем трассировки 0.|  
|`LTraceLevel1`|Сообщение является уровнем трассировки 1.|  
|`LTraceLevel2`|Сообщение является уровнем трассировки 2.|  
|`LTraceLevel3`|Сообщение имеет уровень трассировки 3.|  
|`LTraceLevel4`|Сообщение имеет уровень трассировки 4.|  
|`LStatusLevel0`|Сообщение имеет уровень состояния 0.|  
|`LStatusLevel1`|Сообщение имеет уровень состояния 1.|  
|`LStatusLevel2`|Сообщение имеет уровень состояния 2.|  
|`LStatusLevel3`|Сообщение имеет уровень состояния 3.|  
|`LStatusLevel4`|Сообщение имеет уровень состояния 4.|  
|`LWarningLevel`|Сообщение является уровнем предупреждения.|  
|`LErrorLevel`|Сообщение имеет уровень ошибки.|  
|`LPanicLevel`|Сообщение имеет уровень тревоги.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR вызывает метод [ICorDebugManagedCallback:: LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) , чтобы уведомить отладчик о том, что управляемый поток зарегистрировал событие. Среда CLR передает значение перечисления `LoggingLevelEnum`, чтобы указать степень серьезности сообщения, которое управляемый поток записал в журнал событий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.EventLog>
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
