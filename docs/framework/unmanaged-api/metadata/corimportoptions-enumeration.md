---
title: Перечисление CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2f71a277484adbbfe3628222c635528cdab03e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045751"
---
# <a name="corimportoptions-enumeration"></a>Перечисление CorImportOptions
Содержит значения флага, управляющие поведением во время импорта сборки за пределы текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDImportOptionDefault`|Указывает поведение по умолчанию, которое является пропуск удаленных записей.|  
|`MDImportOptionAll`|Указывает, что должны быть перечислены все метаданные.|  
|`MDImportOptionAllTypeDefs`|Указывает, что должны быть перечислены все определения типов, включая удаленные.|  
|`MDImportOptionAllMethodDefs`|Указывает, что должны быть перечислены все маркеры MethodDef, включая удаленные.|  
|`MDImportOptionAllFieldDefs`|Указывает, что должны быть перечислены все маркеры FieldDef, включая удаленные.|  
|`MDImportOptionAllProperties`|Указывает, что должны быть перечислены все маркеры PropertyDef, включая удаленные.|  
|`MDImportOptionAllEvents`|Указывает, что должны быть перечислены все маркеры EventDef, включая удаленные.|  
|`MDImportOptionAllCustomAttributes`|Указывает, что должны быть перечислены все настраиваемые атрибуты, включая удаленные.|  
|`MDImportOptionAllExportedTypes`|Указывает, что должны быть перечислены все экспортируемые типы, включая удаленные.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
