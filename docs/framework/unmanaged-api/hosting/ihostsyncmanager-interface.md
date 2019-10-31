---
title: Интерфейс IHostSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132626"
---
# <a name="ihostsyncmanager-interface"></a>Интерфейс IHostSyncManager
Предоставляет методы, позволяющие среде CLR создавать примитивы синхронизации путем вызова узла вместо использования функций синхронизации Win32.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Создает объект события автоматического сброса.|  
|[Метод CreateCrst](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Создает объект критической секции для синхронизации.|  
|[Метод CreateCrstWithSpinCount](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Создает объект критической секции с количеством счетчиков для синхронизации.|  
|[Метод CreateManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Создает объект события ручного сброса.|  
|[Метод CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Создает Отслеживаемый объект события автоматического сброса.|  
|[Метод CreateRWLockReaderEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Создает объект события ручного сброса для реализации блокировки чтения.|  
|[Метод CreateRWLockWriterEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Создает объект события автоматического сброса для реализации блокировки модуля записи.|  
|[Метод CreateSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Создает объект [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) для среды CLR, который будет использоваться в качестве семафора для событий ожидания.|  
|[Метод SetCLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Задает экземпляр [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) , связываемый с текущим экземпляром `IHostSyncManager`.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR обнаруживает реализацию `IHostSyncManager` узла, вызывая метод [IHostControl:: жесостманажер](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) с `IID` IID_IHostSyncManager.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
