---
title: Перечисление EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0175ab1d06a8166a5bbfd0c42018085a801740f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="einitializenewdomainflags-enumeration"></a>Перечисление EInitializeNewDomainFlags
Ведущее приложение может предоставлять среде выполнения сведения об инициализации домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Флаги не.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Информирует общеязыковой среды выполнения (CLR), что узел не внесет изменений в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> метод.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) метод принимает параметр типа `EInitializeNewDomainFlags`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [Метод SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
