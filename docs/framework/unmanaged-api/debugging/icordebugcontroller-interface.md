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
ms.openlocfilehash: d6c923f03309da3ad8092ea6119e7d850120ee2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783806"
---
# <a name="icordebugcontroller-interface"></a>Интерфейс ICorDebugController

Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Этот метод устарел.|  
|`ICorDebugController::CommitChanges`|Этот метод устарел.|  
|[Метод Continue](icordebugcontroller-continue-method.md)|Возобновляет выполнение управляемых потоков после вызова [ICorDebugController:: останавливаться](icordebugcontroller-stop-method.md).|  
|[Метод Detach](icordebugcontroller-detach-method.md)|Отсоединяет отладчик от процесса или домена приложения.|  
|[Метод EnumerateThreads](icordebugcontroller-enumeratethreads-method.md)|Возвращает перечислитель для активных управляемых потоков в процессе.|  
|[Метод HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)|Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.|  
|[Метод IsRunning](icordebugcontroller-isrunning-method.md)|Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.|  
|[Метод SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md)|Задает состояние отладки всех управляемых потоков в процессе.|  
|[Метод Stop](icordebugcontroller-stop-method.md)|Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.|  
|[Метод Terminate](icordebugcontroller-terminate-method.md)|Завершает процесс с указанным кодом выхода.|  
  
## <a name="remarks"></a>Заметки  
 Если `ICorDebugController` управляет процессом, область включает все потоки процесса. Если `ICorDebugController` управляет доменом приложения, область включает только потоки этого конкретного домена приложения.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
