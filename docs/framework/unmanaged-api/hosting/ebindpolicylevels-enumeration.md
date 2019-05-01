---
title: Перечисление EBindPolicyLevels
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985677"
---
# <a name="ebindpolicylevels-enumeration"></a>Перечисление EBindPolicyLevels
Предоставляет флаги для указания уровня, по которому следует применить или изменить политику сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Указывает, что политика должна применяться на уровне администратора.|  
|`ePolicyLevelApp`|Указывает, что политика должна применяться на уровне приложения.|  
|`ePolicyLevelHost`|Указывает, что политика должна применяться на уровне узла.|  
|`ePolicyLevelNone`|Указывает флаги не уровня политики.|  
|`ePolicyLevelPublisher`|Указывает, что политика должна применяться на уровне издателя.|  
|`ePolicyLevelRetargetable`|Указывает, что политика применяется на уровнях переменной.|  
|`ePolicyPortability`|Указывает, что политики должно поддерживать переносимости между реализациями сборки платформы .NET Framework. См. в разделе [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) элемент файла конфигурации.|  
|`ePolicyUnifiedToCLR`|Указывает, что политика должна соответствовать политике, общеязыковой среды выполнения (CLR).|  
  
## <a name="remarks"></a>Примечания  
 Это перечисление передается методам [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) интерфейс для выполнения изменений в политике приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
