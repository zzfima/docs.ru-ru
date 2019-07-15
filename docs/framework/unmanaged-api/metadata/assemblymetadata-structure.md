---
title: Структура ASSEMBLYMETADATA
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5039117c649943a1f05a91ecccf22eb4230e5e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776375"
---
# <a name="assemblymetadata-structure"></a>Структура ASSEMBLYMETADATA
Содержит сведения о сборке, на которую указывает ссылка, включая ее версию и уровень поддержки языковых стандартов, процессоры и операционные системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`usMajorVersion`|Основной номер версии сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если все биты `usMajorVersion` задаются, основной номер версии не указан.|  
|`usMinorVersion`|Дополнительный номер версии сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если все биты `usMinorVersion` задаются, дополнительный номер версии не указан.|  
|`usBuildNumber`|Номер построения сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если все биты `usBuildNumber` задаются, номер сборки не указан.|  
|`usRevisionNumber`|Номер редакции сборки, на которую указывает ссылка. Это значение не может быть нулевым. Если все биты `usRevisionNumber` задаются, не указан номер редакции.|  
|`szLocale`|Список имен языковых стандартов, выполняет существующую спецификацию RFC1766, разделенных точкой с запятой, указав языки, поддерживаемые сборкой, на которую указывает ссылка. Значение null указывает на независимость от языкового стандарта. **Примечание.**  В .NET Framework версии 1.0, нельзя указать более одного языкового стандарта.|  
|`cbLocale`|Размер в расширенных символах `szLocale`.|  
|`rdwProcessor`|Массив идентификаторов, как определено в заголовке Winnt.h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от процессора.|  
|`ulProcessor`|Длина `rdwProcessor` массива.|  
|`rOS`|Массив [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) экземпляров, задающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от операционной системы.|  
|`ulOS`|Длина `rOS` массива.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Структура OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
