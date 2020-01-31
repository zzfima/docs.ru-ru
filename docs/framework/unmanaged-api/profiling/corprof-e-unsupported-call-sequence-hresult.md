---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: b4ab5c8f7cdca1303cb4fbbc4fa39db3c5977c15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867013"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT

CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT был введен в .NET Framework версии 2,0. .NET Framework 4 возвращает это значение HRESULT в двух сценариях:  
  
- Когда захватывающий профилировщик принудительно сбрасывает контекст регистрации потока в произвольный момент времени, чтобы поток попытается получить доступ к структурам, которые находятся в непротиворечивом состоянии.  
  
- Когда профилировщик пытается вызвать информационный метод, который активирует сбор мусора из метода обратного вызова, запрещающего сборку мусора.  
  
Эти два сценария обсуждаются в следующих разделах.  
  
## <a name="hijacking-profilers"></a>Захват профилировщиков  

  (В основном это проблема с захватом профилировщиков, хотя в некоторых случаях незахватывающие профилировщики могут видеть это значение HRESULT.)  
  
 В этом сценарии захватывающий профилировщик принудительно сбрасывает контекст регистрации потока в произвольный момент времени, чтобы поток мог ввести код профилировщика или повторно ввести среду CLR с помощью метода [ICorProfilerInfo](icorprofilerinfo-interface.md) .  
  
 Многие из идентификаторов, предоставляемых API профилирования, указывают на структуры данных в среде CLR. Многие `ICorProfilerInfo` вызовы просто считывают информацию из этих структур данных и передают их обратно. Однако среда CLR может изменить все эти структуры при ее выполнении и использовать блокировки для этого. Предположим, что среда CLR уже удерживает (или пытается получить) блокировку во время перехвата потоком профилировщика. Если поток повторно вводит среду CLR и пытается выполнить больше блокировок или проверять структуры, которые были в процессе изменения, эти структуры могут находиться в нестабильном состоянии. В таких ситуациях можно легко вызывать взаимоблокировки и нарушения прав доступа.  
  
 Как правило, когда незахватывающий профилировщик выполняет код внутри метода [ICorProfilerCallback](icorprofilercallback-interface.md) и вызывает метод `ICorProfilerInfo` с допустимыми параметрами, он не должен быть взаимоблокировками или получать нарушение прав доступа. Например, код профилировщика, который выполняется внутри метода [ICorProfilerCallback:: класслоадфинишед](icorprofilercallback-classloadfinished-method.md) , может запросить сведения о классе, вызвав метод [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) . Код может получить CORPROF_E_DATAINCOMPLETE HRESULT, чтобы указать, что информация недоступна. Однако он не будет взаимоблокировками или получить нарушение прав доступа. Эти вызовы в `ICorProfilerInfo` считаются синхронными, так как они создаются из метода `ICorProfilerCallback`.  
  
 Однако управляемый поток, который выполняет код, не находящиеся в методе `ICorProfilerCallback`, считается асинхронным вызовом. В .NET Framework версии 1 было сложно определить, что может произойти в асинхронном вызове. Вызов может привести к взаимоблокировке, сбою или дать недопустимый ответ. В .NET Framework версии 2,0 появились некоторые простые проверки, которые помогут избежать этой проблемы. В .NET Framework 2,0 при асинхронном вызове ненадежной функции `ICorProfilerInfo` происходит сбой с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE значением HRESULT.  
  
 Как правило, асинхронные вызовы не являются надежными. Однако следующие методы являются надежными и специально поддерживают асинхронные вызовы:  
  
- [GetEventMask](icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)  
  
- [жетсреадаппдомаин](icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)  
  
- [жетклассидинфо](icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [исаррайкласс](icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Дополнительные сведения см. в записи, [зачем CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) в блоге API профилирования CLR.  
  
## <a name="triggering-garbage-collections"></a>Запуск сборок мусора  
 В этом сценарии используется профилировщик, работающий в методе обратного вызова (например, один из методов `ICorProfilerCallback`), который запрещает сбор мусора. Если профилировщик пытается вызвать информационный метод (например, метод в интерфейсе `ICorProfilerInfo`), который может запустить сборку мусора, то информационный метод завершается с CORPROF_E_UNSUPPORTED_CALL_SEQUENCE значением HRESULT.  
  
 В следующей таблице показаны методы обратного вызова, запрещающие сборки мусора, и информационные методы, которые могут запускать сборку мусора. Если профилировщик выполняется внутри одного из указанных методов обратного вызова и вызывает один из указанных информационных методов, этот информационный метод завершается с ошибкой CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Методы обратного вызова, запрещающие сборку мусора|Информационные методы, инициирующие сборку мусора|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ексцептионунвиндфунктионлеаве](icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ексцептионунвиндфиналлентер](icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [Exceptionunwindfinallyleave-](icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ексцептионкатчерентер](icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [рунтимесуспендабортед](icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](icorprofilercallback-objectreferences-method.md)<br /><br /> [обжектсаллокатедбикласс](icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](icorprofilercallback-rootreferences-method.md)<br /><br /> [хандлекреатед](icorprofilercallback2-handlecreated-method.md)<br /><br /> [хандледестройед](icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [сетилинструментедкодемап](icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](icorprofilerinfo-forcegc-method.md)<br /><br /> [жетклассфромтокен](icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [жетфунктионфромтокенандтипеаргс](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [жетаппдомаининфо](icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](icorprofilerinfo3-enummodules-method.md)<br /><br /> [рекуестпрофилердетач](icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [жетаппдомаинсконтаинингмодуле](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Интерфейс ICorProfilerCallback3](icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Профилирование](index.md)
