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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175230"
---
# <a name="osinfo-structure"></a>Структура OSINFO
Содержит подробную информацию об операционной системе для сборки или модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`dwOSPlatformId`|Одно из значений идентификатора, `GetVersionEx`определяемое функцией платформы Microsoft Windows. Поддерживаются следующие значения.<br /><br /> - VER_PLATFORM_WIN32s, или 0x0000, чтобы указать Microsoft Windows 3.1.<br />- VER_PLATFORM_WIN32_WINDOWS, или 0x0001, чтобы указать Windows 95, Windows 98, или операционные системы произошли от них.<br />- VER_PLATFORM_WIN32_NT, или 0x0002, чтобы указать Windows NT или операционные системы произошли от него.|  
|`dwOSMajorVersion`|Основная версия операционной системы, или значение NULL для обозначения любой версии.|  
|`dwOSMinorVersion`|Незначительная версия операционной системы, или значение NULL для обозначения любой версии.|  
  
## <a name="remarks"></a>Remarks  
 `OSINFO`основанна на `OSVERSIONINFOEX` структуре, которая используется при вызовах к функции `GetVersionEx`платформы Microsoft Windows. Эта структура используется структурой ASSEMBLYMETADATA для обозначения поддержки операционной системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
