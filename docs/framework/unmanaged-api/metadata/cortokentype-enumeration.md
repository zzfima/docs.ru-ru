---
title: "Перечисление CorTokenType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTokenType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTokenType
helpviewer_keywords: CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1910321942ebac26d8c377f9d156cdf97bd34b62
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`mdtModule`|`mdModule` Маркеров.|  
|`mdtTypeRef`|`mdTypeRef` Маркеров.|  
|`mdtTypeDef`|`mdTypeDef` Маркеров.|  
|`mdtFieldDef`|`mdFieldDef` Маркеров.|  
|`mdtMethodDef`|`mdMethodDef` Маркеров.|  
|`mdtParamDef`|`mdParamDef` Маркеров.|  
|`mdtInterfaceImpl`|`mdInterfaceImpl` Маркеров.|  
|`mdtMemberRef`|`mdMemberRef` Маркеров.|  
|`mdtCustomAttribute`|`mdCustomAttribute` Маркеров.|  
|`mdtPermission`|`mdPermission` Маркеров.|  
|`mdtSignature`|`mdSignature` Маркеров.|  
|`mdtEvent`|`mdEvent` Маркеров.|  
|`mdtProperty`|`mdProperty` Маркеров.|  
|`mdtModuleRef`|`mdModuleRef` Маркеров.|  
|`mdtTypeSpec`|`mdTypeSpec` Маркеров.|  
|`mdtAssembly`|`mdAssembly` Маркеров.|  
|`mdtAssemblyRef`|`mdAssemblyRef` Маркеров.|  
|`mdtFile`|`mdFile` Маркеров.|  
|`mdtExportedType`|`mdExportedType` Маркеров.|  
|`mdtManifestResource`|`mdManifestResource` Маркеров.|  
|`mdtGenericParam`|`mdGenericParam` Маркеров.|  
|`mdtMethodSpec`|`mdMethodSpec` Маркеров.|  
|`mdtGenericParamConstraint`|`mdGenericParamConstraint` Маркеров.|  
|`mdtString`|`mdString` Маркеров.|  
|`mdtName`|`mdName` Маркеров.|  
|`mdtBaseType`|Не используется.|  
  
## <a name="remarks"></a>Примечания  
 Каждое значение равно значению старшего байта в соответствующем маркере метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
