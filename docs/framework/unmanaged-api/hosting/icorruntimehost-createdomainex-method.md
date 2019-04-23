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
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158929"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Метод ICorRuntimeHost::CreateDomainEx
Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain>, чтобы экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType>. Этот метод позволяет вызывающей стороне передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращенного <xref:System._AppDomain> экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzFriendlyName`  
 [in] Необязательный параметр, используемый нужно присвоить понятное имя домена. Это понятное имя может отображаться в пользовательском интерфейсе, такие как отладчики для определения домена.  
  
 `pSetup`  
 [in] Указатель необязательный интерфейс типа `IAppDomainSetup`достигается путем вызова [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) метод.  
  
 `pIdentityArray`  
 [in] Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное посредством политики безопасности для установления набора разрешений. `IIdentity` Может быть получен путем вызова [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) метод.  
  
 `pAppDomain`  
 [out] Указатель интерфейса типа <xref:System._AppDomain> к экземпляру <xref:System.AppDomain?displayProperty=nameWithType> , можно использовать для последующего управления домена.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная, разрушительного сбоя. Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 `CreateDomainEx` расширяет возможности [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передать в `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Метод CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
