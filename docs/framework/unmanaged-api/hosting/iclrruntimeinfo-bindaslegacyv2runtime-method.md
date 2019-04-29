---
title: Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 647c87b6f42b01922a385d502d72410af3140cd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771791"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
Привязывает текущую среду выполнения для всех устаревших распространенных языка среды выполнения (CLR) версии 2 активации решения на основе политик.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие специфичные результаты HRESULT:  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Привязка выполнена успешно, либо эта среда выполнения уже были привязаны как старой среды выполнения CLR версии 2 активации политики.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другие среды выполнения уже была привязана к устаревшая политика активации 2 версии среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Если для всех предыдущих версий среды CLR версии 2 решений политики активации уже привязано текущей среды выполнения (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; Вместо этого возвращается значение S_OK, так же, как было бы, если метод успешно привязал устаревшей политике активации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Элемент \<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
