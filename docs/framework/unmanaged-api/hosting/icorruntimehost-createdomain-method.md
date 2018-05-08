---
title: Метод ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea2353f1375667619db47ac5e1f037ce68dbded5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorruntimehostcreatedomain-method"></a>Метод ICorRuntimeHost::CreateDomain
Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> к экземпляру типа <xref:System.AppDomain?displayProperty=nameWithType>.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzFriendlyName`  
 [in] Необязательный параметр используется, чтобы дать понятное имя для домена. Это понятное имя может отображаться в пользовательском интерфейсе, такие как отладчики для определения домена.  
  
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
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
