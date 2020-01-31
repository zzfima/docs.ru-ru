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
ms.openlocfilehash: 2ed32449c4a133e6e72ec44f9cb57f49de22164a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778232"
---
# <a name="cordebugplatform-enumeration"></a>Перечисление CorDebugPlatform
Предоставляет значения целевой платформы, используемые методом [ICorDebugDataTarget::](icordebugdatatarget-getplatform-method.md) WebMethod.  
  
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
|CORDB_PLATFORM_MAC_PPC|Целевая платформа — это операционная система Macintosh, которая работает на оборудовании PowerPC.|  
|CORDB_PLATFORM_MAC_X86|Целевая платформа — это операционная система Macintosh, работающая на оборудовании Intel x86.|  
|CORDB_PLATFORM_WINDOWS_ARM|Целевая платформа — это операционная система Macintosh, которая работает на оборудовании Windows ARM.|  
|CORDB_PLATFORM_MAC_AMD64|Целевая платформа — это операционная система Macintosh, работающая на оборудовании AMD64.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
 Члены `CORDB_PLATFORM_WINDOWS_ARM` и `CORDB_PLATFORM_MAC_AMD64` доступны в платформе .NET Framework версии 4.5.2 и более поздних.  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
