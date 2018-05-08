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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96c8c9de7a6b26c9a00a0ffaf4fb50c08a80d5a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback-interface"></a>Интерфейс ICorProfilerCallback
Предоставляет методы, используемые средой CLR (CLR) для уведомления профилировщика кода при событиях, на которые подписан профилировщик.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Уведомляет профилировщик, что домен приложения был создан.|  
|[Метод AppDomainCreationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Уведомляет профилировщик создания домена приложения.|  
|[Метод AppDomainShutdownFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Уведомляет профилировщик о том, что домен приложения выгружен из процесса.|  
|[Метод AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Уведомляет профилировщик о том, что домен приложения выгружается из процесса.|  
|[Метод AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Уведомляет профилировщик об окончании загрузки сборки.|  
|[Метод AssemblyLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Уведомляет профилировщик, что сборка загружается.|  
|[Метод AssemblyUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Уведомляет профилировщик о выгрузке сборки.|  
|[Метод AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Уведомляет профилировщик о том, что сборка выгружается.|  
|[Метод ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Уведомляет профилировщик об окончании загрузки класса.|  
|[Метод ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Уведомляет профилировщик о том, что при загрузке класса.|  
|[Метод ClassUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки класса.|  
|[Метод ClassUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Уведомляет профилировщик о выгрузке класса.|  
|[Метод COMClassicVTableCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Уведомляет профилировщик, что вызываемая оболочка (времени выполнения RCW) для заданного IID и класса был создан.|  
|[Метод COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Уведомляет профилировщик об удалении вызываемая оболочка времени Выполнения.|  
|[Метод ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Уведомляет профилировщик, управление передается соответствующему `catch` блока.|  
|[Метод ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Уведомляет профилировщик, управление передается за пределы соответствующего `catch` блока.|  
|[Метод ExceptionCLRCatcherExecute](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Устарело в .NET Framework версии 2.0.|  
|[Метод ExceptionCLRCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Устарело в .NET Framework 2.0.|  
|[Метод ExceptionOSHandlerEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Не реализовано. Профилировщик, которому необходимы сведения о неуправляемом исключении необходимо получить эти сведения другим способом.|  
|[Метод ExceptionOSHandlerLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Не реализовано. Профилировщик, которому необходимы сведения о неуправляемом исключении необходимо получить эти сведения другим способом.|  
|[Метод ExceptionSearchCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Уведомляет профилировщик, что на поисковом этапе обработки исключений был обнаружен обработчик для исключения.|  
|[Метод ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Уведомляет профилировщик выполнение пользовательского фильтра.|  
|[Метод ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Уведомляет профилировщик о том, что фильтр пользователей завершении выполнения.|  
|[Метод ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Уведомляет профилировщик, что на поисковом этапе обработки исключений ввел функции.|  
|[Метод ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Уведомляет профилировщик об окончании этапа поиска обработки исключений функции.|  
|[Метод ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Уведомляет профилировщик о том, что было создано исключение.|  
|[Метод ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Уведомляет профилировщик, фазы перемотки исключения входит обработка `finally` предложение, содержащегося в указанной функции.|  
|[Метод ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Уведомляет профилировщик, фазы перемотки исключения покинул обработки `finally` предложения.|  
|[Метод ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Уведомляет профилировщик этапа очистки во время обработки исключений вошел в функцию.|  
|[Метод ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Уведомляет профилировщик об окончании этапа очистки во время обработки исключений в функции.|  
|[Метод FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Уведомляет профилировщик о том, что среда выполнения начала выгрузку функции.|  
|[Метод Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Вызывается для инициализации профилировщика при запуске нового приложения среды CLR.|  
|[Метод JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Уведомляет профилировщик об окончании поиска для функции, которая была скомпилирована ранее с помощью NGen.exe.|  
|[Метод JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью NGen.exe.|  
|[Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Уведомляет профилировщик о завершении компиляции функции JIT-компилятором.|  
|[Метод JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Уведомляет профилировщик о начале just-in-time (JIT) компилятор для компиляции функции.|  
|[Метод JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Уведомляет профилировщик о том, что функция, которая после его JIT-компиляции был удален из памяти.|  
|[Метод JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Уведомляет профилировщик, что JIT-компилятор намерен вставить функцию в одну строку другой функции.|  
|[Метод ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Уведомляет профилировщик о переходе из управляемого кода в неуправляемый код.|  
|[Метод ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Уведомляет профилировщик, модуль присоединяется к его родительской сборки.|  
|[Метод ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Уведомляет профилировщик об окончании загрузки модуля.|  
|[Метод ModuleLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Уведомляет профилировщик о том, что при загрузке модуля.|  
|[Метод ModuleUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки модуля.|  
|[Метод ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Уведомляет профилировщик о выгрузке модуля.|  
|[Метод MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, которые были перемещены во время сборки мусора.|  
|[Метод ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Уведомляет профилировщик, для объекта выделена память в куче.|  
|[Метод ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Уведомляет профилировщик об объектах в памяти ссылается указанный объект.|  
|[Метод ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Уведомляет профилировщик о количестве экземпляров каждого заданного класса, которые были созданы с момента предыдущей сборки мусора.|  
|[Метод RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Уведомляет профилировщик о запуске удаленного вызова для завершения на клиенте.|  
|[Метод RemotingClientInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Уведомляет профилировщик о начале вызова удаленного взаимодействия.|  
|[Метод RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Уведомляет профилировщик, серверную часть вызова удаленного взаимодействия завершена, и теперь получает клиента и сведения для обработки ответа.|  
|[Метод RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.|  
|[Метод RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Уведомляет профилировщик, что процесс завершил вызов метода в ответ на запрос вызова удаленного метода.|  
|[Метод RemotingServerInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Уведомляет профилировщик о том, что процесс вызывает метод в ответ на запрос вызова удаленного метода.|  
|[Метод RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Уведомляет профилировщик о том, что процесс получает запрос удаленного метода вызова или активации.|  
|[Метод RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Уведомляет профилировщик, что процесс завершил обработку удаленного запроса вызова метода и собирается передачи ответа по каналу.|  
|[Метод RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Уведомляет профилировщик с информацией о корневых ссылках после сборки мусора.|  
|[Метод RuntimeResumeFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Уведомляет профилировщик, что среда выполнения возобновил все потоки среды выполнения и вернулся к нормальной работе.|  
|[Метод RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Уведомляет профилировщик о том, что среда выполнения возобновляет работу всех потоков во время выполнения.|  
|[Метод RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Уведомляет профилировщик о том, что среда выполнения прервала приостановку выполнения.|  
|[Метод RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков во время выполнения.|  
|[Метод RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Уведомляет профилировщик, что среда выполнения собирается приостановить все потоки во время выполнения.|  
|[Метод RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Уведомляет профилировщик о том, что указанный поток возобновлен после приостановки.|  
|[Метод RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Уведомляет профилировщик был указанный поток или быть, приостановлено.|  
|[Метод Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Уведомляет профилировщик о том, что приложение завершает работу.|  
|[Метод ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы (ОС).|  
|[Метод ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Уведомляет профилировщик, что был создан поток.|  
|[Метод ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Уведомляет профилировщик о том, что поток был удален.|  
|[Метод UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Уведомляет профилировщик о переход от неуправляемого кода в управляемый код.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает метод в `ICorProfilerCallback` (или [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) интерфейс для уведомления профилировщика, когда событие, на который подписан профилировщик, происходит. Это основной интерфейс обратного вызова через который среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода необходимо реализовать методы `ICorProfilerCallback` интерфейса. Для платформы .NET Framework версии 2.0 или более поздней версии, профилировщик должен также реализовать `ICorProfilerCallback2` методы. Каждая реализация метода должны возвращать значение HRESULT со значением S_OK в случае успешного выполнения или E_FAIL в случае ошибки. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемого каждой обратного вызова, за исключением [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 В реестре Windows, профилировщик кода необходимо зарегистрировать его объекта модели объектов компонентов (COM), который реализует `ICorProfilerCallback` и `ICorProfilerCallback2` интерфейсов. Профилировщик кода подписывается на события, для которых требуется получать уведомления путем вызова [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Затем, профилировщик может получать уведомления из среды выполнения при возникновении события о или просто произошла в процессе среды выполнения.  
  
> [!NOTE]
>  Профилировщик регистрирует один COM-объектом. Если профилировщик предназначен для .NET Framework версии 1.0 или 1.1, что COM-объект должен реализовывать только методы `ICorProfilerCallback`. Если он предназначен для платформы .NET Framework версии 2.0 или более поздней версии, COM-объект также должен реализовывать методы `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
