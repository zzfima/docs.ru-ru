---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb3e382a93f28ea99c66268e6e402ea275961047
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387199"
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT появилась в .NET Framework версии 2.0. [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Возвращает это значение HRESULT в двух сценариях:  
  
-   Когда захватывающий профилировщик принудительно сбрасывает потока зарегистрируйте контекст в произвольный момент таким образом, чтобы поток пытается получить доступ к структурам, которые находятся в несогласованном состоянии.  
  
-   При попытке вызвать метод информационное, который инициирует сбор мусора из метода обратного вызова профилировщика, запрещающего сборку мусора.  
  
 В следующих разделах рассматриваются эти два сценария.  
  
## <a name="hijacking-profilers"></a>Захват профилировщики  
 (Этот сценарий является главным образом неполадку Захватывающие профилировщики, несмотря на то, что существуют случаи, где не Захватывающие профилировщики могут просматривать данный HRESULT).  
  
 В этом случае захватывающий профилировщик принудительно сбрасывает контекст регистра потока в произвольный момент таким образом, чтобы поток можно ввести код профилировщика или повторно введите общеязыковой среды выполнения (CLR) через [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) метод.  
  
 Многие из идентификаторов, что API профилирования предоставляет точки к структурам данных в среде CLR. Многие `ICorProfilerInfo` вызовы просто считывать данные из этих структур данных и передают их обратно. Тем не менее CLR может изменять вещи в этих структурах, так как он работает и может использовать блокировки для этого. Предположим, что среда CLR уже удерживает (или попытке получить) блокировку во время захвата потока профилировщиком. Если поток повторно входит в среду CLR и пытается получить несколько блокировок или проверять структуры, которые были в процессе изменения, эти структуры могут быть в несогласованном состоянии. Взаимоблокировки и нарушение прав доступа, легко могут происходить в таких ситуациях.  
  
 Как правило, в том случае, когда не захватывающий профилировщик запустит код внутри [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) метод и выполняет вызов в `ICorProfilerInfo` метод с допустимыми параметрами, его не следует принимать участие во взаимоблокировке или нарушение доступа. Например, профилировщик код, выполняемый внутри [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) путем вызова метода может запросить сведения о классе [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) метод. Код может получать значение HRESULT CORPROF_E_DATAINCOMPLETE, чтобы указать, что информация недоступна; Тем не менее он не будет принимать участие во взаимоблокировке или нарушение доступа. Этот класс вызывает `ICorProfilerInfo` называются синхронными, так как они будут осуществляться `ICorProfilerCallback` метод.  
  
 Тем не менее, управляемый поток, выполняет код, который не находится в `ICorProfilerCallback` считается осуществлять асинхронный вызов метода. В платформе .NET Framework версии 1 было сложно определить, что может произойти в асинхронный вызов. Вызов может принимать участие во взаимоблокировке, сбой или дать недопустимый ответ. В .NET Framework версии 2.0 появились некоторые простые проверки, чтобы избежать этой проблемы. В .NET Framework 2.0, если вы вызываете небезопасный `ICorProfilerInfo` работать асинхронно, он завершается с ошибкой CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Как правило асинхронные вызовы не являются безопасными. Однако следующие методы являются безопасными и специально поддерживает асинхронные вызовы:  
  
-   [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [Метод GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [Метод GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Дополнительные сведения см. в записи [почему у нас есть CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://go.microsoft.com/fwlink/?LinkId=169156) в блоге API профилирования CLR.  
  
## <a name="triggering-garbage-collections"></a>Запуск коллекции мусора  
 Этот сценарий включает профилировщик, который работает внутри метода обратного вызова (например, один из `ICorProfilerCallback` методы), запрещающего сборку мусора. Если профилировщик пытается вызвать информационный метод (например, метод `ICorProfilerInfo` интерфейс), может запустить сбор мусора, информационный метод завершается с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 Следующая таблица отображает методы обратного вызова, запрещающие сбор мусора и информационные методы, которые могут запустить сбор мусора. Если профилировщик выполняется внутри одного из перечисленных методов обратного вызова и вызывает один из перечисленных информационные методов, что информационный метод завершается с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Методы обратного вызова, запрещающие сбор мусора|Информационные методы, которые запустить сбор мусора|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
