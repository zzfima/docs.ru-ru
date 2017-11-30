---
title: "Перечисление LoggingLevelEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f6041f429c057cea9607df34ec5691be84e2d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`LTraceLevel0`|Сообщение находится на уровне трассировки 0.|  
|`LTraceLevel1`|Сообщение является уровень трассировки 1.|  
|`LTraceLevel2`|Сообщение является уровень трассировки 2.|  
|`LTraceLevel3`|Сообщение является 3 уровень трассировки.|  
|`LTraceLevel4`|Сообщение является 4 уровень трассировки.|  
|`LStatusLevel0`|Сообщение находится на уровне состояния 0.|  
|`LStatusLevel1`|Сообщение находится на уровне состояния 1.|  
|`LStatusLevel2`|Сообщение находится на уровне состояния 2.|  
|`LStatusLevel3`|Сообщение — это состояние, уровень 3.|  
|`LStatusLevel4`|Сообщение находится на уровне состояния 4.|  
|`LWarningLevel`|Сообщение находится на уровне предупреждения.|  
|`LErrorLevel`|Сообщение находится на уровне ошибки.|  
|`LPanicLevel`|Сообщение находится на уровне тревоги.|  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения (CLR) вызывает [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) метод для уведомления отладчик, что управляемый поток выполнил событие. Среда CLR передает значение `LoggingLevelEnum` перечисления, чтобы указать уровень серьезности сообщения, которое управляемый поток будет записано в журнал событий.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.EventLog>  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
