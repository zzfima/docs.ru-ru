---
title: Метод ICLRHostProtectionManager::SetProtectedCategories
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141038"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>Метод ICLRHostProtectionManager::SetProtectedCategories
Указывает, какие категории управляемых типов и членов следует блокировать при выполнении в частично доверенном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `categories`  
 окне Сочетание значений [еапикатегориес](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) , указывающих, какие категории управляемых типов и членов должны блокироваться в коде с частичным доверием.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Каждое значение `EApiCategories` ссылается на список управляемых типов и членов. Перечисление `EApiCategories` и метод `SetProtectedCategories` напрямую связаны с управляемым классом <xref:System.Security.Permissions.HostProtectionAttribute>, который используется для обозначения управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описанным в `EApiCategories`. Дополнительные сведения см. в разделе <xref:System.Security.Permissions.HostProtectionAttribute> и перечисление <xref:System.Security.Permissions.HostProtectionResource>, которое непосредственно соответствует `EApiCategories`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [Перечисление EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
