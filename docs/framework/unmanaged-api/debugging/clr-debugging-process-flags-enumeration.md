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
ms.openlocfilehash: ef142ed5284262fd758ff13af8207b2290938e77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741146"
---
# <a name="clrdebuggingprocessflags-enumeration"></a>Перечисление CLR_DEBUGGING_PROCESS_FLAGS
Предоставляет значения, используемые [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|Эта среда выполнения имеет событие catch вверх управляемого отладчика для отправки. См. в разделе "Примечания" различие между событиями наверстывания и catch вверх.|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|Управляемое событие, которое находится в состоянии ожидания является <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> запроса.|  
  
## <a name="remarks"></a>Примечания  
 Захват событий включают процесса, домена приложения, сборки, модуля и поток создания уведомлений, которые приносят отладчик до текущего состояния после ее присоединения к процессу. Non-catch вверх событий, которые обозначены `CLR_DEBUGGING_MANAGED_EVENT_PENDING` флаг, включают все другие события отладчика, такие как исключения и управлении отладки уведомления помощник (кода MDA).  
  
 `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Флаг позволяет среде выполнения различать неустранимое исключение и запрос на присоединение управляемого отладчика, которое может быть отменено.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Metahost.IDL Metahost.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
