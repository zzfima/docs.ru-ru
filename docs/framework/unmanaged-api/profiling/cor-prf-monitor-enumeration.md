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
ms.openlocfilehash: b6c3dc78b9c503747c7a2d404706eb797790b931
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175204"
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
  
## <a name="members"></a>Члены  
 Следующие разделы перечислять `COR_PRF_MONITOR` членов списка по категориям. Категории:  
  
- [Нет флагов набор](#None)  
  
- [Флаги обратного вызова](#Callback)  
  
- [Флаги включения компонентов](#Feature)  
  
- [Флаги конфигурации](#Config)  
  
- [Составные флаги](#Composite)  
  
<a name="None"></a>
### <a name="no-flags-set"></a>Нет флагов набор  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|Флаги не установлены.|  
  
<a name="Callback"></a>
### <a name="callback-flags"></a>Флаги обратного вызова  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Активирует все события обратного вызова.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Контролирует `AppDomainCreation*` и `AppDomainShutdown*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Контролирует `AssemblyLoad*` и `AssemblyUnload*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Контролирует `JITCachedFunctionSearch*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)<br /><br /> Поведение этого флага в платформе .NET Framework версии 2.0 изменено.|  
|`COR_PRF_MONITOR_CCW`|Контролирует `COMClassicVTable*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Контролирует `ClassLoad*` и `ClassUnload*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Контролирует `ExceptionCLRCatcher*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Контролирует [неуправляемыепереходные](icorprofilercallback-unmanagedtomanagedtransition-method.md) и [управляемыепереходы](icorprofilercallback-managedtounmanagedtransition-method.md) в [интерфейсе ICorProfilerCallback](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Контролирует и `FunctionTailCall*` [профилирование глобальных статических функций.](profiling-global-static-functions.md) `FunctionEnter*` `FunctionLeave*`|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Контролирует обратный вызов [ExceptionThrown](icorprofilercallback-exceptionthrown-method.md) `ExceptionSearch*` `ExceptionUnwind*`и, `ExceptionCatcher*` `ExceptionOSHandler*`и , и обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Контролирует [вызов FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md) в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_GC`|Управление [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](icorprofilercallback-movedreferences-method.md), [MovedReferences2](icorprofilercallback4-movedreferences2-method.md), [SurvivingReferences](icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](icorprofilercallback-rootreferences-method.md), RootReferences , `ICorProfilerCallback*` [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [HandleCreated](icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md), и [FinalizeableObject'](icorprofilercallback2-finalizeableobjectqueued-method.md) обратные вызовы в интерфейсах. При `COR_PRF_MONITOR_GC` выделении одновременного сбора мусора отключается.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Контролирует `JITCompilation*`, [JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md), и [JITInlining](icorprofilercallback-jitinlining-method.md) обратных вызовов в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Управляет `ModuleLoad*`обратными `ModuleUnload*`вызовами [ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Управляет [обратным](icorprofilercallback-objectallocated-method.md) вызовом ObjectAllocated в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_REMOTING`|Контролирует `Remoting*` обратные вызовы в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Определяет, будут ли обратные вызовы `Remoting*` отслеживать асинхронные события.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Определяет, будут ли передаваться файлы cookie для обратных вызовов `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|Контролирует `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md), и [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md) обратных вызовов в интерфейсе [ICorProfilerCallback.](icorprofilercallback-interface.md)|  
|`COR_PRF_MONITOR_THREADS`|Контролирует [ThreadCreated,](icorprofilercallback-threadcreated-method.md) [ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md), и [ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md) обратных вызовов в [ICorProfilerCallback](icorprofilercallback-interface.md) и [ICorProfilerCallback2](icorprofilercallback2-interface.md) интерфейсов.|  
  
<a name="Feature"></a>
### <a name="feature-enabling-flags"></a>Флаги включения компонентов  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Позволяет получить `ClassID` точное для общего функции, позвонив в метод [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) со значением, `COR_PRF_FRAME_INFO` возвращенным обратным вызовом [FunctionEnter2.](functionenter2-function.md)|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Позволяет отслеживать аргументы с помощью вызова [FunctionEnter2](functionenter2-function.md) или [вызова FunctionEnter3WithInfo](functionenter3withinfo-function.md) и метода [GetFunctionEnter3Info.](icorprofilerinfo3-getfunctionenter3info-method.md)|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Позволяет отслеживать значения возврата с помощью обратного вызова [FunctionLeave2](functionleave2-function.md) или вызова [FunctionLeave3WithInfo](functionleave3withinfo-function.md) и [метода GetFunctionLeave3Info.](icorprofilerinfo3-getfunctionleave3info-method.md)|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Не рекомендуется.<br /><br /> Отладка в процессе работы не поддерживается. Этот флаг ни на что не влияет.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Не рекомендуется.<br /><br /> Позволяет профилировщику получать карты IL-to-native с помощью [GetILToNativeMapping.](icorprofilerinfo-getiltonativemapping-method.md) Начиная с платформы .NET Framework версии 2.0, среда выполнения всегда отслеживает сопоставления промежуточного и машинного языков, поэтому данный флаг всегда считается установленным.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Сообщает среде выполнения о том, что профилировщик может захотеть получать уведомления о распределениях объекта. Этот флаг должен быть установлен во время инициализации. Это позволяет профайлеру `COR_PRF_MONITOR_OBJECT_ALLOCATED` впоследствии использовать флаг для получения обратных вызовов [ObjectAllocated.](icorprofilercallback-objectallocated-method.md)|  
|`COR_PRF_ENABLE_REJIT`|Позволяет выполнять вызовы в методы [RequestReJIT](icorprofilerinfo4-requestrejit-method.md) и [RequestRevert.](icorprofilerinfo4-requestrevert-method.md) Профилировщик должен установить этот флаг при запуске.  Если профилировщик указывает этот флаг, он также должен указать и `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Позволяет звонить в метод [DoStackSnapshot.](icorprofilerinfo2-dostacksnapshot-method.md)|  
  
<a name="Config"></a>
### <a name="configuration-flags"></a>Флаги конфигурации  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Запрещает загрузку всех машинных образов (включая образы, улучшенные профилировщиком).  Если этот флаг и флаг `COR_PRF_USE_PROFILE_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Отключает все встраивания.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Отключает все оптимизации кода.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Отключает проверки прозрачности безопасности, которые обычно производятся во время JIT-компиляции и загрузки классов для обеспечения полного доверия к сборкам. Это может облегчить выполнение некоторых инструментирований.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Вызывает поиск машинного образа для поиска образов, улучшенных профилировщиком. Если для данной сборки образов, улучшенных профилировщиком, не найдено, среда CLR возвращается к JIT для этой сборки. Если этот флаг и флаг `COR_PRF_DISABLE_ALL_NGEN_IMAGES` указаны, используется `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>
### <a name="composite-flags"></a>Составные флаги  
  
|Участник|Описание|  
|------------|-----------------|  
|`COR_PRF_ALL`|Представляет все значения флагов `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены после присоединения профилировщика к выполняющемуся приложению. В разделе "Синтаксис" указываются отдельные флаги, которые присутствуют в этой битовой маске.|  
|`COR_PRF_MONITOR_ALL`|Активирует все события обратного вызова.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Представляет все флаги `COR_PRF_MONITOR`, которые могут быть установлены только во время инициализации. Попытка изменить какой-нибудь из этих флагов после инициализации вызовет значение `HRESULT`, указывающее на сбой.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Представляет все флаги `COR_PRF_MONITOR`, для которых необходимы улучшенные профилировщиком изображения.|  
  
## <a name="remarks"></a>Remarks  
 Значение `COR_PRF_MONITOR` используется с [iCorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) и [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) методы для определения уведомления о событии, что общий язык время выполнения делает для профайлера.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления профилирования](profiling-enumerations.md)
- [Метод GetEventMask](icorprofilerinfo-geteventmask-method.md)
- [Метод SetEventMask](icorprofilerinfo-seteventmask-method.md)
