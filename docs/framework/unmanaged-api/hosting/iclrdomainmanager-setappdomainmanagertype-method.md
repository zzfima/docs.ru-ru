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
ms.openlocfilehash: ea10f9b7d23d8ca6a94d05cac6e586b434c000d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435547"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Метод ICLRDomainManager::SetAppDomainManagerType
Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `wszAppDomainManagerAssembly`  
 [in] Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: «AdMgrExample, Version = 1.0.0.0, язык и региональные параметры = neutral, PublicKeyToken = 6856bccf150f00b3».  
  
 `wszAppDomainManagerType`  
 [in] Имя типа диспетчера домена приложения, включая пространство имен.  
  
 `dwInitializeDomainFlags`  
 [in] Сочетание [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) значений перечисления, предоставляющих сведения о диспетчере домена приложения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 В настоящее время единственным пользователем значение для `dwInitializeDomainFlags` — `eInitializeNewDomainFlags_NoSecurityChanges`, который сообщает среде (CLR), диспетчер домена приложения, не изменяйте параметры безопасности во время выполнения <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод. Это позволяет среде CLR для оптимизации загрузки сборок, содержащих условной <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA). Это может привести к существенным усовершенствованием времени запуска, если транзитивное замыкание этого набора сборок имеет большой размер.  
  
> [!IMPORTANT]
>  Если узел указывает `eInitializeNewDomainFlags_NoSecurityChanges` для домена приложения <xref:System.InvalidOperationException> создается, если все попытки изменения уровня безопасности домена приложения.  
  
 Вызов [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)метода эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [Интерфейс ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [Перечисление EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
