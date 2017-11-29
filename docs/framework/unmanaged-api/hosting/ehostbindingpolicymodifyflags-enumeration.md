---
title: "Перечисление EHostBindingPolicyModifyFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ff7ec7487be649e353b48e537cf1d8d45f6962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>Перечисление EHostBindingPolicyModifyFlags
Позволяет узлу указать тип перенаправления, которую должен выполнить общеязыковой среды выполнения (CLR), при применении изменений политики из исходной сборки на целевую сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Указывает, что среда CLR присоединит значения политики исходной сборки к соответствующим целевой сборки.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Указывает, что среда CLR выполняет действие по умолчанию.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Указывает, что среда CLR будет значения политики целевой сборки максимальные значения.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Указывает, что среда CLR заменит значения политики целевой сборки с этими исходной сборки.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) метод принимает параметр типа `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Iclrhostbindingpolicymanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [Перечисления размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
