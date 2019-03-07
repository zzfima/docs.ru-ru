---
title: Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd725f7468b26f9d8af3d7928b9df6fbefd93b6f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502505"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>Метод ICLRDomainManager::SetPropertiesForDefaultAppDomain
Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `nProperties`  
 [in] Количество записей в `pwszPropertyNames` и `pwszPropertyValues`.  
  
 `pwszPropertyNames`  
 [in] Массив имен свойств или значение null, если свойства отсутствуют. В настоящее время единственное свойство, распознаваемый этот метод называется «PARTIAL_TRUST_VISIBLE_ASSEMBLIES».  
  
 `pwszPropertyValues`  
 [in] Массив значений свойств, или значение null, если свойства отсутствуют.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` включает в себя имя свойства, которое не распознается этим методом.|  
  
## <a name="remarks"></a>Примечания  
 Значение свойства для «PARTIAL_TRUST_VISIBLE_ASSEMBLIES» приведен список сборок, имеющих условное <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA) с <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> флаг, который будут сделаны видимыми для частично доверенных вызывающих объектов в приложении по умолчанию домен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Интерфейс ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
