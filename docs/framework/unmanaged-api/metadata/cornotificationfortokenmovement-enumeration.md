---
title: Перечисление CorNotificationForTokenMovement
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15c5e8b34f2748868611bd7dc47ef73c491b1338
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045439"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Перечисление CorNotificationForTokenMovement
Указывает уведомления, которые будут отправляться клиенту метаданных API, когда происходит новое сопоставление маркеров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDNotifyDefault`|Отправить уведомление при `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, или `mdFieldDef` токенов перемещения.|  
|`MDNotifyAll`|Уведомлять о перемещении маркера.|  
|`MDNotifyNone`|Не уведомлять о перемещении маркера.|  
|`MDNotifyMethodDef`|Уведомлять, если `mdMethodDef` маркер перемещения.|  
|`MDNotifyMemberRef`|Уведомлять, если `mdMemberRef` маркер перемещения.|  
|`MDNotifyFieldDef`|Уведомлять, если `mdFieldDef` маркер перемещения.|  
|`MDNotifyTypeRef`|Уведомлять, если `mdTypeRef` маркер перемещения.|  
|`MDNotifyTypeDef`|Уведомлять, если `mdTypeDef` маркер перемещения.|  
|`MDNotifyParamDef`|Уведомлять, если `mdParamDef` маркер перемещения.|  
|`MDNotifyInterfaceImpl`|Уведомлять, если `mdInterfaceImpl` маркер перемещения.|  
|`MDNotifyProperty`|Уведомлять, если `mdProperty` маркер перемещения.|  
|`MDNotifyEvent`|Уведомлять, если `mdEvent` маркер перемещения.|  
|`MDNotifySignature`|Уведомлять, если `mdSignature` маркер перемещения.|  
|`MDNotifyTypeSpec`|Уведомлять, если `mdTypeSpec` маркер перемещения.|  
|`MDNotifyCustomAttribute`|Уведомлять, если `mdCustomAttribute` маркер перемещения.|  
|`MDNotifySecurityValue`|Уведомлять, если `mdSecurityValue` маркер перемещения.|  
|`MDNotifyPermission`|Уведомлять, если `mdPermission` маркер перемещения.|  
|`MDNotifyModuleRef`|Уведомлять, если `mdModuleRef` маркер перемещения.|  
|`MDNotifyNameSpace`|Уведомлять, если `mdNameSpace` маркер перемещения.|  
|`MDNotifyAssemblyRef`|Уведомлять, если `mdAssemblyRef` маркер перемещения.|  
|`MDNotifyFile`|Уведомлять, если `mdFile` маркер перемещения.|  
|`MDNotifyExportedType`|Уведомлять, если `mdExportedType` маркер перемещения.|  
|`MDNotifyResource`|Уведомлять, если `mdManifestResource` маркер перемещения.|  
  
## <a name="remarks"></a>Примечания  
 Маркер может быть повторно сопоставлен (которые перемещаются) во время слияния метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
