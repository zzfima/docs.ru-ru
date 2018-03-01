---
title: "Интерфейс ICLRTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fcce85e56abae561b05364a925fdb6b55825669
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask-interface"></a>Интерфейс ICLRTask
Предоставляет методы, позволяющие основному приложению отправлять запросы среды common language runtime (CLR), или для предоставления уведомления в среду CLR о соответствующей задаче.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Запрашивает прерывание задачи среды CLR, текущий `ICLRTask` представляет экземпляр.|  
|[Метод ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Сообщает среде CLR, которая задачу, связанную с текущим `ICLRTask` экземпляра заканчивается и пытается корректно задача завершается.|  
|[Метод GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Возвращает статистические сведения об использовании ресурсов памяти задачей, представленный текущим `ICLRTask` экземпляра.|  
|[Метод LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Возвращает число блокировок, произведенных в задаче.|  
|[Метод NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Возвращает значение, указывающее, является ли узел следует назначить высокий приоритет повторное планирование задач, представленных текущим `ICLRTask` экземпляра.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Информирует среду CLR, завершит задачу узла и позволяет повторно использовать текущий CLR `ICLRTask` экземпляра для представления другой задачи.|  
|[Метод RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Среда CLR прервать задачу, представленную текущим `ICLRTask` экземпляра немедленно, без обеспечения выполнения методов завершения.|  
|[Метод SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Задает уникальный идентификатор для задачи, представленный текущим `ICLRTask` экземпляра, используемые для отладки.|  
|[Метод SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Уведомляет CLR, задача, представленная текущим `ICLRTask` экземпляр находится в рабочем состоянии.|  
|[Метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Уведомляет CLR, задача, представленная текущим `ICLRTask` экземпляр больше не находится в рабочем состоянии.|  
|[Метод YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Запрашивает CLR убедитесь процессорного времени для других задач. Среда CLR не дает никаких гарантий, что задача будет помещена в состоянии, где она может возвращать время обработки.|  
  
## <a name="remarks"></a>Примечания  
 `ICLRTask` Является представлением задачу для среды CLR. В любой момент во время выполнения кода задачу можно описать как запущен или ожидание выполнения. Узел вызывает метод `ICLRTask::SwitchIn` метод для уведомления среды CLR, задача, текущий `ICLRTask` представляет экземпляр находится в рабочем состоянии. После вызова `ICLRTask::SwitchIn`, узел можно запланировать задачу на любом потоке операционной системы, за исключением того, в случаях, где среда выполнения требует сходство потоков, в соответствии с вызовы [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) и [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) методы. Некоторое время спустя операционной системы может понадобиться удалить задачу из потока и поместите его в состоянии без выполнения. Например это может произойти всякий раз, когда задача блокируется примитивы синхронизации, и, ожидает завершения операций ввода-вывода. Узел вызывает метод [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) для уведомления среды CLR, задача, представленная текущим `ICLRTask` экземпляр больше не находится в рабочем состоянии.  
  
 Обычно, задача прерывается в конце выполнения кода. В этот момент узел вызывает метод `ICLRTask::ExitTask` для уничтожения связанного `ICLRTask`. Однако задачи можно также будет перезапущен с помощью вызова `ICLRTask::Reset`, что позволяет `ICLRTask` экземпляра можно использовать повторно. Этот подход позволяет избежать издержек по несколько раз, создания и удаления экземпляров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Интерфейс ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
