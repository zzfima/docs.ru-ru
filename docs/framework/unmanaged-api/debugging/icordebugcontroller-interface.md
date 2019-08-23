---
title: Интерфейс ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2a083f46f24d6f3f24c63dd2415b85f975cfa29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912854"
---
# <a name="icordebugcontroller-interface"></a>Интерфейс ICorDebugController

Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Этот метод устарел.|  
|`ICorDebugController::CommitChanges`|Этот метод устарел.|  
|[Метод Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Возобновляет выполнение управляемых потоков после вызова [ICorDebugController:: останавливаться](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Метод Detach](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Отсоединяет отладчик от процесса или домена приложения.|  
|[Метод EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Возвращает перечислитель для активных управляемых потоков в процессе.|  
|[Метод HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.|  
|[Метод IsRunning](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.|  
|[Метод SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Задает состояние отладки всех управляемых потоков в процессе.|  
|[Метод Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.|  
|[Метод Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Завершает процесс с указанным кодом выхода.|  
  
## <a name="remarks"></a>Примечания  
 Если `ICorDebugController` управляет процессом, область включает все потоки процесса. Если `ICorDebugController` управляет доменом приложения, область включает только потоки этого конкретного домена приложения.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
