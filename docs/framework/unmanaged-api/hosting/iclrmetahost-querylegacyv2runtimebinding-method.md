---
title: Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7312a50137ab8a5c066d5e140a1742ee1918b44
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776562"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
Возвращает интерфейс, представляющий среду выполнения, к которому устаревшей политике активации привязки, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<startup > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) запись файла конфигурации, напрямую используя Устаревшие интерфейсы API активации или вызывая [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Параметры  
 `riid`  
 [in] Единственным допустимым значением для этого параметра является Required.Currently `IID_ICLRRuntimeInfo`.  
  
 `ppUnk`  
 [out] Обязательный. При возвращении данного метода содержит указатель на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, представляющий среду выполнения, привязанное к устаревшей политике активации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод успешно выполнен, и возвращена среда выполнения, которая была привязана к устаревшей политике активации.|  
|S_FALSE|Метод успешно выполнен, но устаревшая среда выполнения еще не привязана.|  
|E_NOINTERFACE|Метод обнаружил среду выполнения, которая была привязана к устаревшей политике активации, но параметр `riid` не поддерживается этой средой.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MetaHost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
