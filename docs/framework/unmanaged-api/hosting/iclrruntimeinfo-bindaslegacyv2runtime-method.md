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
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120258"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
Привязывает текущую среду выполнения для всех устаревших решений политики активации среды CLR версии 2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие определенные значения HRESULT:  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Либо привязка выполнена успешно, либо эта среда выполнения уже была привязана к устаревшей среде выполнения политики активации CLR версии 2.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.|  
  
## <a name="remarks"></a>Заметки  
 Если текущая среда выполнения уже привязана для всех устаревших решений политики активации CLR версии 2 (например, с помощью атрибута `useLegacyV2RuntimeActivationPolicy` в [элементе\<startup >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки. Вместо этого результатом будет значение S_OK, точно так же, как если бы метод успешно привязать устаревшую политику активации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [Элемент \<startup>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
