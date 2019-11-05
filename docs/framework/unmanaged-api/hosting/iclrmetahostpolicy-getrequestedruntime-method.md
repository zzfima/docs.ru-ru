---
title: Метод ICLRMetaHostPolicy::GetRequestedRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
ms.openlocfilehash: 1b07029990ef529ded57bc569beff1061ad0f938
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140869"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>Метод ICLRMetaHostPolicy::GetRequestedRuntime

Предоставляет интерфейс для предпочитаемой версии общеязыковой среды выполнения (CLR) на основе политики размещения, управляемой сборки, строки версии и потока конфигурации. Этот метод не выполняет фактическую загрузку или активацию среды CLR, но просто возвращает интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , представляющий результат политики. Этот метод заменяет методы [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [жетрекуестедрунтимеверсион](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [корбиндторунтимехост](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [корбиндторунтимебикфг](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)и [жеткоррекуиредверсион](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a>Параметры

|Название|Описание|
|----------|-----------------|
|`dwPolicyFlags`|[in] Обязательный. Указывает член перечисления [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) , представляющий политику привязки, и любое количество модификаторов. Единственной доступной в данный момент политикой является [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).<br /><br /> К модификаторам относятся [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md)и [METAHOST_POLICY_ ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).|
|`pwzBinary`|[в] Необязательно. Задает путь к файлу сборки.|
|`pCfgStream`|[в] Необязательно. Задает файл конфигурации в виде <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|`pwzVersion`|[in, out] Необязательный. Задает или возвращает предпочтительную версию среды CLR для загрузки.|
|`pcchVersion`|[in, out] Обязательный. Указывает ожидаемый размер `pwzVersion` в качестве входных данных для предотвращения переполнения буфера. Если `pwzVersion` имеет значение NULL, `pcchVersion` содержит ожидаемый размер `pwzVersion` при возвращении значения `GetRequestedRuntime`, чтобы разрешить предварительное выделение; в противном случае `pcchVersion` содержит число символов, записанных в `pwzVersion`.|
|`pwzImageVersion`|[out] Необязательный. При возвращении `GetRequestedRuntime` содержит версию среды CLR, соответствующую возвращаемому интерфейсу [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .|
|`pcchImageVersion`|[in, out] Необязательный. Указывает размер `pwzImageVersion` в качестве входных данных для предотвращения переполнения буфера. Если `pwzImageVersion` имеет значение NULL, `pcchImageVersion` содержит требуемый размер `pwzImageVersion` при возвращении значения `GetRequestedRuntime`, чтобы разрешить предварительное выделение.|
|`pdwConfigFlags`|[out] Необязательный. Если `GetRequestedRuntime` использует файл конфигурации в процессе привязки, то при возвращении `pdwConfigFlags` содержит значение [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) , указывающее, установлен ли в элементе [> запуска\<](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) набор атрибутов `useLegacyV2RuntimeActivationPolicy`, а также значение атрибут. Примените маску [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) к `pdwConfigFlags`, чтобы получить значения, относящиеся к `useLegacyV2RuntimeActivationPolicy`.|
|`riid`|окне Указывает идентификатор интерфейса IID_ICLRRuntimeInfo для запрошенного интерфейса [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .|
|`ppRuntime`|заполняет При возвращении `GetRequestedRuntime` содержит указатель на соответствующий интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .|

## <a name="remarks"></a>Заметки

После успешного завершения этого метода имеет место его побочный эффект в виде объединения дополнительных флагов с текущими флагами запуска по умолчанию из возвращенного интерфейса среды выполнения тогда и только тогда, когда один или несколько из следующих элементов существуют в потоке конфигурации в разделе `<configuration><runtime>`.

- `<gcServer enabled="true"/>` приводит к заданию `STARTUP_SERVER_GC`.

- `<etwEnable enabled="true"/>` приводит к заданию `STARTUP_ETW`.

- `<appDomainResourceMonitoring enabled="true"/>` приводит к заданию `STARTUP_ARM`.

По умолчанию результирующее значение`STARTUP_FLAGS` является побитовым или сочетанием заданных значений из предыдущего списка с флагами запуска по умолчанию.

## <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.

|HRESULT|Описание|
|-------------|-----------------|
|S_OK|Метод завершился успешно.|
|E_POINTER|`pwzVersion` не равен NULL, а `pcchVersion` равен NULL.<br /><br /> \- или -<br /><br /> `pwzImageVersion` не равен NULL, а `pcchImageVersion` равен NULL.|
|E_INVALIDARG|`dwPolicyFlags` не указывает `METAHOST_POLICY_HIGHCOMPAT`.|
|ERROR_INSUFFICIENT_BUFFER|Памяти, выделенной для `pwzVersion`, недостаточно.<br /><br /> \- или -<br /><br /> Памяти, выделенной для `pwzImageVersion`, недостаточно.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` включает в себя METAHOST_POLICY_APPLY_UPGRADE_POLICY, а как `pwzVersion`, так и `pcchVersion` имеют значение NULL.|

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** Метахост. h

**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)
- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
