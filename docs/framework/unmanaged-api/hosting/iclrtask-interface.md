---
title: Интерфейс ICLRTask
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1baeac5db41aa64380d694ebab5419229d8adb4c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763546"
---
# <a name="iclrtask-interface"></a>Интерфейс ICLRTask
Предоставляет методы, позволяющие основному приложению отправлять запросы общеязыковой среды выполнения (CLR), или для предоставления уведомления в среду CLR о соответствующей задаче.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Запрашивает прерывание задачи среды CLR, текущий `ICLRTask` представленное экземпляром.|  
|[Метод ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Уведомляет среды CLR, которая задачу, связанную с текущим `ICLRTask` экземпляра завершается и пытается корректно завершить работу задачи.|  
|[Метод GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Возвращает статистические сведения об использовании ресурсов памяти задачей, представленный текущим `ICLRTask` экземпляра.|  
|[Метод LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Возвращает число блокировок, произведенных в задаче.|  
|[Метод NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Получает значение, указывающее, является ли узел следует присваивать высокий приоритет повторного планирования задач, представленный текущим `ICLRTask` экземпляра.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Информирует среду CLR, что узел завершения задачи и обеспечивает работу CLR для повторного использования текущего `ICLRTask` экземпляра для представления другой задачи.|  
|[Метод RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Вынуждает среду CLR прервать задачу, представленную текущим `ICLRTask` экземпляра немедленно, не гарантирует выполнения методов завершения.|  
|[Метод SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Задает уникальный идентификатор для задачи, представленный текущим `ICLRTask` экземпляр, для использования при отладке.|  
|[Метод SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Уведомляет CLR, задача, представленная текущим `ICLRTask` экземпляр находится в рабочем состоянии.|  
|[Метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Уведомляет CLR, задача, представленная текущим `ICLRTask` экземпляр больше не находится в рабочем состоянии.|  
|[Метод YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Запрашивает CLR марки процессорного времени для других задач. Среда CLR не дает никакой гарантии, что задача будет помещен в состоянии, где может дать время обработки.|  
  
## <a name="remarks"></a>Примечания  
 `ICLRTask` Является представлением задачу для среды CLR. В любой момент во время выполнения кода задачу можно описать как беготни или ожидания для выполнения. Узел вызывает метод `ICLRTask::SwitchIn` метод для уведомления среды CLR, задачи, текущий `ICLRTask` представляет экземпляр находится в рабочем состоянии. После вызова `ICLRTask::SwitchIn`, узел может запланировать задачу в любом потоке операционной системы, за исключением в случаях, где среда выполнения требует сходства потоков, как указано при вызове [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) и [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) методы. Некоторое время спустя операционной системы может потребоваться удалить задачу из потока и поместите его в состоянии без выполнения. Например это может произойти всякий раз, когда задача блокируется на примитивах синхронизации и, ожидает завершения операций ввода-вывода. Узел вызывает метод [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) для уведомления среды CLR, задача, представленная текущим `ICLRTask` экземпляр больше не находится в рабочем состоянии.  
  
 Обычно, задача прерывается в конце выполнения кода. В этот момент узел вызывает метод `ICLRTask::ExitTask` для уничтожения связанного `ICLRTask`. Тем не менее, задачи можно также будет перезапущен с помощью вызова `ICLRTask::Reset`, что позволяет `ICLRTask` экземпляр можно использовать повторно. Этот способ исключает затраты на многократное Создание и уничтожение экземпляров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Интерфейс ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
