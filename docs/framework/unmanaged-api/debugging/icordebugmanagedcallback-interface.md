---
title: Интерфейс ICorDebugManagedCallback
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
ms.openlocfilehash: 96dedcd27e87c5afc504e7840100eb121410675e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130762"
---
# <a name="icordebugmanagedcallback-interface"></a>Интерфейс ICorDebugManagedCallback
Предоставляет методы для обработки обратных вызовов отладчика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Break](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Уведомляет отладчик о выполнении инструкции <xref:System.Reflection.Emit.OpCodes.Break> в потоке кода.|  
|[Метод Breakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Уведомляет отладчик об обнаружении точки останова.|  
|[Метод BreakpointSetError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.|  
|[Метод ControlCTrap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Уведомляет отладчик о том, что в отлаживаемом процессе выполняется треппинг CTRL + C.|  
|[Метод CreateAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Уведомляет отладчик о создании домена приложения.|  
|[Метод CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.|  
|[Метод CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Уведомляет отладчик о том, что поток начал выполнение управляемого кода.|  
|[Метод DebuggerError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.|  
|[Метод EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Не рекомендуется. Уведомляет отладчик о том, что событие повторного сопоставления было отправлено в интегрированную среду разработки.|  
|[Метод EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Уведомляет отладчик о завершении оценки.|  
|[Метод EvalException](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Уведомляет отладчик о завершении оценки с необработанным исключением.|  
|[Метод Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Уведомляет отладчик о появлении исключения из управляемого кода.|  
|[Метод ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Уведомляет отладчик о завершении работы домена приложения.|  
|[Метод ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Уведомляет отладчик о завершении процесса.|  
|[Метод ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Уведомляет отладчик о том, что поток, который выполнял управляемый код, завершил работу.|  
|[Метод LoadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Уведомляет отладчик о том, что сборка CLR была успешно загружена.|  
|[Метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Уведомляет отладчик о том, что класс был загружен.|  
|[Метод LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Уведомляет отладчик о том, что модуль CLR был успешно загружен.|  
|[Метод LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Уведомляет отладчик о том, что управляемый поток CLR вызвал метод в классе <xref:System.Diagnostics.EventLog> для записи события в журнал.|  
|[Метод LogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Уведомляет отладчик о том, что управляемый поток CLR вызвал метод в классе <xref:System.Diagnostics.Switch> для создания, изменения или удаления переключателя отладки или трассировки.|  
|[Метод NameChange](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Уведомляет отладчик о том, что имя домена приложения или потока изменилось.|  
|[Метод StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Уведомляет отладчик о завершении шага.|  
|[Метод UnloadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Уведомляет отладчик о выгрузке сборки CLR.|  
|[Метод UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Уведомляет отладчик о выгрузке класса.|  
|[Метод UnloadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Уведомляет отладчик о выгрузке модуля CLR (DLL).|  
|[Метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Уведомляет отладчик о том, что символы для модуля CLR были изменены.|  
  
## <a name="remarks"></a>Заметки  
 Все обратные вызовы сериализуются, вызываются в том же потоке и вызываются с процессом в состоянии SYNCHRONIZED.  
  
 Каждая реализация обратного вызова должна вызывать [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения. Если `ICorDebugController::Continue` не вызывается до возврата обратного вызова, процесс останется остановленным, а обратные вызовы событий не будут выполняться до вызова `ICorDebugController::Continue`.  
  
 Отладчик должен реализовать [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) при отладке приложений .NET Framework версии 2,0. Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается в качестве объекта обратного вызова в метод [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
