---
title: Профилирующие интерфейсы
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: adc47417265d32d79508af949c118c4d31a83365
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124200"
---
# <a name="profiling-interfaces"></a>Профилирующие интерфейсы
В этом разделе описываются неуправляемые интерфейсы, позволяющие профилировать программу, выполняемую в среде CLR.  
  
## <a name="in-this-section"></a>Содержание  
 [Интерфейс ICLRProfiling](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 Предоставляет метод [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) , который позволяет профилировщику присоединяться к выполняющемуся процессу.  
  
 [Интерфейс ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 Позволяет профилировщику сообщать о CLR ссылок на сборки, которые профилировщик будет добавлять в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .  
  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 Предоставляет методы, используемые средой CLR для уведомления профилировщика кода при событиях, на которые подписан профилировщик.  
  
 [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 Расширяет интерфейс `ICorProfilerCallback` обратными вызовами, поддерживаемыми платформой .NET Framework 2.0 и более поздней версии.  
  
 [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о подключенном и отключенном состоянии профилировщику.  
  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений профилировщику.  
  
 [Интерфейс ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 Предоставляет метод, идентифицирующий транзитивное замыкание объектов, на которые ссылаются корни сборки мусора.  
  
 [Интерфейс ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 Предоставляет метод обратного вызова, который используется средой CLR для уведомления профилировщика о загрузке сборки.  
  
 [Интерфейс ICorProfilerCallback7](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что поток символов, связанный с модулем в памяти, обновлен.  

[Интерфейс ICorProfilerCallback8](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
Предоставляет методы обратного вызова, используемые средой CLR для уведомления профилировщика о начале и завершении JIT-компиляции динамического метода.

[Интерфейс ICorProfilerCallback9](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод уничтожается сборщиком мусора и затем выгружается.

 [Интерфейс ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.  
  
 [Интерфейс ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции функций в среде CLR.  
  
 [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.  
  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 Расширяет интерфейс `ICorProfilerInfo` методами, поддерживаемыми платформой .NET Framework 2.0 и более поздних версий.  
  
 [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 Расширяет интерфейс `ICorProfilerInfo2` с помощью методов, поддерживаемых в .NET Framework 4 и более поздних версиях.  
  
 [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.  
  
 [Интерфейс ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий.  
  
 [Интерфейс ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 Предоставляет перечислитель для всех методов, принадлежащих заданному модулю NGen и встроенных в тело данного метода.  
  
 [Интерфейс ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 Предоставляет метод для применения новых заданных метаданных к модулю и предоставляет доступ к потоку символов в памяти.  
  
 [Интерфейс ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.  
  
 [Интерфейс ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 Предоставляет методы для последовательного прохода по коллекции замороженных объектов, созданных [Ngen. exe (генератор образов в машинном кодах)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
 [Интерфейс ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.  
  
 [Интерфейс IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 Предоставляет метод [выделения](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) для выделения памяти для нового текста функции MSIL.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о профилировании](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [Структуры профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
