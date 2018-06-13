---
title: Метод ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc3616b2cec0fa951df745e3c5f0468f74ab82bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435933"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Метод ICLRPolicyManager::SetActionOnFailure
Задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), если указанного сбоя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `failure`  
 [in] Один из [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значения, указывающие тип сбоя, для которого требуется выполнить действие.  
  
 `action`  
 [in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значений, указывающее действие, предпринимаемое при возникновении сбоя. Список поддерживаемых значений см. в разделе "Примечания".  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Невозможно задать действие политики для указанной операции или для операции указано недопустимое действие политики.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию среда CLR создает исключение, если ему не удалось выделить ресурс, например памяти. `SetActionOnFailure` предоставляет узлу возможность переопределить это поведение, задав действие политики при сбое. В следующей таблице показаны сочетания [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) и [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) поддерживаемые значения. (Опущена префикс FAIL_ [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) значений.)  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|CodeContract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||Н/Д||  
|eThrowException|X|X||||Н/Д||  
|`eAbortThread`|X|X||||Н/Д|X|  
|`eRudeAbortThread`|X|X||||Н/Д|X|  
|`eUnloadAppDomain`|X|X||X||Н/Д|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|Н/Д|X|  
|`eExitProcess`|X|X||X|X|Н/Д|X|  
|eFastExitProcess|X|X||X|X|Н/Д||  
|`eRudeExitProcess`|X|X|X|X|X|Н/Д||  
|`eDisableRuntime`|X|X|X|X|X|Н/Д||  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
