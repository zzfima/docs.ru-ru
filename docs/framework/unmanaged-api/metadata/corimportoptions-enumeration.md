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
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442840"
---
# <a name="corimportoptions-enumeration"></a>Перечисление CorImportOptions
Содержит значения флага, управляющие поведением во время импорта сборки за пределы текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDImportOptionDefault`|Указывает поведение по умолчанию, которое пропускает удаленные записи.|  
|`MDImportOptionAll`|Указывает, что необходимо перечислить все метаданные.|  
|`MDImportOptionAllTypeDefs`|Указывает, что необходимо перечислить все определения типов, включая удаленные.|  
|`MDImportOptionAllMethodDefs`|Указывает, что необходимо перечислить все Месоддефс, включая удаленные.|  
|`MDImportOptionAllFieldDefs`|Указывает, что необходимо перечислить все Фиелддефс, включая удаленные.|  
|`MDImportOptionAllProperties`|Указывает, что необходимо перечислить все Пропертидефс, включая удаленные.|  
|`MDImportOptionAllEvents`|Указывает, что необходимо перечислить все Евентдефс, включая удаленные.|  
|`MDImportOptionAllCustomAttributes`|Указывает, что необходимо перечислить все настраиваемые атрибуты, включая удаленные.|  
|`MDImportOptionAllExportedTypes`|Указывает, что должны быть перечислены все экспортированные типы, включая удаленные.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
