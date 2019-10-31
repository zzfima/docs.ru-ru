---
title: Перечисление EHostBindingPolicyModifyFlags
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129448"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>Перечисление EHostBindingPolicyModifyFlags
Позволяет узлу указать тип перенаправления, которое должна выполнять среда CLR при применении изменений политики из исходной сборки к целевой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Указывает, что среда CLR будет связывать значения политики исходной сборки с целевыми сборками.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Указывает, что среда CLR будет выполнять действие по умолчанию.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Указывает, что среда CLR будет задавать максимальные значения политики для целевой сборки.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Указывает, что среда CLR заменит значения политики целевой сборки значениями из исходной сборки.|  
  
## <a name="remarks"></a>Заметки  
 Метод [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) принимает параметр типа `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
