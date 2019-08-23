---
title: Метод ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b142f1a05036eddf44c69d8b7da95091dc8f445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963093"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Метод ICLRDomainManager::SetAppDomainManagerType
Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszAppDomainManagerAssembly`  
 окне Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: "Адмгрексампле, Version = 1.0.0.0, культура = Neutral, PublicKeyToken = 6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 окне Имя типа диспетчера домена приложения, включая пространство имен.  
  
 `dwInitializeDomainFlags`  
 окне Сочетание значений перечисления [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) , которые предоставляют сведения о диспетчере доменов приложений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 В настоящее время единственным определенным значением для `dwInitializeDomainFlags` является `eInitializeNewDomainFlags_NoSecurityChanges`, которое указывает среде CLR, что диспетчер домена приложения не изменяет параметры безопасности <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> во время выполнения метода. Это позволяет среде CLR оптимизировать загрузку сборок с условным <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом (APTCA). Это может привести к значительному улучшению времени запуска, если транзитивное замыкание этого набора сборок велико.  
  
> [!IMPORTANT]
> Если узел указан `eInitializeNewDomainFlags_NoSecurityChanges` для диспетчера доменов приложений <xref:System.InvalidOperationException> , создается исключение, если выполняется любая попытка изменить безопасность домена приложения.  
  
 Вызов метода [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Метахост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Интерфейс ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [Перечисление EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
