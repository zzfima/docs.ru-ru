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
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450156"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Перечисление CorNotificationForTokenMovement
Указывает уведомления, которые будут отправляться клиенту API метаданных при выполнении сопоставления маркеров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDNotifyDefault`|Уведомлять при перемещении маркеров `mdTypeRef`, `mdMethodDef`, `mdMemberRef`или `mdFieldDef`.|  
|`MDNotifyAll`|Уведомлять при перемещении токена.|  
|`MDNotifyNone`|Не уведомлять при перемещении токенов.|  
|`MDNotifyMethodDef`|Уведомлять при перемещении маркера `mdMethodDef`.|  
|`MDNotifyMemberRef`|Уведомлять при перемещении маркера `mdMemberRef`.|  
|`MDNotifyFieldDef`|Уведомлять при перемещении маркера `mdFieldDef`.|  
|`MDNotifyTypeRef`|Уведомлять при перемещении маркера `mdTypeRef`.|  
|`MDNotifyTypeDef`|Уведомлять при перемещении маркера `mdTypeDef`.|  
|`MDNotifyParamDef`|Уведомлять при перемещении маркера `mdParamDef`.|  
|`MDNotifyInterfaceImpl`|Уведомлять при перемещении маркера `mdInterfaceImpl`.|  
|`MDNotifyProperty`|Уведомлять при перемещении маркера `mdProperty`.|  
|`MDNotifyEvent`|Уведомлять при перемещении маркера `mdEvent`.|  
|`MDNotifySignature`|Уведомлять при перемещении маркера `mdSignature`.|  
|`MDNotifyTypeSpec`|Уведомлять при перемещении маркера `mdTypeSpec`.|  
|`MDNotifyCustomAttribute`|Уведомлять при перемещении маркера `mdCustomAttribute`.|  
|`MDNotifySecurityValue`|Уведомлять при перемещении маркера `mdSecurityValue`.|  
|`MDNotifyPermission`|Уведомлять при перемещении маркера `mdPermission`.|  
|`MDNotifyModuleRef`|Уведомлять при перемещении маркера `mdModuleRef`.|  
|`MDNotifyNameSpace`|Уведомлять при перемещении маркера `mdNameSpace`.|  
|`MDNotifyAssemblyRef`|Уведомлять при перемещении маркера `mdAssemblyRef`.|  
|`MDNotifyFile`|Уведомлять при перемещении маркера `mdFile`.|  
|`MDNotifyExportedType`|Уведомлять при перемещении маркера `mdExportedType`.|  
|`MDNotifyResource`|Уведомлять при перемещении маркера `mdManifestResource`.|  
  
## <a name="remarks"></a>Примечания  
 Маркер может быть повторно сопоставлен (т. е. перемещен) во время слияния метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
