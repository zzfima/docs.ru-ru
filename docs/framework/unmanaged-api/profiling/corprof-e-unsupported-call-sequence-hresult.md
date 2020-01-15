---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: a0b117949190bcaffc334c208fff6e04a6a2c5bf
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964500"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT был введен в .NET Framework версии 2,0. .NET Framework 4 возвращает это значение HRESULT в двух сценариях:  
  
- Когда захватывающий профилировщик принудительно сбрасывает контекст регистрации потока в произвольный момент времени, чтобы поток попытается получить доступ к структурам, которые находятся в непротиворечивом состоянии.  
  
- Когда профилировщик пытается вызвать информационный метод, который активирует сбор мусора из метода обратного вызова, запрещающего сборку мусора.  
  
 Эти два сценария обсуждаются в следующих разделах.  
  
## <a name="hijacking-profilers"></a>Захват профилировщиков  
 (В основном это проблема с захватом профилировщиков, хотя бывают случаи, когда незахватывающие профилировщики могут видеть это значение HRESULT.)  
  
 В этом сценарии захватывающий профилировщик принудительно сбрасывает контекст регистрации потока в произвольный момент времени, чтобы поток мог ввести код профилировщика или повторно ввести среду CLR с помощью метода [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) .  
  
 Многие из идентификаторов, предоставляемых API профилирования, указывают на структуры данных в среде CLR. Многие `ICorProfilerInfo` вызовы просто считывают информацию из этих структур данных и передают их обратно. Однако среда CLR может изменить все эти структуры при ее выполнении и использовать блокировки для этого. Предположим, что среда CLR уже удерживает (или пытается получить) блокировку во время перехвата потоком профилировщика. Если поток повторно входит в среду CLR и пытается получить больше блокировок или проверять структуры, которые были в процессе изменения, эти структуры могут находиться в нестабильном состоянии. В таких ситуациях можно легко вызывать взаимоблокировки и нарушения прав доступа.  
  
 Как правило, когда незахватывающий профилировщик выполняет код внутри метода [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) и вызывает метод `ICorProfilerInfo` с допустимыми параметрами, он не должен быть взаимоблокировками или получать нарушение прав доступа. Например, код профилировщика, который выполняется внутри метода [ICorProfilerCallback:: класслоадфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) , может запросить сведения о классе, вызвав метод [ICorProfilerInfo2:: GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) . Код может получить CORPROF_E_DATAINCOMPLETE HRESULT, чтобы указать, что информация недоступна; Однако он не будет взаимоблокировками или получить нарушение прав доступа. Этот класс вызовов в `ICorProfilerInfo` называется синхронным, так как они создаются из метода `ICorProfilerCallback`.  
  
 Однако управляемый поток, который выполняет код, не находящиеся в методе `ICorProfilerCallback`, считается асинхронным вызовом. В .NET Framework версии 1 было сложно определить, что может произойти в асинхронном вызове. Вызов может привести к взаимоблокировке, сбою или дать недопустимый ответ. В .NET Framework версии 2,0 появились некоторые простые проверки, которые помогут избежать этой проблемы. В .NET Framework 2,0 при асинхронном вызове ненадежной функции `ICorProfilerInfo` происходит сбой с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE значением HRESULT.  
  
 Как правило, асинхронные вызовы не являются надежными. Однако следующие методы являются надежными и специально поддерживают асинхронные вызовы:  
  
- [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
- [жетсреадаппдомаин](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
- [жетклассидинфо](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [исаррайкласс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Дополнительные сведения см. в записи, [зачем CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) в блоге API профилирования CLR.  
  
## <a name="triggering-garbage-collections"></a>Запуск сборок мусора  
 В этом сценарии используется профилировщик, работающий в методе обратного вызова (например, один из методов `ICorProfilerCallback`), который запрещает сбор мусора. Если профилировщик пытается вызвать информационный метод (например, метод в интерфейсе `ICorProfilerInfo`), который может запустить сборку мусора, то информационный метод завершается с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE значением HRESULT.  
  
 В следующей таблице показаны методы обратного вызова, запрещающие сборки мусора, и информационные методы, которые могут запускать сборку мусора. Если профилировщик выполняется внутри одного из указанных методов обратного вызова и вызывает один из указанных информационных методов, этот информационный метод завершается с ошибкой CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Методы обратного вызова, запрещающие сборку мусора|Информационные методы, инициирующие сборку мусора|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ексцептионунвиндфунктионлеаве](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ексцептионунвиндфиналлентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [Exceptionunwindfinallyleave-](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ексцептионкатчерентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [рунтимесуспендстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [рунтимесуспендабортед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [обжектсаллокатедбикласс](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [хандлекреатед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [хандледестройед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [сетилинструментедкодемап](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [жетклассфромтокен](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [жетфунктионфромтокенандтипеаргс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [жетаппдомаининфо](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [рекуестпрофилердетач](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [жетаппдомаинсконтаинингмодуле](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
