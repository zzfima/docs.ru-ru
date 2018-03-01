---
title: "Перечисление CorNotificationForTokenMovement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e1d3ad11867dbd06dfe3f43cc31817a44cb96d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Перечисление CorNotificationForTokenMovement
Указывает уведомления, которые будут отправлены клиенту API метаданных при возникновении маркера преобразования.  
  
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
  
|Член|Описание:|  
|------------|-----------------|  
|`MDNotifyDefault`|Отправить уведомление при `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, или `mdFieldDef` маркеры перемещения.|  
|`MDNotifyAll`|Уведомите о перемещении маркера.|  
|`MDNotifyNone`|Не уведомлять о перемещении маркера.|  
|`MDNotifyMethodDef`|Отправить уведомление при `mdMethodDef` маркера перемещения.|  
|`MDNotifyMemberRef`|Отправить уведомление при `mdMemberRef` маркера перемещения.|  
|`MDNotifyFieldDef`|Отправить уведомление при `mdFieldDef` маркера перемещения.|  
|`MDNotifyTypeRef`|Отправить уведомление при `mdTypeRef` маркера перемещения.|  
|`MDNotifyTypeDef`|Отправить уведомление при `mdTypeDef` маркера перемещения.|  
|`MDNotifyParamDef`|Отправить уведомление при `mdParamDef` маркера перемещения.|  
|`MDNotifyInterfaceImpl`|Отправить уведомление при `mdInterfaceImpl` маркера перемещения.|  
|`MDNotifyProperty`|Отправить уведомление при `mdProperty` маркера перемещения.|  
|`MDNotifyEvent`|Отправить уведомление при `mdEvent` маркера перемещения.|  
|`MDNotifySignature`|Отправить уведомление при `mdSignature` маркера перемещения.|  
|`MDNotifyTypeSpec`|Отправить уведомление при `mdTypeSpec` маркера перемещения.|  
|`MDNotifyCustomAttribute`|Отправить уведомление при `mdCustomAttribute` маркера перемещения.|  
|`MDNotifySecurityValue`|Отправить уведомление при `mdSecurityValue` маркера перемещения.|  
|`MDNotifyPermission`|Отправить уведомление при `mdPermission` маркера перемещения.|  
|`MDNotifyModuleRef`|Отправить уведомление при `mdModuleRef` маркера перемещения.|  
|`MDNotifyNameSpace`|Отправить уведомление при `mdNameSpace` маркера перемещения.|  
|`MDNotifyAssemblyRef`|Отправить уведомление при `mdAssemblyRef` маркера перемещения.|  
|`MDNotifyFile`|Отправить уведомление при `mdFile` маркера перемещения.|  
|`MDNotifyExportedType`|Отправить уведомление при `mdExportedType` маркера перемещения.|  
|`MDNotifyResource`|Отправить уведомление при `mdManifestResource` маркера перемещения.|  
  
## <a name="remarks"></a>Примечания  
 Маркер можно сопоставить повторно (иными словами переместить) во время слияния метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
