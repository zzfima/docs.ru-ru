---
title: Перечисления профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 1a9781fa1b4b608152faa7d5edc80bd4866f0c81
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868139"
---
# <a name="profiling-enumerations"></a>Перечисления профилирования
В этом разделе описываются неуправляемые перечисления, которые использует API профилирования.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перечисление COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md)  
 Указывает тип предложения исключения, код которого был только что введен или удален.  
  
 [Перечисление COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)  
 Определяет флаги создания кода, которые можно задать с помощью метода [икорпрофилерфунктионконтрол:: SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
 [Перечисление COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md)  
 Описывает метод завершения для объекта.  
  
 [Перечисление COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md)  
 Идентифицирует создание сборки мусора.  
  
 [Перечисление COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md)  
 Указывает причину возникновения сборки мусора.  
  
 [Перечисление COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md)  
 Указывает свойства корня сборщика мусора.  
  
 [Перечисление COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md)  
 Указывает тип корня сборщика мусора, предоставляемый обратным вызовом [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) .  
  
 [Перечисление COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)  
 Предоставляет флаги в дополнение к тем, которые находятся в перечислении [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) , которые профилировщик может указать в методе [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) при загрузке.  
  
 [Перечисление COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md)  
 Указывает результат кэшированной функции поиска.  
  
 [Перечисление COR_PRF_MISC](cor-prf-misc-enumeration.md)  
 Содержит постоянные значения, которые указывают специальные идентификаторы.  
  
 [Перечисление COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md)  
 Указывает свойства модуля.  
  
 [Перечисление COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)  
 Содержит значения, используемые для указания поведения, возможностей или событий, на которые желает подписаться профилировщик.  
  
 [Перечисление COR_PRF_RUNTIME_TYPE](cor-prf-runtime-type-enumeration.md)  
 Содержит значения, которые указывают версию среды CLR.  
  
 [Перечисление COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md)  
 Указывает количество данных для обратной передачи со снимком стека в каждом вызове функции профилировщика `StackSnapshotCallback`.  
  
 [Перечисление COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md)  
 Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество.  
  
 [Перечисление COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md)  
 Указывает причину приостановки среды выполнения.  
  
 [Перечисление COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md)  
 Указывает причину перехода из управляемого в неуправляемый код или наоборот.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](profiling-overview.md)  
  
 [Интерфейсы профилирования](profiling-interfaces.md)  
  
 [Глобальные статические функции профилирования](profiling-global-static-functions.md)  
  
 [Структуры профилирования](profiling-structures.md)
