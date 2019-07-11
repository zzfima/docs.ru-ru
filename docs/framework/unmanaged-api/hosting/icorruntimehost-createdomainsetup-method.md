---
title: Метод ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f8e9284283247ec46a225470ae3063dac539f43
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780018"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>Метод ICorRuntimeHost::CreateDomainSetup
Возвращает указатель интерфейса типа IAppDomainSetup для <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра. `IAppDomainSetup` Предоставляет методы для настройки аспектов домена приложения, прежде чем она создается.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomainSetup`  
 [out] Указатель интерфейса на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра. Этот параметр имеет тип `IUnknown`, поэтому вызывающие объекты обычно должен вызвать `QueryInterface` на этот указатель для получения указателя интерфейса типа `IAppDomainSetup`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная, разрушительного сбоя. Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
  
## <a name="remarks"></a>Примечания  
 Указатель, возвращенный из этого метода обычно передается в качестве параметра [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
