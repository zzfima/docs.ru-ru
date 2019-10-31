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
ms.openlocfilehash: 143052febe136e969987c35bc06f6c3b3356aedf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140785"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Метод ICLRPolicyManager::SetActionOnFailure
Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `failure`  
 окне Одно из значений [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) , указывающее тип сбоя, для которого необходимо выполнить действие.  
  
 `action`  
 окне Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее действие, выполняемое в случае сбоя. Список поддерживаемых значений см. в разделе "Примечания".  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Действие политики не может быть задано для указанной операции, или для операции указано недопустимое действие политики.|  
  
## <a name="remarks"></a>Заметки  
 По умолчанию среда CLR создает исключение, когда не удается выделить ресурс, например память. `SetActionOnFailure` позволяет узлу переопределить это поведение, указав действие политики для выполнения при сбое. В следующей таблице показаны поддерживаемые сочетания значений [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) и [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) . (Префикс FAIL_ опускается из значений [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) .)  
  
||нонкритикалресаурце|критикалресаурце|фаталрунтиме|орфанедлокк|StackOverflow|AccessViolationException|кодеконтракт|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|x|x||||Н/Д||  
|есровексцептион|x|x||||Н/Д||  
|`eAbortThread`|x|x||||Н/Д|x|  
|`eRudeAbortThread`|x|x||||Н/Д|x|  
|`eUnloadAppDomain`|x|x||x||Н/Д|x|  
|`eRudeUnloadAppDomain`|x|x||x|x|Н/Д|x|  
|`eExitProcess`|x|x||x|x|Н/Д|x|  
|ефастекситпроцесс|x|x||x|x|Н/Д||  
|`eRudeExitProcess`|x|x|x|x|x|Н/Д||  
|`eDisableRuntime`|x|x|x|x|x|Н/Д||  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
