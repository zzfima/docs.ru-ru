---
title: Метод ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e851cf16e4b23b1f8510c4d96b23c01eb726a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438058"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Метод ICorRuntimeHost::CreateDomainEx
Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain>, чтобы экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType>. Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращенного <xref:System._AppDomain> экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzFriendlyName`  
 [in] Необязательный параметр используется, чтобы дать понятное имя для домена. Это понятное имя может отображаться в пользовательском интерфейсе, такие как отладчики для определения домена.  
  
 `pSetup`  
 [in] Указатель на дополнительный интерфейс типа `IAppDomainSetup`, полученного путем вызова [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) метод.  
  
 `pIdentityArray`  
 [in] Необязательный массив указателей на `IIdentity` экземпляры, которые представляют свидетельство, отображаемое через политику безопасности, чтобы установить набор разрешений. `IIdentity` Объекта можно получить, вызвав [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) метод.  
  
 `pAppDomain`  
 [out] Указатель на интерфейс типа <xref:System._AppDomain> к экземпляру <xref:System.AppDomain?displayProperty=nameWithType> может использоваться для последующего управления домена.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Неизвестный, Разрушительный сбой. Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 `CreateDomainEx` расширяет возможности [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передать в `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версия платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [Метод CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)  
 [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
