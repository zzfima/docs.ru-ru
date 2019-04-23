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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eacd10eecf2a8a2fc1b73a7f97eef5cb5eabafd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133722"
---
# <a name="icordebugmanagedcallback-interface"></a>Интерфейс ICorDebugManagedCallback
Предоставляет методы для обработки обратных вызовов отладчика.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Break](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Уведомляет отладчик при <xref:System.Reflection.Emit.OpCodes.Break> выполнения инструкции в потоке кода.|  
|[Метод Breakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Уведомляет отладчик о достижении точки останова.|  
|[Метод BreakpointSetError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Уведомляет отладчик о том, что общеязыковой среды выполнения (CLR) не удалось точно привязать точку останова, который был задан до функции just-in-time (JIT) компиляции.|  
|[Метод ControlCTrap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Уведомляет отладчик, что сочетание клавиш CTRL + C, представленные в отлаживаемом процессе.|  
|[Метод CreateAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Уведомляет отладчик о том, что домен приложения был создан.|  
|[Метод CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Уведомляет отладчик присоединен процесс или запускается в первый раз.|  
|[Метод CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Уведомляет отладчик о том, что поток начал выполнение управляемого кода.|  
|[Метод DebuggerError](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Уведомляет отладчик о том, что произошла ошибка при попытке обработать событие из среды CLR.|  
|[Метод EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Не рекомендуется. Уведомляет отладчик о том, что события повторного сопоставления отправлено в интегрированную среду разработки.|  
|[Метод EvalComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Уведомляет отладчик о завершении вычисления.|  
|[Метод EvalException](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Уведомляет отладчик о том, что оценку завершен с необработанным исключением.|  
|[Метод Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Уведомляет отладчик о том, что исключение выдавалось из управляемого кода.|  
|[Метод ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Уведомляет отладчик о том, что завершил работу домена приложения.|  
|[Метод ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Уведомляет отладчик о том, что процесс завершен.|  
|[Метод ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Уведомляет отладчик о завершении потока, время выполнения управляемого кода.|  
|[Метод LoadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Уведомляет отладчик о успешной загрузке сборки среды CLR.|  
|[Метод LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Уведомляет отладчик о том, что класс был загружен.|  
|[Метод LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Уведомляет отладчик о том, успешно загружен модуль среды CLR.|  
|[Метод LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Уведомляет отладчик о том, что поток управляемого кода CLR вызвал метод в <xref:System.Diagnostics.EventLog> класс события в журнал.|  
|[Метод LogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Уведомляет отладчик о том, что поток управляемого кода CLR вызвал метод в <xref:System.Diagnostics.Switch> класса для создания, изменения или удаления коммутатора отладки и трассировки.|  
|[Метод NameChange](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Уведомляет отладчик о том, что изменилось имя домена приложения или потока.|  
|[Метод StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Уведомляет отладчик о выполнении шага.|  
|[Метод UnloadAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Уведомляет отладчик о выгрузке сборки среды CLR.|  
|[Метод UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Уведомляет отладчик о выгрузке класса.|  
|[Метод UnloadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Уведомляет отладчик о выгрузке модуля среды CLR (DLL).|  
|[Метод UpdateModuleSymbols](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Уведомляет отладчик о том, что символы для модуля CLR были изменены.|  
  
## <a name="remarks"></a>Примечания  
 Все обратные вызовы сериализации, в том же потоке и вызываются с использованием процессов в синхронизированном состоянии.  
  
 Каждая реализация обратного вызова должна вызвать [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) для возобновления выполнения. Если `ICorDebugController::Continue` не вызывается прежде, чем функция обратного вызова, процесс будет оставаться остановленной и дальнейшие обратные вызовы событий будет происходить, пока `ICorDebugController::Continue` вызывается.  
  
 Отладчик должен реализовать [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) при отладке приложений .NET Framework версии 2.0. Экземпляр `ICorDebugManagedCallback` или `ICorDebugManagedCallback2` передается в качестве объекта обратного вызова для [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
