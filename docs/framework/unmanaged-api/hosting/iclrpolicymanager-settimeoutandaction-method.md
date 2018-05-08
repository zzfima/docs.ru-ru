---
title: Метод ICLRPolicyManager::SetTimeoutAndAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c375fdffacccb27c20878c4e6adef9dd947148e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>Метод ICLRPolicyManager::SetTimeoutAndAction
Задает значение времени ожидания для указанной операции и задает действие политики, которое должен выполнить общеязыковой среды выполнения (CLR), при выполнении этой операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `operation`  
 [in] Один из [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) значения, указывает, что операция, для которого требуется задать время ожидания и политики `action`. Поддерживаются следующие значения:  
  
-   OPR_AppDomainUnload  
  
-   OPR_ProcessExit  
  
-   OPR_ThreadRudeAbortInCriticalRegion  
  
-   OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 [in] Новое значение времени ожидания в миллисекундах. Значение БЕСКОНЕЧНЫЙ причины `operation` никогда не до времени ожидания.  
  
 `action`  
 [in] Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие действие политики, когда должна выполнять среда CLR `operation` происходит.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Невозможно задать время ожидания для указанного `operation`, или было задано недопустимое значение для `action`.|  
  
## <a name="remarks"></a>Примечания  
 `SetTimeoutAndAction` Инкапсулирует возможности [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) и [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) методов и может быть вызван вместо последовательные вызовы этих двух методов.  
  
> [!IMPORTANT]
>  Не все значения действий политики может быть указан как поведение времени ожидания для операций среды CLR. См. в разделах Примечание разделов для этих двух методов для допустимых значений.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [Метод SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [ICLRPolicyManager::SetTimeoutAndAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
