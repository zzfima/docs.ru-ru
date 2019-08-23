---
title: Метод ICLRMemoryNotificationCallback::OnMemoryNotification
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949705"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a>Метод ICLRMemoryNotificationCallback::OnMemoryNotification
Уведомляет среду CLR о загрузке памяти на компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `eMemoryAvailable`  
 окне Одно из значений [емеморяваилабле](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) , указывающее на нехватку памяти в данный момент на компьютере.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OnMemoryNotification`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR регистрирует обратный вызов `OnMemoryNotification` с помощью вызова метода [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) . Среда выполнения использует сведения, возвращаемые при обратном вызове, чтобы освободить дополнительную память, когда узел сообщает, что ресурсы памяти имеют низкий уровень.  
  
> [!NOTE]
> `OnMemoryNotification` Вызовы никогда не блокируются. Они всегда возвращают немедленно.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Метод RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [Интерфейс ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
