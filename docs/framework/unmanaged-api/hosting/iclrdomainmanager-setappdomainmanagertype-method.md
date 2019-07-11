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
ms.openlocfilehash: 28feddffff7dc5dba1860b3d2d1327a17bd08190
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772946"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>Метод ICLRDomainManager::SetAppDomainManagerType
Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класс диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.  
  
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
 [in] Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: «AdMgrExample, версия = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3».  
  
 `wszAppDomainManagerType`  
 [in] Имя типа диспетчера домена приложения, включая пространство имен.  
  
 `dwInitializeDomainFlags`  
 [in] Сочетание [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) значений перечисления, предоставляющая сведения о диспетчера доменов приложений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 В настоящее время единственное определенное значение для `dwInitializeDomainFlags` — `eInitializeNewDomainFlags_NoSecurityChanges`, которое сообщает общеязыковой среды выполнения (CLR), что диспетчер домена приложения не будет изменять параметры безопасности во время выполнения <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод. Это позволяет среде CLR для оптимизации загрузки сборок, которые имеют условное <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA). Это может привести к значительному улучшению время запуска при большом транзитивное замыкание этот набор сборок.  
  
> [!IMPORTANT]
>  Если узел указывает `eInitializeNewDomainFlags_NoSecurityChanges` для домена приложения, <xref:System.InvalidOperationException> возникает, если все возможные попытки для изменения уровня безопасности домена приложения.  
  
 Вызов [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)метода эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Интерфейс ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [Перечисление EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
