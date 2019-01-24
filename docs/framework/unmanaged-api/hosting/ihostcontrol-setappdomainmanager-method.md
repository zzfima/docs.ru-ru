---
title: Метод IHostControl::SetAppDomainManager
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fd0cf4f47781afb397c1fdd4b42715c710982e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580763"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>Метод IHostControl::SetAppDomainManager
Уведомляет ведущее приложение для создания домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwAppDomainID`  
 [in] Числовой идентификатор выбранного <xref:System.AppDomain>.  
  
 `pUnkAppDomainManager`  
 [in] Указатель на <xref:System.AppDomainManager> объект, реализующий узла как `IUnknown`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 <xref:System.AppDomainManager> Предоставляет механизм для начальной загрузки в управляемый код, так и для управления созданием и параметры каждого основному <xref:System.AppDomain>. <xref:System.AppDomainManager> Загружается в каждом <xref:System.AppDomain> при, <xref:System.AppDomain> создается. Если это предусмотрено, среда CLR Уведомляет основное приложение создания домена приложения, задав значение `pUnkAppDomainManager` параметра.  
  
 В своей реализации `SetAppDomainManager` метод, узел можно задать имя сборки и тип для домена приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [Интерфейс IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
