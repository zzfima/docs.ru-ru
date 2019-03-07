---
title: Метод IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93deb2d0457fef6f190d90cc4084b9bb5997680d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488491"
---
# <a name="ihosttaskmanagercreatetask-method"></a>Метод IHostTaskManager::CreateTask
Запросы на создание новой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `stacksize`  
 [in] Запрошенный размер в байтах, запрошенной стека, или 0 (ноль) для размера по умолчанию.  
  
 `pStartAddress`  
 [in] Указатель на функцию будет выполнять задача.  
  
 `pParameter`  
 [in] Указатель на данные пользователя должны быть переданы функции, или значение null, если функция не принимает никаких параметров.  
  
 `ppTask`  
 [out] Указатель на адрес [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра, созданные в узле, или значение null, если задача не может быть создана. Задача остается в приостановленном состоянии, пока она запущена явным образом с помощью вызова [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`CreateTask` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти, доступного для создания требуемой задачи.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает `CreateTask` для запроса, создание новой задачи. Основное приложение возвращает указатель интерфейса на `IHostTask` экземпляра. Возвращаемая задача должна отложен до явным образом она запущена с помощью вызова `IHostTask::Start`.  
  
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
