---
title: Перечисление CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff6b245c80050a5e85561b8bba6aa9ba8199ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="clrdebuggingprocessflags-enumeration"></a>Перечисление CLR_DEBUGGING_PROCESS_FLAGS
Предоставляет значения, которые используются в [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Эта среда выполнения имеет событие catch вверх отладчика управляемого кода для отправки. Различие между событиями, связанной с подключением и catch вверх см.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Управляемые события, которое находится в состоянии ожидания является <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> запроса.|  
  
## <a name="remarks"></a>Примечания  
 Захват событий включают процесса, домена приложения, сборки, модуля и уведомления создания потока, что позволяет использовать отладчик до текущего состояния после он присоединен к процессу. Non-catch вверх событий, которые обозначаются `CLR_DEBUGGING_MANAGED_EVENT_PENDING` флаг, включают все другие события отладчика, такие как исключения и управляемых отладки уведомления помощник (кода MDA).  
  
 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Флаг позволяет среде выполнения для различения неустранимое исключение и запрос на присоединение отладчика управляемого кода, может быть отменено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Metahost.idl, Metahost.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
