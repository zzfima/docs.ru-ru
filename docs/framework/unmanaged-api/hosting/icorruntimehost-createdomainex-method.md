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
ms.openlocfilehash: a3a2d1827774ddedc00eb849f64256e3f425b3fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127710"
---
# <a name="icorruntimehostcreatedomainex-method"></a>Метод ICorRuntimeHost::CreateDomainEx
Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain>в экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType>. Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого экземпляра <xref:System._AppDomain>.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzFriendlyName`  
 окне Необязательный параметр, используемый для присвоения понятного имени домену. Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.  
  
 `pSetup`  
 окне Необязательный указатель интерфейса типа `IAppDomainSetup`, полученный при вызове метода [ICorRuntimeHost:: креатедомаинсетуп](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) .  
  
 `pIdentityArray`  
 окне Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное через политику безопасности для создания набора разрешений. Объект `IIdentity` можно получить, вызвав метод [креативиденце](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) .  
  
 `pAppDomain`  
 заполняет Указатель интерфейса типа <xref:System._AppDomain> на экземпляр <xref:System.AppDomain?displayProperty=nameWithType>, который может использоваться для дальнейшего управления доменом.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Заметки  
 `CreateDomainEx` расширяет возможности [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передать экземпляр `IAppDomainSetup` со значениями свойств для настройки домена приложения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версия .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Метод CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
