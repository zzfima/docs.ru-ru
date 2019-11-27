---
title: Интерфейс ICorProfilerCallback
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
ms.openlocfilehash: 487f347c19ab513f328a9f1a02601fc72c233eb5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449926"
---
# <a name="icorprofilercallback-interface"></a>Интерфейс ICorProfilerCallback
Предоставляет методы, используемые общеязыковой средой выполнения (CLR) для уведомления профилировщика кода о событиях, на которые подписан профилировщик.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Уведомляет профилировщик о том, что домен приложения создан.|  
|[Метод AppDomainCreationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Уведомляет профилировщик о том, что создается домен приложения.|  
|[Метод AppDomainShutdownFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.|  
|[Метод AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Уведомляет профилировщик о том, что домен приложения выгружается из процесса.|  
|[Метод AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Уведомляет профилировщик о том, что загрузка сборки завершена.|  
|[Метод AssemblyLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Уведомляет профилировщик о загрузке сборки.|  
|[Метод AssemblyUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Уведомляет профилировщик о том, что сборка была выгружена.|  
|[Метод AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Уведомляет профилировщик о выгрузке сборки.|  
|[Метод ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Уведомляет профилировщик о том, что загрузка класса завершена.|  
|[Метод ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Уведомляет профилировщик о загрузке класса.|  
|[Метод ClassUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки класса.|  
|[Метод ClassUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Уведомляет профилировщик о выгрузке класса.|  
|[Метод COMClassicVTableCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Уведомляет профилировщик, что вызываемая оболочка времени выполнения (RCW) для заданного IID и класса была создана.|  
|[Метод COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Уведомляет профилировщик об удалении вызываемой оболочки времени выполнения.|  
|[Метод ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Уведомляет профилировщик о том, что управление передается соответствующему блоку `catch`.|  
|[Метод ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Уведомляет профилировщик о том, что управление передается из соответствующего блока `catch`.|  
|[Метод ExceptionCLRCatcherExecute](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Устарело в .NET Framework версии 2,0.|  
|[Метод ExceptionCLRCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Устарело в .NET Framework 2,0.|  
|[Метод ExceptionOSHandlerEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Не реализовано. Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.|  
|[Метод ExceptionOSHandlerLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Не реализовано. Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.|  
|[Метод ExceptionSearchCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Уведомляет профилировщик о том, что на фазе поиска исключений обнаружен обработчик для созданного исключения.|  
|[Метод ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Уведомляет профилировщик о выполнении пользовательского фильтра.|  
|[Метод ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Уведомляет профилировщик о завершении выполнения пользовательского фильтра.|  
|[Метод ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Уведомляет профилировщик, что поисковый этап обработки исключений вошел в функцию.|  
|[Метод ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Уведомляет профилировщик о завершении фазы поиска обработки исключений при поиске функции.|  
|[Метод ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Уведомляет профилировщик о том, что было создано исключение.|  
|[Метод ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Уведомляет профилировщик о том, что фаза очистки при обработке исключений вводит `finally` предложение, содержащееся в указанной функции.|  
|[Метод ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений оставлена предложением `finally`.|  
|[Метод ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений вводит функцию.|  
|[Метод ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений завершила очистку функции.|  
|[Метод FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Уведомляет профилировщик о запуске среды выполнения для выгрузки функции.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Вызывается для инициализации профилировщика при запуске нового приложения CLR.|  
|[Метод JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Уведомляет профилировщик о завершении поиска для функции, которая была скомпилирована ранее с помощью NGen. exe.|  
|[Метод JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью NGen. exe.|  
|[Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Уведомляет профилировщик о завершении компиляции функции JIT-компилятором.|  
|[Метод JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.|  
|[Метод JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Уведомляет профилировщик о том, что функция, скомпилированная JIT-компилятором, была удалена из памяти.|  
|[Метод JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Уведомляет профилировщик о том, что JIT-компилятор собирается вставить функцию в строку с другой функцией.|  
|[Метод ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Уведомляет профилировщик о том, что произошел переход из управляемого кода в неуправляемый код.|  
|[Метод ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Уведомляет профилировщик о том, что модуль присоединен к своей родительской сборке.|  
|[Метод ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Уведомляет профилировщик о завершении загрузки модуля.|  
|[Метод ModuleLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Уведомляет профилировщик о загрузке модуля.|  
|[Метод ModuleUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки модуля.|  
|[Метод ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Уведомляет профилировщик о выгрузке модуля.|  
|[Метод MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, которые были перемещены во время сборки мусора.|  
|[Метод ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Уведомляет профилировщик о том, что для объекта выделена память в куче.|  
|[Метод ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Уведомляет профилировщик об объектах в памяти, на которые ссылается указанный объект.|  
|[Метод ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Уведомляет профилировщик о количестве экземпляров каждого указанного класса, которые были созданы с момента предыдущей сборки мусора.|  
|[Метод RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Уведомляет профилировщик о том, что вызов удаленного взаимодействия был выполнен до завершения на клиенте.|  
|[Метод RemotingClientInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Уведомляет профилировщик о начале удаленного вызова.|  
|[Метод RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Уведомляет профилировщик, что серверная часть вызова удаленного взаимодействия завершена, клиент принимает ответ и готов к его обработке.|  
|[Метод RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.|  
|[Метод RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Уведомляет профилировщик о том, что процесс завершил вызов метода в ответ на запрос удаленного вызова метода.|  
|[Метод RemotingServerInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Уведомляет профилировщик о том, что процесс вызывает метод в ответ на запрос удаленного вызова метода.|  
|[Метод RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Уведомляет профилировщик о том, что процесс получает удаленный вызов метода или запрос на активацию.|  
|[Метод RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Уведомляет профилировщик о том, что процесс завершил обработку запроса удаленного вызова метода и собирается передать ответ через канал.|  
|[Метод RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.|  
|[Метод RuntimeResumeFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Уведомляет профилировщик о том, что среда выполнения возобновила все потоки среды выполнения и вернула нормальную работу.|  
|[Метод RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Уведомляет профилировщик о том, что среда выполнения возобновляет все потоки времени выполнения.|  
|[Метод RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Уведомляет профилировщик о том, что среда выполнения прервал приостановленную приостановку времени выполнения.|  
|[Метод RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков времени выполнения.|  
|[Метод RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Уведомляет профилировщик о том, что среда выполнения собирается приостановить все потоки времени выполнения.|  
|[Метод RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Уведомляет профилировщик о том, что указанный поток возобновил работу после приостановки.|  
|[Метод RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Уведомляет профилировщик о том, что указанный поток был или находится в состоянии приостановки.|  
|[Метод Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Уведомляет профилировщик о том, что приложение завершает работу.|  
|[Метод ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы (ОС).|  
|[Метод ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Уведомляет профилировщик о том, что поток был создан.|  
|[Метод ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Уведомляет профилировщик о том, что поток был уничтожен.|  
|[Метод UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Уведомляет профилировщик о том, что произошел переход из неуправляемого кода в управляемый код.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR вызывает метод в интерфейсе `ICorProfilerCallback` (или [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) для уведомления профилировщика о том, что происходит событие, на которое подписан профилировщик. Это основной интерфейс обратного вызова, через который среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода должен реализовывать методы интерфейса `ICorProfilerCallback`. Для .NET Framework версии 2,0 или более поздней профилировщик также должен реализовать методы `ICorProfilerCallback2`. Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успеха или E_FAIL при сбое. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 В реестре Microsoft Windows профилировщик кода должен зарегистрировать объект модели COM, реализующий интерфейсы `ICorProfilerCallback` и `ICorProfilerCallback2`. Профилировщик кода подписывается на события, для которых требуется получать уведомления путем вызова [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации метода [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)профилировщика. Затем профилировщик может получать уведомления от среды выполнения, когда в процессе в среде выполнения происходит или скоро произойдет событие.  
  
> [!NOTE]
> Профилировщик регистрирует один COM-объект. Если профилировщик предназначен для .NET Framework версии 1,0 или 1,1, этот COM-объект должен реализовывать только методы `ICorProfilerCallback`. Если он предназначен для .NET Framework версии 2,0 или более поздней, COM-объект также должен реализовывать методы `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
