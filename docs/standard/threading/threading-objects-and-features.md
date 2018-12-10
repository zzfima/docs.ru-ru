---
title: Объекты и функциональные возможности работы с потоками
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a355c2e996ddb00dad804dfeb22987923d91aa6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144524"
---
# <a name="threading-objects-and-features"></a>Объекты и функциональные возможности работы с потоками

Вместе с классом <xref:System.Threading.Thread?displayProperty=nameWithType> .NET предоставляет ряд классов для разработки многопоточных приложений. В следующих статьях приведены общие сведения об этих классах:

|Заголовок|Описание|  
|-----------|-----------------|  
|[Пул управляемых потоков](the-managed-thread-pool.md)|Описание класса <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, который предоставляет пул рабочих потоков, управляемых .NET.|  
|[Таймеры](timers.md)|Описывает таймеры .NET, которые можно использовать в многопоточной среде.|
|[Обзор примитивов синхронизации](overview-of-synchronization-primitives.md)|Описывает типы, которые можно использовать для синхронизации доступа к общему ресурсу или для управления взаимодействием потоков.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.|
|[Мьютексы](mutexes.md)|Описывает <xref:System.Threading.Mutex?displayProperty=nameWithType>, который предоставляет монопольный доступ к общему ресурсу.|
|[Классы Semaphore и SemaphoreSlim](semaphore-and-semaphoreslim.md)|Описывает класс 3<xref:System.Threading.Semaphore?displayProperty=nameWithType>, ограничивающий число потоков, которые могут одновременно обращаться к ресурсу или пулу ресурсов.|
|[Barrier](barrier.md)|Описывает класс <xref:System.Threading.Barrier?displayProperty=nameWithType>, реализующий шаблон барьера для координации потоков при выполнении поэтапных операций.|
|[SpinLock](spinlock.md)|Описывает структуру <xref:System.Threading.SpinLock?displayProperty=nameWithType>, упрощенную альтернативу классу <xref:System.Threading.Monitor?displayProperty=nameWithType> для определенных низкоуровневых сценариев блокировки.|
|[SpinWait](spinwait.md)|Описывает структуру <xref:System.Threading.SpinWait?displayProperty=nameWithType>, которая обеспечивает поддержку ожидания на основе холостых циклов.|

## <a name="see-also"></a>См. также

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Использование потоков и работа с потоками](using-threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Параллельное программирование](../parallel-programming/index.md)
- [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md)
