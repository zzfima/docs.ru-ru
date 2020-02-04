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
ms.openlocfilehash: 9a33b90bf39103756ab4fd07157739633997fb61
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788400"
---
# <a name="icordebugmanagedcallback-interface"></a>Интерфейс ICorDebugManagedCallback
Предоставляет методы для обработки обратных вызовов отладчика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Break](icordebugmanagedcallback-break-method.md)|Уведомляет отладчик о выполнении инструкции <xref:System.Reflection.Emit.OpCodes.Break> в потоке кода.|  
|[Метод Breakpoint](icordebugmanagedcallback-breakpoint-method.md)|Уведомляет отладчик об обнаружении точки останова.|  
|[Метод BreakpointSetError](icordebugmanagedcallback-breakpointseterror-method.md)|Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.|  
|[Метод ControlCTrap](icordebugmanagedcallback-controlctrap-method.md)|Уведомляет отладчик о том, что в отлаживаемом процессе выполняется треппинг CTRL + C.|  
|[Метод CreateAppDomain](icordebugmanagedcallback-createappdomain-method.md)|Уведомляет отладчик о создании домена приложения.|  
|[Метод CreateProcess](icordebugmanagedcallback-createprocess-method.md)|Уведомляет отладчик о том, что процесс был присоединен или запущен в первый раз.|  
|[Метод CreateThread](icordebugmanagedcallback-createthread-method.md)|Уведомляет отладчик о том, что поток начал выполнение управляемого кода.|  
|[Метод DebuggerError](icordebugmanagedcallback-debuggererror-method.md)|Уведомляет отладчик о том, что произошла ошибка при попытке выполнить обработку события из среды CLR.|  
|[Метод EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md)|Устаревшее. Уведомляет отладчик о том, что событие повторного сопоставления было отправлено в интегрированную среду разработки.|  
|[Метод EvalComplete](icordebugmanagedcallback-evalcomplete-method.md)|Уведомляет отладчик о завершении оценки.|  
|[Метод EvalException](icordebugmanagedcallback-evalexception-method.md)|Уведомляет отладчик о завершении оценки с необработанным исключением.|  
|[Метод Exception](icordebugmanagedcallback-exception-method.md)|Уведомляет отладчик о появлении исключения из управляемого кода.|  
|[Метод ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md)|Уведомляет отладчик о завершении работы домена приложения.|  
|[Метод ExitProcess](icordebugmanagedcallback-exitprocess-method.md)|Уведомляет отладчик о завершении процесса.|  
|[Метод ExitThread](icordebugmanagedcallback-exitthread-method.md)|Уведомляет отладчик о том, что поток, который выполнял управляемый код, завершил работу.|  
|[Метод LoadAssembly](icordebugmanagedcallback-loadassembly-method.md)|Уведомляет отладчик о том, что сборка CLR была успешно загружена.|  
|[Метод LoadClass](icordebugmanagedcallback-loadclass-method.md)|Уведомляет отладчик о том, что класс был загружен.|  
|[Метод LoadModule](icordebugmanagedcallback-loadmodule-method.md)|Уведомляет отладчик о том, что модуль CLR был успешно загружен.|  
|[Метод LogMessage](icordebugmanagedcallback-logmessage-method.md)|Уведомляет отладчик о том, что управляемый поток CLR вызвал метод в классе <xref:System.Diagnostics.EventLog> для записи события в журнал.|  
|[Метод LogSwitch](icordebugmanagedcallback-logswitch-method.md)|Уведомляет отладчик о том, что управляемый поток CLR вызвал метод в классе <xref:System.Diagnostics.Switch> для создания, изменения или удаления переключателя отладки или трассировки.|  
|[Метод NameChange](icordebugmanagedcallback-namechange-method.md)|Уведомляет отладчик о том, что имя домена приложения или потока изменилось.|  
|[Метод StepComplete](icordebugmanagedcallback-stepcomplete-method.md)|Уведомляет отладчик о завершении шага.|  
|[Метод UnloadAssembly](icordebugmanagedcallback-unloadassembly-method.md)|Уведомляет отладчик о выгрузке сборки CLR.|  
|[Метод UnloadClass](icordebugmanagedcallback-unloadclass-method.md)|Уведомляет отладчик о выгрузке класса.|  
|[Метод UnloadModule](icordebugmanagedcallback-unloadmodule-method.md)|Уведомляет отладчик о выгрузке модуля CLR (DLL).|  
|[Метод UpdateModuleSymbols](icordebugmanagedcallback-updatemodulesymbols-method.md)|Уведомляет отладчик о том, что символы для модуля CLR были изменены.|  
  
## <a name="remarks"></a>Заметки  
 Все обратные вызовы сериализуются, вызываются в том же потоке и вызываются с процессом в состоянии SYNCHRONIZED.  
  
 Каждая реализация обратного вызова должна вызывать [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) для возобновления выполнения. Если `ICorDebugController::Continue` не вызывается до возврата обратного вызова, процесс останется остановленным, а обратные вызовы событий не будут выполняться до вызова `ICorDebugController::Continue`.  
  
 Отладчик должен реализовать [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) при отладке приложений .NET Framework версии 2,0. Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается в качестве объекта обратного вызова в метод [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebug](icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
