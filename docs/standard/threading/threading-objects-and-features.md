---
title: Объекты и функциональные возможности работы с потоками
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: dd9b7b8cb194353d0a1c285af10d54dc7366896e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128960"
---
# <a name="threading-objects-and-features"></a>Объекты и функциональные возможности работы с потоками

Вместе с классом <xref:System.Threading.Thread?displayProperty=nameWithType> .NET предоставляет ряд классов для разработки многопоточных приложений. В следующих статьях приведены общие сведения об этих классах:

|Заголовок|Описание|  
|-----------|-----------------|  
|[Пул управляемых потоков](the-managed-thread-pool.md)|Описание класса <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, который предоставляет пул рабочих потоков, управляемых .NET.|  
|[Таймеры](timers.md)|Описывает таймеры .NET, которые можно использовать в многопоточной среде.|
|[Обзор примитивов синхронизации](overview-of-synchronization-primitives.md)|Описывает типы, которые можно использовать для синхронизации доступа к общему ресурсу или для управления взаимодействием потоков.|
|[EventWaitHandle](eventwaithandle.md)|Описывает класс <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, который представляет событие синхронизации потока.|
|[CountdownEvent](countdownevent.md)|Описывает класс <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>, который представляет событие синхронизации потока, задаваемое при отсчете до нуля.|
|[Мьютексы](mutexes.md)|Описывает класс <xref:System.Threading.Mutex?displayProperty=nameWithType>, который предоставляет монопольный доступ к общему ресурсу.|
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
