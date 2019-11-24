---
title: Перечисления профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: bc90743fb348c31bd2f7487c1573ec38a43bd3af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447446"
---
# <a name="profiling-enumerations"></a>Перечисления профилирования
В этом разделе описываются неуправляемые перечисления, которые использует API профилирования.  
  
## <a name="in-this-section"></a>Содержание  
 [Перечисление COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 Указывает тип предложения исключения, код которого был только что введен или удален.  
  
 [Перечисление COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.  
  
 [Перечисление COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 Описывает метод завершения для объекта.  
  
 [Перечисление COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 Идентифицирует создание сборки мусора.  
  
 [Перечисление COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 Указывает причину возникновения сборки мусора.  
  
 [Перечисление COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 Указывает свойства корня сборщика мусора.  
  
 [Перечисление COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.  
  
 [Перечисление COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.  
  
 [Перечисление COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 Указывает результат кэшированной функции поиска.  
  
 [Перечисление COR_PRF_MISC](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 Содержит постоянные значения, которые указывают специальные идентификаторы.  
  
 [Перечисление COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 Указывает свойства модуля.  
  
 [Перечисление COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 Содержит значения, используемые для указания поведения, возможностей или событий, на которые желает подписаться профилировщик.  
  
 [Перечисление COR_PRF_RUNTIME_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 Содержит значения, которые указывают версию среды CLR.  
  
 [Перечисление COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 Указывает количество данных для обратной передачи со снимком стека в каждом вызове функции профилировщика `StackSnapshotCallback`.  
  
 [Перечисление COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество.  
  
 [Перечисление COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 Указывает причину приостановки среды выполнения.  
  
 [Перечисление COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 Указывает причину перехода из управляемого в неуправляемый код или наоборот.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
