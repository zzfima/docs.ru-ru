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
ms.openlocfilehash: 81aef6beb9ee6d622519738d24fdd0a4d42a75b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136555"
---
# <a name="ebindpolicylevels-enumeration"></a>Перечисление EBindPolicyLevels
Предоставляет флаги для указания уровня применения или изменения политики сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Указывает, что политику следует применять на уровне администратора.|  
|`ePolicyLevelApp`|Указывает, что политику следует применять на уровне приложения.|  
|`ePolicyLevelHost`|Указывает, что политику следует применять на уровне узла.|  
|`ePolicyLevelNone`|Указывает отсутствие флагов уровня политики.|  
|`ePolicyLevelPublisher`|Указывает, что политика должна применяться на уровне издателя.|  
|`ePolicyLevelRetargetable`|Указывает, что политика должна быть применима на уровнях переменных.|  
|`ePolicyPortability`|Указывает, что политика должна поддерживать переносимость между реализациями сборки .NET Framework. См. раздел файла конфигурации [\<тег supportportability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) .|  
|`ePolicyUnifiedToCLR`|Указывает, что политика должна быть унифицированной для среды CLR.|  
  
## <a name="remarks"></a>Заметки  
 Это перечисление передается методам интерфейса [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) для указания изменений в политике приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
