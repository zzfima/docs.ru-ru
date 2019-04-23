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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe8e1355382273a681e927897f4a8ff5814b8de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086511"
---
# <a name="logginglevelenum-enumeration"></a>Перечисление LoggingLevelEnum
Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`LTraceLevel0`|Сообщение является уровень трассировки 0.|  
|`LTraceLevel1`|Сообщение является уровень трассировки 1.|  
|`LTraceLevel2`|Сообщение является уровень трассировки 2.|  
|`LTraceLevel3`|Сообщение является уровень трассировки 3.|  
|`LTraceLevel4`|Сообщение является уровень трассировки 4.|  
|`LStatusLevel0`|Сообщение является уровнем состояние 0.|  
|`LStatusLevel1`|Сообщение является уровнем состояние 1.|  
|`LStatusLevel2`|Сообщение является уровнем состояние 2.|  
|`LStatusLevel3`|Сообщение является уровнем состояние 3.|  
|`LStatusLevel4`|Сообщение является уровнем состояние 4.|  
|`LWarningLevel`|Сообщение является уровень предупреждений.|  
|`LErrorLevel`|Сообщение находится на уровне ошибки.|  
|`LPanicLevel`|Сообщение находится на уровне тревоги.|  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения (CLR) вызывает [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) метод для уведомления отладчик о том, что управляемый поток выполнил событие. Среда CLR передает значение `LoggingLevelEnum` перечисление, чтобы указать уровень серьезности сообщения, которое написал управляемый поток в журнале событий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.EventLog>
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
