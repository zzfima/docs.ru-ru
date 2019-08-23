---
title: Метод ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbc38d9cf88f2449bbf689e4cf1b4101f47a0577
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943250"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a>Метод ICLRSyncManager::GetRWLockOwnerNext
Возвращает следующий экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , заблокированный для текущей блокировки чтения и записи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Iterator`  
 окне Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).  
  
 `ppOwnerHostTask`  
 заполняет Указатель на следующий `IHostTask` объект, ожидающий блокировки, или значение null, если ни одна из задач не ожидает выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetRWLockOwnerNext`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Если `ppOwnerHostTask` параметр имеет значение null, итерация завершается и узел должен вызвать метод [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
> [!NOTE]
> Среда CLR вызывает `AddRef` метод в `IHostTask` , который `ppOwnerHostTask` указывает, чтобы предотвратить выход этой задачи, пока узел удерживает указатель. Узел должен вызвать `Release` , чтобы уменьшить число ссылок по завершении.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
