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
ms.openlocfilehash: c4f27a73022b0495b2772c0485c14a1b007dc883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132643"
---
# <a name="iclrtask-interface"></a>Интерфейс ICLRTask
Предоставляет методы, позволяющие основному приложению выполнять запросы среды CLR или предоставлять в среду CLR уведомление о связанной задаче.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Abort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Требует, чтобы среда CLR прервала задачу, которую представляет текущий экземпляр `ICLRTask`.|  
|[Метод ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Уведомляет среду CLR о том, что задача, связанная с текущим экземпляром `ICLRTask`, завершается и пытается корректно завершить задачу.|  
|[Метод GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Возвращает статистические сведения об использовании ресурсов памяти задачей, представленной текущим экземпляром `ICLRTask`.|  
|[Метод LocksHeld](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Возвращает количество блокировок, которые в настоящее время удерживаются в задаче.|  
|[Метод NeedsPriorityScheduling](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Возвращает значение, указывающее, должен ли узел назначить высокий приоритет для перепланирования задачи, представленной текущим экземпляром `ICLRTask`.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Информирует среду CLR о том, что узел выполнил задачу, и позволяет среде CLR повторно использовать текущий экземпляр `ICLRTask` для представления другой задачи.|  
|[Метод RudeAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Заставляет CLR немедленно прерывать задачу, представленную текущим экземпляром `ICLRTask`, без гарантии того, что методы завершения будут выполняться.|  
|[Метод SetTaskIdentifier](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Задает уникальный идентификатор для задачи, представленной текущим экземпляром `ICLRTask`, для использования при отладке.|  
|[Метод SwitchIn](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Уведомляет среду CLR о том, что задача, представленная текущим экземпляром `ICLRTask`, находится в рабочем состоянии.|  
|[Метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Уведомляет среду CLR о том, что задача, представленная текущим экземпляром `ICLRTask`, больше не находится в рабочем состоянии.|  
|[Метод YieldTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Запрашивает доступность процессорного времени средой CLR для выполнения других задач. Среда CLR не гарантирует, что задача будет переведена в состояние, в котором она может подать время на обработку.|  
  
## <a name="remarks"></a>Заметки  
 `ICLRTask` — это представление задачи для среды CLR. В любой момент во время выполнения кода задача может быть описана как выполняется или ожидает выполнения. Узел вызывает метод `ICLRTask::SwitchIn`, чтобы уведомить среду CLR о том, что задача, которую представляет текущий экземпляр `ICLRTask`, теперь находится в рабочем состоянии. После вызова `ICLRTask::SwitchIn`узел может запланировать задачу в любом потоке операционной системы, за исключением случаев, когда среда выполнения требует сходство потоков, как указано вызовами методов [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) и [IHostTaskManager:: Методы EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) . Спустя некоторое время операционная система может решить удалить задачу из потока и перевести ее в неработающее состояние. Например, это может произойти, если задача блокирует примитивы синхронизации или ожидает завершения операций ввода-вывода. Узел вызывает [Переключение](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) , чтобы УВЕДОМИТЬ среду CLR о том, что задача, представленная текущим экземпляром `ICLRTask`, больше не находится в рабочем состоянии.  
  
 Обычно задача завершается в конце выполнения кода. В это время узел вызывает `ICLRTask::ExitTask`, чтобы уничтожить связанную `ICLRTask`. Однако задачи можно также перезапускать с помощью вызова `ICLRTask::Reset`, что позволяет снова использовать экземпляр `ICLRTask`. Такой подход предотвращает издержки на многократное создание и уничтожение экземпляров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Интерфейс ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
