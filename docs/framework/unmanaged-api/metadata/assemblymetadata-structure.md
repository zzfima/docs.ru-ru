---
title: "Структура ASSEMBLYMETADATA"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLYMETADATA
api_location: mscoree.dll
api_type: COM
f1_keywords: ASSEMBLYMETADATA
helpviewer_keywords: ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5652907abc17868414c554cb5c87b0856d2c5a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assemblymetadata-structure"></a>Структура ASSEMBLYMETADATA
Содержит сведения о ссылочной сборки, включая его версии, уровне поддержки языковых стандартов, процессоры и операционные системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`usMajorVersion`|Основной номер версии сборки. Это значение не может быть нулевым. Если все биты `usMajorVersion` настраиваются, основной номер версии не указан.|  
|`usMinorVersion`|Дополнительный номер версии сборки. Это значение не может быть нулевым. Если все биты `usMinorVersion` настраиваются, дополнительный номер версии не указан.|  
|`usBuildNumber`|Номер построения сборки. Это значение не может быть нулевым. Если все биты `usBuildNumber` настраиваются, номер сборки не указан.|  
|`usRevisionNumber`|Номер редакции сборки. Это значение не может быть нулевым. Если все биты `usRevisionNumber` настраиваются, номер редакции не определен.|  
|`szLocale`|Список имен языкового стандарта существующую спецификацию RFC1766, разделенных точкой с запятой, указав языковые стандарты, поддерживаемые сборкой, на которую указывает ссылка. Значение null указывает на независимость от языкового стандарта. **Примечание:** в .NET Framework версии 1.0, нельзя указать несколько языковых стандартов.|  
|`cbLocale`|Размер в расширенных символах с `szLocale`.|  
|`rdwProcessor`|Массив идентификаторов, определенный в заголовке Winnt.h, для типов процессоров, поддерживаемых сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от процессора.|  
|`ulProcessor`|Длина `rdwProcessor` массива.|  
|`rOS`|Массив [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) экземпляров, задающих операционные системы, поддерживаемые сборкой, на которую указывает ссылка. Значение NULL указывает на независимость от операционной системы.|  
|`ulOS`|Длина `rOS` массива.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [Структура OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
