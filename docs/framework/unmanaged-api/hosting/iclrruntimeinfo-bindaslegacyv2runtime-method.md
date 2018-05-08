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
ms.openlocfilehash: 690287bf54f98c19298504ee3058a59ef88a87f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
Привязывает текущую среду выполнения для всех устаревших общих языка среды CLR версии 2 решений политики активации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT:  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Привязка выполнена успешно, либо эта среда выполнения уже были привязаны как устаревшие версии 2 активации политики среды CLR.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другая среда выполнения уже была привязана к прежних версий среды CLR политике активации версии 2.|  
  
## <a name="remarks"></a>Примечания  
 Если текущей среды выполнения уже связана со всех предыдущих версий среды CLR версии 2 решений политики активации (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; Вместо этого результатом является значение S_OK, так же, как было бы, если метод успешно привязал устаревшей политике активации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [Элемент \<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
