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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176192"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Перечисление CorCheckDuplicatesFor
Определяет токены метаданных, которые будут проверены на наличие дубликатов.  
  
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
  
|Участник|Описание|  
|------------|-----------------|  
|`MDDupAll`|Проверьте все токены метаданных на наличие дубликатов.|  
|`MDDupENC`|Не используется.|  
|`MDNoDupChecks`|Не проверяйте токены метаданных на наличие дубликатов.|  
|`MDDupTypeDef`|Проверьте наличие `mdTypeDef` дубликатов токенов.|  
|`MDDupInterfaceImpl`|Проверьте наличие `mdInterfaceImpl` дубликатов токенов.|  
|`MDDupMethodDef`|Проверьте наличие `mdMethodDef` дубликатов токенов.|  
|`MDDupTypeRef`|Проверьте наличие `mdTypeRef` дубликатов токенов.|  
|`MDDupMemberRef`|Проверьте наличие `mdMemberRef` дубликатов токенов.|  
|`MDDupCustomAttribute`|Проверьте наличие `mdCustomAttribute` дубликатов токенов.|  
|`MDDupParamDef`|Проверьте наличие `mdParamDef` дубликатов токенов.|  
|`MDDupPermission`|Проверьте наличие `mdPermission` дубликатов токенов.|  
|`MDDupProperty`|Проверьте наличие `mdProperty` дубликатов токенов.|  
|`MDDupEvent`|Проверьте наличие `mdEvent` дубликатов токенов.|  
|`MDDupFieldDef`|Проверьте наличие `mdFieldDef` дубликатов токенов.|  
|`MDDupSignature`|Проверьте наличие `mdSignature` дубликатов токенов.|  
|`MDDupModuleRef`|Проверьте наличие `mdModuleRef` дубликатов токенов.|  
|`MDDupTypeSpec`|Проверьте наличие `mdTypeSpec` дубликатов токенов.|  
|`MDDupImplMap`|Проверьте наличие `mdImplMap` дубликатов токенов.|  
|`MDDupAssemblyRef`|Проверьте наличие `mdAssemblyRef` дубликатов токенов.|  
|`MDDupFile`|Проверьте наличие `mdFile` дубликатов токенов.|  
|`MDDupExportedType`|Проверьте наличие `mdExportedType` дубликатов токенов.|  
|`MDDupManifestResource`|Проверьте наличие `mdManifestResource` дубликатов токенов.|  
|`MDDupGenericParam`|Проверьте наличие `mdGenericParam` дубликатов токенов.|  
|`MDDupMethodSpec`|Проверьте наличие `mdMethodSpec` дубликатов токенов.|  
|`MDDupGenericParamConstraint`|Проверьте наличие `mdGenericParamConstraint` дубликатов токенов.|  
|`MDDupAssembly`|Проверьте наличие `mdAssembly` дубликатов токенов.|  
|`MDDupDefault`|`mdMemberRef`Проверьте дубликаты, `mdSignature` `mdTypeRef` `mdTypeSpec`, `mdMethodSpec` , и жетоны.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
