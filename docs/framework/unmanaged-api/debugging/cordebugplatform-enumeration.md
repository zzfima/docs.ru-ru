---
title: Перечисление CorDebugPlatform
ms.date: 03/30/2017
api_name:
- CorDebugPlatformEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugPlatformEnum
helpviewer_keywords:
- CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c0644dc247225c510e1c84254417551b490416
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739665"
---
# <a name="cordebugplatform-enumeration"></a>Перечисление CorDebugPlatform
Предоставляет значения целевой платформы, используемые [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|CORDB_PLATFORM_WINDOWS_X86|Целевая платформа — ОС Windows, работающая на процессоре Intel x86.|  
|CORDB_PLATFORM_WINDOWS_AMD64|Целевая платформа — 64-разрядная версия ОС Windows, работающая на процессоре AMD64 или Intel EM64T.|  
|CORDB_PLATFORM_WINDOWS_IA64|Целевая платформа — 32-разрядная версия ОС Windows, работающая на процессоре IA-64.|  
|CORDB_PLATFORM_MAC_PPC|Целевая платформа — ОС Macintosh, работающая на процессоре PowerPC.|  
|CORDB_PLATFORM_MAC_X86|Целевая платформа — ОС Macintosh, работающая на процессоре Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|Целевая платформа — ОС Macintosh, работающая на процессоре Windows ARM.|  
|CORDB_PLATFORM_MAC_AMD64|Целевая платформа — ОС Macintosh, работающая на процессоре AMD64.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 Члены `CORDB_PLATFORM_WINDOWS_ARM` и `CORDB_PLATFORM_MAC_AMD64` доступны в платформе .NET Framework версии 4.5.2 и более поздних.  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
