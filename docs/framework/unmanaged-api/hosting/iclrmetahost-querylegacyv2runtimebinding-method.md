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
ms.openlocfilehash: 90474a61b16d65565889bd69ef75616804d8bc60
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140883"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a>Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
Возвращает интерфейс, представляющий среду выполнения, к которой привязана политика устаревшей активации, например, с помощью атрибута `useLegacyV2RuntimeActivationPolicy` в записи файла конфигурации [элемента\<startup >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) , путем прямого использования API-интерфейсов активации прежних версий или путем вызова метода [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Параметры  
 `riid`  
 окне Обязательно. в настоящее время для этого параметра допустимо только значение `IID_ICLRRuntimeInfo`.  
  
 `ppUnk`  
 [out] Обязательный. При возврате из этого метода содержит указатель на интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , представляющий среду выполнения, привязанную к устаревшей политике активации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод успешно выполнен, и возвращена среда выполнения, которая была привязана к устаревшей политике активации.|  
|S_FALSE|Метод успешно выполнен, но устаревшая среда выполнения еще не привязана.|  
|E_NOINTERFACE|Метод обнаружил среду выполнения, которая была привязана к устаревшей политике активации, но параметр `riid` не поддерживается этой средой.|  
  
## <a name="remarks"></a>Заметки  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
