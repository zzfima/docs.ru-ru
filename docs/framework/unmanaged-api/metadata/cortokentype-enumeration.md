---
title: Перечисление CorTokenType
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b33b50e53c454f2b62253d12943ea044240d8cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230516"
---
# <a name="cortokentype-enumeration"></a>Перечисление CorTokenType
Указывает тип маркера метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`mdtModule`|`mdModule` Токена.|  
|`mdtTypeRef`|`mdTypeRef` Токена.|  
|`mdtTypeDef`|`mdTypeDef` Токена.|  
|`mdtFieldDef`|`mdFieldDef` Токена.|  
|`mdtMethodDef`|`mdMethodDef` Токена.|  
|`mdtParamDef`|`mdParamDef` Токена.|  
|`mdtInterfaceImpl`|`mdInterfaceImpl` Токена.|  
|`mdtMemberRef`|`mdMemberRef` Токена.|  
|`mdtCustomAttribute`|`mdCustomAttribute` Токена.|  
|`mdtPermission`|`mdPermission` Токена.|  
|`mdtSignature`|`mdSignature` Токена.|  
|`mdtEvent`|`mdEvent` Токена.|  
|`mdtProperty`|`mdProperty` Токена.|  
|`mdtModuleRef`|`mdModuleRef` Токена.|  
|`mdtTypeSpec`|`mdTypeSpec` Токена.|  
|`mdtAssembly`|`mdAssembly` Токена.|  
|`mdtAssemblyRef`|`mdAssemblyRef` Токена.|  
|`mdtFile`|`mdFile` Токена.|  
|`mdtExportedType`|`mdExportedType` Токена.|  
|`mdtManifestResource`|`mdManifestResource` Токена.|  
|`mdtGenericParam`|`mdGenericParam` Токена.|  
|`mdtMethodSpec`|`mdMethodSpec` Токена.|  
|`mdtGenericParamConstraint`|`mdGenericParamConstraint` Токена.|  
|`mdtString`|`mdString` Токена.|  
|`mdtName`|`mdName` Токена.|  
|`mdtBaseType`|Не используется.|  
  
## <a name="remarks"></a>Примечания  
 Каждое значение равно значению старший байт в соответствующий маркер метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
