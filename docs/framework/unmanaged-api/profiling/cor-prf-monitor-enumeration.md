---
title: Перечисление COR_PRF_MONITOR
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 321ad53ca5f773191c5b5d1084b36caa6aeae4dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137051"
---
# <a name="cor_prf_monitor-enumeration"></a>Перечисление COR_PRF_MONITOR
Содержит значения, используемые для указания поведения, возможностей или событий, на которые желает подписаться профилировщик.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>Members  
 В следующих разделах перечисляются `COR_PRF_MONITOR` членов перечисления по категориям. Категории:  
  
- [Флаги не заданы](#None)  
  
- [Флаги обратного вызова](#Callback)  
  
- [Флаги включения функций](#Feature)  
  
- [Флаги конфигурации](#Config)  
  
- [Составные флаги](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>Флаги не заданы  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Флаги не установлены.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Флаги обратного вызова  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Активирует все события обратного вызова.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Управляет обратными вызовами `AppDomainCreation*` и `AppDomainShutdown*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Управляет обратными вызовами `AssemblyLoad*` и `AssemblyUnload*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Управляет обратными вызовами `JITCachedFunctionSearch*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).<br /><br /> Поведение этого флага в платформе .NET Framework версии 2.0 изменено.|  
|`COR_PRF_MONITOR_CCW`|Управляет обратными вызовами `COMClassicVTable*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Управляет обратными вызовами `ClassLoad*` и `ClassUnload*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Управляет обратными вызовами `ExceptionCLRCatcher*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Управляет обратными вызовами [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) и [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Управляет [глобальными статическими функциями профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)`FunctionEnter*`, `FunctionLeave*`и `FunctionTailCall*`.|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Управляет обратными вызовами [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) и обратными вызовами `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*` и `ExceptionCatcher*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Управляет обратным вызовом [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_GC`|Управляет обратными вызовами [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md) и [FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) и интерфейсах `ICorProfilerCallback*`. При выделении `COR_PRF_MONITOR_GC` отключена параллельная сборка мусора.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Управляет обратными вызовами `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md) и [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Управляет обратными вызовами `ModuleLoad*`, `ModuleUnload*` и [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Управляет обратным вызовом [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_REMOTING`|Управляет обратными вызовами `Remoting*` в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Определяет, будут ли обратные вызовы `Remoting*` отслеживать асинхронные события.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Определяет, будут ли передаваться файлы cookie для обратных вызовов `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|Управляет обратными вызовами `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md) и [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) в интерфейсе [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_THREADS`|Управляет обратными вызовами [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md) и [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) в интерфейсах [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) и [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md).|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Флаги включения компонентов  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Включает извлечение точного значения `ClassID` для базовой функции путем вызова метода [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) со значением `COR_PRF_FRAME_INFO`, возвращаемым обратным вызовом [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md).|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Включает трассировку аргумента с помощью обратного вызова [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) или [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) и метода [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md).|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Включает трассировку возвращаемых значений с помощью обратного вызова [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) или [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) и метода [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md).|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Не рекомендуется.<br /><br /> Отладка в процессе работы не поддерживается. Этот флаг ни на что не влияет.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Не рекомендуется.<br /><br /> Позволяет профилировщику получать сопоставления промежуточного и машинного языка с помощью [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md). Начиная с платформы .NET Framework версии 2.0, среда выполнения всегда отслеживает сопоставления промежуточного и машинного языков, поэтому данный флаг всегда считается установленным.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Сообщает среде выполнения о том, что профилировщик может захотеть получать уведомления о распределениях объекта. Этот флаг должен быть установлен во время инициализации. Он позволяет профилировщику последовательно использовать флаг `COR_PRF_MONITOR_OBJECT_ALLOCATED` для получения обратных вызовов [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).|  
|`COR_PRF_ENABLE_REJIT`|Включает вызовы методов [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) и [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md). Профилировщик должен установить этот флаг при запуске.  Если профилировщик указывает этот флаг, он также должен указать и `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Включает вызов метода [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md).|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Флаги конфигурации  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Запрещает загрузку всех машинных образов (включая образы, улучшенные профилировщиком).  Если этот флаг и флаг `COR_PRF_USE_PROFILE_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Отключает все встраивания.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Отключает все оптимизации кода.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Отключает проверки прозрачности безопасности, которые обычно производятся во время JIT-компиляции и загрузки классов для обеспечения полного доверия к сборкам. Это может облегчить выполнение некоторых инструментирований.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Вызывает поиск машинного образа для поиска образов, улучшенных профилировщиком. Если для данной сборки образов, улучшенных профилировщиком, не найдено, среда CLR возвращается к JIT для этой сборки. Если этот флаг и флаг `COR_PRF_DISABLE_ALL_NGEN_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a>Составные флаги  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_ALL`|Представляет все значения флагов `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению. В разделе "Синтаксис" указываются отдельные флаги, которые присутствуют в этой битовой маске.|  
|`COR_PRF_MONITOR_ALL`|Активирует все события обратного вызова.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены только во время инициализации. Попытка изменить какой-нибудь из этих флагов после инициализации вызовет значение `HRESULT`, указывающее на сбой.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Представляет все флаги `COR_PRF_MONITOR`, для которых необходимы улучшенные профилировщиком изображения.|  
  
## <a name="remarks"></a>Заметки  
 Значение `COR_PRF_MONITOR` используется с методами [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) для определения уведомлений о событиях, которые среда CLR создает для профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [Метод GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [Метод SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
