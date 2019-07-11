---
title: Метод ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804a295cf74067eb23ed8e8c860252a1f2fcf5d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770188"
---
# <a name="iclrtaskmanagercreatetask-method"></a>Метод ICLRTaskManager::CreateTask
Запрашивает явным образом, что общеязыковая среда выполнения (CLR) создайте новую задачу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTask`  
 [out] Указатель на адрес вновь созданного [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), или значение null, если не удалось создать задачу.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод возвратился успешно.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для выделения запрошенного ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR создает новую задачу автоматически при инициализации, когда пользовательский код создает поток с помощью типов в <xref:System.Threading> пространства имен, или когда увеличивается размер пула потоков. Он также создает задачи, если неуправляемый код вызывает для управляемой функции.  
  
 `CreateTask` позволяет узлу убедитесь, что среда CLR создаст новую задачу явного запроса. Например узел может вызывать этот метод для предварительной инициализации структур данных.  
  
> [!IMPORTANT]
>  Новая задача возвращается в приостановленном состоянии и остается в узел явным образом вызывает метод [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
