---
title: Объекты и функциональные возможности работы с потоками
ms.date: 08/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d56d962279120a03a6e4b89154ac1429ea5479e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483662"
---
# <a name="threading-objects-and-features"></a>Объекты и функциональные возможности работы с потоками

Вместе с классом <xref:System.Threading.Thread?displayProperty=nameWithType> .NET предоставляет ряд классов для разработки многопоточных приложений. В следующих статьях приведены общие сведения об этих классах:

|Заголовок|Описание:|  
|-----------|-----------------|  
|[Пул управляемых потоков](the-managed-thread-pool.md)|Описание класса <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, который предоставляет пул рабочих потоков, управляемых .NET.|  
|[Таймеры](timers.md)|Описывает таймеры, которые можно использовать в многопоточной среде.|
|[Обзор примитивов синхронизации](overview-of-synchronization-primitives.md)|Описывает классы, которые могут использоваться для синхронизации доступа к данным или для управления взаимодействием потоков.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.|
|[Мьютексы](mutexes.md)|Описывает использование объекта <xref:System.Threading.Mutex?displayProperty=nameWithType> для синхронизации доступа к объекту или создания собственных механизмов синхронизации.|
|[Блокируемые операции](interlocked-operations.md)|Описывает класс <xref:System.Threading.Interlocked?displayProperty=nameWithType>, который предоставляет атомарные операции для переменных, используемых совместно несколькими потоками.|
|[Блокировки чтения и записи](reader-writer-locks.md)|Описывает класс <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType>, который предоставляет семантику с одним модулем записи и несколькими модулями чтения.|
|[Классы Semaphore и SemaphoreSlim](semaphore-and-semaphoreslim.md)|Описывает класс <xref:System.Threading.Semaphore?displayProperty=nameWithType> и его использование для управления доступом к ограниченным ресурсам.|
|[Barrier](barrier.md)|Описывает класс <xref:System.Threading.Barrier?displayProperty=nameWithType>, реализующий шаблон барьера для координации потоков при выполнении поэтапных операций.|
|[SpinLock](spinlock.md)|Описывает класс <xref:System.Threading.SpinLock?displayProperty=nameWithType>, упрощенную альтернативу классу <xref:System.Threading.Monitor?displayProperty=nameWithType> для определенных низкоуровневых сценариев.|
|[SpinWait](spinwait.md)|Описывает класс <xref:System.Threading.SpinWait?displayProperty=nameWithType>, низкоуровневый примитив синхронизации, выполняющий цикличную работу в режиме занятости до инициирования ожидания ядра.|

## <a name="see-also"></a>См. также

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Использование потоков и работа с потоками](using-threads-and-threading.md)
- [Асинхронный файловый ввод-вывод](../io/asynchronous-file-i-o.md)
- [Параллельное программирование](../parallel-programming/index.md)
- [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md)
