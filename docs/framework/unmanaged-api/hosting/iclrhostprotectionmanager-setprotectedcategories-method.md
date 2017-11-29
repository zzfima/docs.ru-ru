---
title: "Метод ICLRHostProtectionManager::SetProtectedCategories"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetProtectedCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 984a88a9b75a03f421f1dd3f834665fee932876a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Метод ICLRHostProtectionManager::SetProtectedCategories
Указывает, какие категории управляемых типов и членов должны блокироваться в частично доверенном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `categories`  
 [in] Сочетание [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) значений, указывающее, какие категории управляемых типов и членов должны блокироваться в частично доверенном коде.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories`успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Каждый `EApiCategories` значение ссылается на список управляемых типов и членов. `EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемом <xref:System.Security.Permissions.HostProtectionAttribute> класс, который используется для пометки управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описываемого `EApiCategories`. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.HostProtectionAttribute> и <xref:System.Security.Permissions.HostProtectionResource> перечисления, который напрямую соответствует идентификатору `EApiCategories`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [EApiCategories-перечисление](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Iclrhostprotectionmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
