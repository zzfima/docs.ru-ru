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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a82ce9709e008e092c5f31372a89bf9a16e1f88b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767014"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Перечисление CorCheckDuplicatesFor
Указывает, будет проверить наличие дублирующихся маркеры метаданных.  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDDupAll`|Проверьте все токены метаданных повторяющихся значений.|  
|`MDDupENC`|Не используется.|  
|`MDNoDupChecks`|Не устанавливайте флажок Поиск дубликатов маркеров метаданных.|  
|`MDDupTypeDef`|Выполните поиск дубликатов `mdTypeDef` маркеры.|  
|`MDDupInterfaceImpl`|Выполните поиск дубликатов `mdInterfaceImpl` маркеры.|  
|`MDDupMethodDef`|Выполните поиск дубликатов `mdMethodDef` маркеры.|  
|`MDDupTypeRef`|Выполните поиск дубликатов `mdTypeRef` маркеры.|  
|`MDDupMemberRef`|Выполните поиск дубликатов `mdMemberRef` маркеры.|  
|`MDDupCustomAttribute`|Выполните поиск дубликатов `mdCustomAttribute` маркеры.|  
|`MDDupParamDef`|Выполните поиск дубликатов `mdParamDef` маркеры.|  
|`MDDupPermission`|Выполните поиск дубликатов `mdPermission` маркеры.|  
|`MDDupProperty`|Выполните поиск дубликатов `mdProperty` маркеры.|  
|`MDDupEvent`|Выполните поиск дубликатов `mdEvent` маркеры.|  
|`MDDupFieldDef`|Выполните поиск дубликатов `mdFieldDef` маркеры.|  
|`MDDupSignature`|Выполните поиск дубликатов `mdSignature` маркеры.|  
|`MDDupModuleRef`|Выполните поиск дубликатов `mdModuleRef` маркеры.|  
|`MDDupTypeSpec`|Выполните поиск дубликатов `mdTypeSpec` маркеры.|  
|`MDDupImplMap`|Выполните поиск дубликатов `mdImplMap` маркеры.|  
|`MDDupAssemblyRef`|Выполните поиск дубликатов `mdAssemblyRef` маркеры.|  
|`MDDupFile`|Выполните поиск дубликатов `mdFile` маркеры.|  
|`MDDupExportedType`|Выполните поиск дубликатов `mdExportedType` маркеры.|  
|`MDDupManifestResource`|Выполните поиск дубликатов `mdManifestResource` маркеры.|  
|`MDDupGenericParam`|Выполните поиск дубликатов `mdGenericParam` маркеры.|  
|`MDDupMethodSpec`|Выполните поиск дубликатов `mdMethodSpec` маркеры.|  
|`MDDupGenericParamConstraint`|Выполните поиск дубликатов `mdGenericParamConstraint` маркеры.|  
|`MDDupAssembly`|Выполните поиск дубликатов `mdAssembly` маркеры.|  
|`MDDupDefault`|Выполните поиск дубликатов `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, и `mdMethodSpec` маркеров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
