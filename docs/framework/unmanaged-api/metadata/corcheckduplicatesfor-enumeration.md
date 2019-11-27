---
title: Перечисление CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443787"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Перечисление CorCheckDuplicatesFor
Указывает маркеры метаданных, которые будут проверяться на наличие дубликатов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDDupAll`|Проверьте все маркеры метаданных на наличие дубликатов.|  
|`MDDupENC`|Не используется.|  
|`MDNoDupChecks`|Не проверяйте маркеры метаданных для дубликатов.|  
|`MDDupTypeDef`|Проверьте наличие дубликатов токенов `mdTypeDef`.|  
|`MDDupInterfaceImpl`|Проверьте наличие дубликатов токенов `mdInterfaceImpl`.|  
|`MDDupMethodDef`|Проверьте наличие дубликатов токенов `mdMethodDef`.|  
|`MDDupTypeRef`|Проверьте наличие дубликатов токенов `mdTypeRef`.|  
|`MDDupMemberRef`|Проверьте наличие дубликатов токенов `mdMemberRef`.|  
|`MDDupCustomAttribute`|Проверьте наличие дубликатов токенов `mdCustomAttribute`.|  
|`MDDupParamDef`|Проверьте наличие дубликатов токенов `mdParamDef`.|  
|`MDDupPermission`|Проверьте наличие дубликатов токенов `mdPermission`.|  
|`MDDupProperty`|Проверьте наличие дубликатов токенов `mdProperty`.|  
|`MDDupEvent`|Проверьте наличие дубликатов токенов `mdEvent`.|  
|`MDDupFieldDef`|Проверьте наличие дубликатов токенов `mdFieldDef`.|  
|`MDDupSignature`|Проверьте наличие дубликатов токенов `mdSignature`.|  
|`MDDupModuleRef`|Проверьте наличие дубликатов токенов `mdModuleRef`.|  
|`MDDupTypeSpec`|Проверьте наличие дубликатов токенов `mdTypeSpec`.|  
|`MDDupImplMap`|Проверьте наличие дубликатов токенов `mdImplMap`.|  
|`MDDupAssemblyRef`|Проверьте наличие дубликатов токенов `mdAssemblyRef`.|  
|`MDDupFile`|Проверьте наличие дубликатов токенов `mdFile`.|  
|`MDDupExportedType`|Проверьте наличие дубликатов токенов `mdExportedType`.|  
|`MDDupManifestResource`|Проверьте наличие дубликатов токенов `mdManifestResource`.|  
|`MDDupGenericParam`|Проверьте наличие дубликатов токенов `mdGenericParam`.|  
|`MDDupMethodSpec`|Проверьте наличие дубликатов токенов `mdMethodSpec`.|  
|`MDDupGenericParamConstraint`|Проверьте наличие дубликатов токенов `mdGenericParamConstraint`.|  
|`MDDupAssembly`|Проверьте наличие дубликатов токенов `mdAssembly`.|  
|`MDDupDefault`|Проверьте наличие дубликатов `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`и маркеров `mdMethodSpec`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
