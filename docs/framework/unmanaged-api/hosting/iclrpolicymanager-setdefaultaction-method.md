---
title: Метод ICLRPolicyManager::SetDefaultAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 8dc3a3c04a619ace566e173fb8d8945a9d921bce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140763"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>Метод ICLRPolicyManager::SetDefaultAction
Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `operation`  
 окне Одно из значений [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , указывающее действие, для которого необходимо настроить поведение среды CLR.  
  
 `action`  
 окне Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее действие политики, которое должна предпринять среда CLR при `operation`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Для `operation`указан недопустимый `action`, или для `operation`указано недопустимое значение.|  
  
## <a name="remarks"></a>Заметки  
 Не все значения действий политики могут быть указаны в качестве поведения по умолчанию для операций среды CLR. `SetDefaultAction` обычно можно использовать только для эскалации поведения. Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно. В следующей таблице описаны допустимые значения `action` для каждого возможного `operation` значения.  
  
|Значение для `operation`|Допустимые значения для `action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-Еабортсреад<br />-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_AppDomainUnload|-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_AppDomainRudeUnload|-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_ProcessExit|-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_FinalizerRun|-Еноактион<br />-Еабортсреад<br />-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [Перечисление EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
