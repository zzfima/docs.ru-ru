---
title: Структура OSINFO
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 89111bf7eb03d20c2010c7a20c4cd055c2a021e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430731"
---
# <a name="osinfo-structure"></a>Структура OSINFO
Содержит сведения об операционной системе для сборки или модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwOSPlatformId`|Одно из значений идентификатора, определяемое функцией платформы Microsoft Windows `GetVersionEx`. Поддерживаются следующие значения.<br /><br /> -VER_PLATFORM_WIN32s или символ 0x0000, чтобы указать Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS или 0x0001, чтобы указать для Windows 95, Windows 98 или операционных систем по убыванию.<br />-VER_PLATFORM_WIN32_NT или 0x0010, чтобы указать Windows NT или операционные системы в обратном порядке.|  
|`dwOSMajorVersion`|Основной номер версии операционной системы или значение NULL для указания любой версии.|  
|`dwOSMinorVersion`|Дополнительный номер версии операционной системы или значение NULL для указания любой версии.|  
  
## <a name="remarks"></a>Примечания  
 `OSINFO` основан на структуре `OSVERSIONINFOEX`, которая используется в вызовах функции платформы Microsoft Windows `GetVersionEx`. Эта структура используется структурой ASSEMBLYMETADATA для указания поддержки операционной системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
