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
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107553"
---
# <a name="icordebugcontroller-interface"></a>Интерфейс ICorDebugController

Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Этот метод устарел.|  
|`ICorDebugController::CommitChanges`|Этот метод устарел.|  
|[Метод Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Возобновляет выполнение управляемых потоков после вызова [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Метод Detach](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Отключает отладчик от процесса или домена приложения.|  
|[Метод EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Возвращает перечислитель для активных управляемых потоков в процессе.|  
|[Метод HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Получает значение, указывающее ли любой управляемый оно для указанного потока.|  
|[Метод IsRunning](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Получает значение, указывающее, потоки в процессе, в настоящее время работают ли свободно.|  
|[Метод SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Задает состояние отладки все управляемые потоки в процессе.|  
|[Метод Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Выполняет совместную остановку во всех потоках, работающих под управлением управляемого кода в процессе.|  
|[Метод Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Завершает процесс с помощью указанного кода выхода.|  
  
## <a name="remarks"></a>Примечания  
 Если `ICorDebugController` является управление процессом, в том числе все потоки процесса. Если `ICorDebugController` является управление домен приложения, в область входит только потоки конкретного домена приложений.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
