---
title: Общие сведения о примитивах синхронизации
description: Узнайте о том, как с помощью примитивов синхронизации потоков .NET синхронизировать доступ к общему ресурсу или управлять взаимодействием потоков
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET],synchronizing threads
- managed threading
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24df4140e515483adb94fa542a7063bd2ae2120b
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479791"
---
# <a name="overview-of-synchronization-primitives"></a>Общие сведения о примитивах синхронизации

Платформа .NET предоставляет ряд типов для синхронизации доступа к общему ресурсу или координации взаимодействия потоков.

> [!IMPORTANT]
> С помощью одного экземпляра примитива синхронизации можно обеспечить защиту при каждом обращении к общему ресурсу. Можно использовать несколько экземпляров примитивов синхронизации, чтобы защитить доступ к ресурсу или некоторым частям кода, имеющим непосредственный доступ к ресурсу. При этом несколько потоков смогут обращаться к ресурсу одновременно.

## <a name="waithandle-class-and-lightweight-synchronization-types"></a>Класс WaitHandle и типы упрощенной синхронизации

Несколько примитивов синхронизации .NET являются производными от класса <xref:System.Threading.WaitHandle?displayProperty=nameWithType>, который инкапсулирует собственный дескриптор операционной системы синхронизации и использует механизм сигнализации для взаимодействия потоков. К ним относятся такие классы:

- <xref:System.Threading.Mutex?displayProperty=nameWithType>, который предоставляет монопольный доступ к общему ресурсу. Если мьютексом не владеет ни один поток, сообщается состояние мьютекса.
- <xref:System.Threading.Semaphore?displayProperty=nameWithType>, ограничивающий число потоков, которые могут одновременно обращаться к ресурсу или пулу ресурсов. Состояние семафора становится сигнальным, когда это число становится больше нуля, и несигнальным, когда равно нулю.
- <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, который представляет событие синхронизации потоков и может быть в сигнальном или несигнальном состоянии.
- <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, который является производным от <xref:System.Threading.EventWaitHandle> и при получении сигнала автоматически сбрасывается в сигнальное состояние после освобождения одиночного потока в состоянии ожидания.
- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, который является производным от <xref:System.Threading.EventWaitHandle> и при получении сигнала остается в сигнальном состоянии до вызова метода <xref:System.Threading.EventWaitHandle.Reset%2A>.

Так как <xref:System.Threading.WaitHandle> наследует <xref:System.MarshalByRefObject?displayProperty=nameWithType>, в .NET Framework эти типы можно использовать для синхронизации действий потоков за пределами доменов приложений.

В .NET Framework и .NET Core некоторые из этих типов могут быть именованными дескрипторами синхронизации системы, которые видны в операционной системе и могут использоваться для синхронизации между процессами:

- <xref:System.Threading.Mutex> (.NET Framework и .NET Core);
- <xref:System.Threading.Semaphore> (.NET Framework и .NET Core в Windows);
- <xref:System.Threading.EventWaitHandle> (.NET Framework и .NET Core в Windows).

Дополнительные сведения см. в справочной документации по API <xref:System.Threading.WaitHandle>.

Типы упрощенной синхронизации не основаны на дескрипторах базовой операционной системы и обычно обеспечивают лучшее быстродействие. Тем не менее они не могут использоваться для внутрипроцессной синхронизации. Эти типы можно использовать для синхронизации потоков в одном приложении.

Некоторые из них являются альтернативой типам, производным от <xref:System.Threading.WaitHandle>. Например, <xref:System.Threading.SemaphoreSlim> является упрощенной альтернативой <xref:System.Threading.Semaphore>.

## <a name="synchronization-of-access-to-a-shared-resource"></a>Синхронизация доступа к общему ресурсу

Платформа .NET предоставляет ряд примитивов синхронизации для управления доступом нескольких потоков к общему ресурсу.

### <a name="monitor-class"></a>Monitor класс

Класс <xref:System.Threading.Monitor?displayProperty=nameWithType> предоставляет монопольный доступ к общему ресурсу, блокируя или разблокируя объект, определяющий ресурс. Во время блокировки поток, удерживающий блокировку, может снова поставить и снять блокировку. Любой другой поток не может получить блокировку, и метод <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> ожидает снятия блокировки. Метод <xref:System.Threading.Monitor.Enter%2A> получает снятую блокировку. Можно также использовать метод <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>, чтобы задать количество времени, в течение которого поток пытается получить блокировку. Так как класс <xref:System.Threading.Monitor> реализует привязку потока, поток, который получил блокировку, должен снять ее, вызвав метод <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>.

Можно координировать взаимодействие потоков, которые получают блокировку для одного и того же объекта, с помощью методов <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> и <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType>.

Дополнительные сведения см. в справочной документации по API <xref:System.Threading.Monitor>.

> [!NOTE]
> С помощью операторов [lock](../../csharp/language-reference/keywords/lock-statement.md) в C# и [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md) в Visual Basic можно синхронизировать доступ к общему ресурсу вместо использования класса <xref:System.Threading.Monitor> напрямую. Эти операторы реализуются с помощью методов <xref:System.Threading.Monitor.Enter%2A>, <xref:System.Threading.Monitor.Exit%2A> и блока `try…finally`, обеспечивающих постоянное снятие полученной блокировки.

### <a name="mutex-class"></a>Mutex класс

Класс <xref:System.Threading.Mutex?displayProperty=nameWithType>, как и <xref:System.Threading.Monitor>, предоставляет монопольный доступ к общему ресурсу. С помощью вызова одной из перегрузок метода [Mutex.WaitOne](<xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>) можно запросить владение мьютексом. Как и <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> реализует привязку потока, и поток, который получил мьютекс, должен освободить его, вызвав метод <xref:System.Threading.Mutex.ReleaseMutex%2A?displayProperty=nameWithType>.

В отличие от <xref:System.Threading.Monitor>, класс <xref:System.Threading.Mutex> может использоваться для межпроцессной синхронизации. Для этого нужно использовать именованный мьютекс, который виден в операционной системе. Чтобы создать экземпляр именованного мьютекса, используйте [конструктор Mutex](<xref:System.Threading.Mutex.%23ctor%2A>), который задает имя. Также можно вызвать метод <xref:System.Threading.Mutex.OpenExisting%2A?displayProperty=nameWithType>, чтобы открыть существующий именованный системный мьютекс.
  
Дополнительные сведения см. в статье о [мьютексах](mutexes.md) и справочной документации по API <xref:System.Threading.Mutex>.

### <a name="spinlock-structure"></a>Структура SpinLock

Структура <xref:System.Threading.SpinLock?displayProperty=nameWithType>, как и <xref:System.Threading.Monitor>, предоставляет монопольный доступ к общему ресурсу на основе доступности блокировки. Когда <xref:System.Threading.SpinLock> пытается получить блокировку, которая недоступна, этот примитив будет ожидать в цикле, постоянно проверяя возможность получения блокировки.

Дополнительные сведения о преимуществах и недостатках использования SpinLock см. в статье о [SpinLock](spinlock.md) и справочной документации по API <xref:System.Threading.SpinLock>.

### <a name="readerwriterlockslim-class"></a>Класс ReaderWriterLockSlim

Класс <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType> предоставляет монопольный доступ к общему ресурсу для записи и обеспечивает одновременный доступ к ресурсу для чтения нескольким потокам. Можно использовать <xref:System.Threading.ReaderWriterLockSlim> для синхронизации доступа к общей структуре данных, поддерживающей потокобезопасные операции чтения, но требующей монопольного доступа для выполнения операции записи. Если поток запрашивает монопольный доступ (например, путем вызова метода <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A?displayProperty=nameWithType>), последующие запросы модуля чтения и записи блокируются, пока все существующие модули чтения не освободят блокировку, а модуль записи не получит и не снимет блокировку.
  
Дополнительные сведения см. в справочной документации по API <xref:System.Threading.ReaderWriterLockSlim>.

### <a name="semaphore-and-semaphoreslim-classes"></a>Классы Semaphore и SemaphoreSlim

Классы <xref:System.Threading.Semaphore?displayProperty=nameWithType> и <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> ограничивают число потоков, которые могут одновременно обращаться к ресурсу или пулу ресурсов. Дополнительные потоки, запрашивающие ресурс, ожидают освобождения семафора любым из потоков. Так как семафор не реализует привязку потока, поток может занять семафор, а другой поток может его освободить.

<xref:System.Threading.SemaphoreSlim> — это упрощенная альтернатива <xref:System.Threading.Semaphore>, которую можно использовать для синхронизации в рамках одного процесса.

В Windows можно использовать <xref:System.Threading.Semaphore> для внутрипроцессной синхронизации. Для этого необходимо создать экземпляр <xref:System.Threading.Semaphore>, выполняющий роль именованного системного семафора. Это можно сделать с помощью [конструкторов Semaphore](<xref:System.Threading.Semaphore.%23ctor%2A>), которые задают имя или метод <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>. <xref:System.Threading.SemaphoreSlim> не поддерживает именованные системные семафоры.

Дополнительные сведения см. в статье о [классах Semaphore и SemaphoreSlim](semaphore-and-semaphoreslim.md) и справочной документации по API <xref:System.Threading.Semaphore> или <xref:System.Threading.SemaphoreSlim>.

## <a name="thread-interaction-or-signaling"></a>Взаимодействие потоков или сигнализация

Взаимодействие потоков (или сигнализация потоков) означает, что поток должен ждать уведомления или сигнала от одного или нескольких потоков, чтобы продолжить. Например, если поток A вызывает метод <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> потока B, поток А блокируется до завершения потока B. Примитивы синхронизации, описанные в предыдущем разделе, реализуют другой механизм сигнализации: снятие блокировки потоком является сигналом другому потоку о возможности продолжать исполнение, получив блокировку.

В этом разделе описываются дополнительные сигнальные конструкции, предоставляемые .NET.

### <a name="eventwaithandle-autoresetevent-manualresetevent-and-manualreseteventslim-classes"></a>Классы EventWaitHandle, AutoResetEvent и ManualResetEvent

Класс <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> представляет событие синхронизации потока.

Событие синхронизации может находиться в сигнальном или несигнальном состоянии. Если состояние события несигнальное, поток, который вызывает перегрузку события <xref:System.Threading.WaitHandle.WaitOne%2A?>, будет заблокирован, пока состояние события не станет сигнальным. Метод <xref:System.Threading.EventWaitHandle.Set%2A?displayProperty=nameWithType> задает сигнальное состояние события.

Поведение <xref:System.Threading.EventWaitHandle> после получения сигнала зависит от его режима сброса:

- <xref:System.Threading.EventWaitHandle>, созданный с помощью флага <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType>, автоматически сбрасывается после освобождения одного потока в состоянии ожидания. Это похоже на турникет, пропускающий только один поток каждый раз, когда он переводится в сигнальное состояние. Такое поведение характерно для класса <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>, наследующего <xref:System.Threading.EventWaitHandle>.
- <xref:System.Threading.EventWaitHandle>, созданный с помощью флага <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType>, находится в сигнальном состоянии, пока не будет вызван его метод <xref:System.Threading.EventWaitHandle.Reset%2A>. Это как ворота, которые закрыты до получения сигнала и остающиеся затем открытыми, пока кто-нибудь их не закроет. Такое поведение характерно для класса <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>, наследующего <xref:System.Threading.EventWaitHandle>. Класс <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> является упрощенной альтернативой <xref:System.Threading.ManualResetEvent>.

В Windows можно использовать <xref:System.Threading.EventWaitHandle> для синхронизации между процессами. Для этого необходимо создать экземпляр <xref:System.Threading.EventWaitHandle>, выполняющий роль именованного системного события синхронизации. Это можно сделать с помощью [конструкторов EventWaitHandle](<xref:System.Threading.EventWaitHandle.%23ctor%2A>), которые задают имя или метод <xref:System.Threading.EventWaitHandle.OpenExisting%2A?displayProperty=nameWithType>.

Дополнительные сведения см. в статье о [EventWaitHandle](eventwaithandle.md). Справочные сведения об API см. здесь: <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.AutoResetEvent>, <xref:System.Threading.ManualResetEvent> и <xref:System.Threading.ManualResetEventSlim>.

### <a name="countdownevent-class"></a>Класс CountdownEvent

Класс <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> представляет событие, возникающее, когда его счетчик имеет значение ноль. Когда <xref:System.Threading.CountdownEvent.CurrentCount?displayProperty=nameWithType> не равен нулю, поток, который вызывает <xref:System.Threading.CountdownEvent.Wait%2A?displayProperty=nameWithType>, блокируется. Вызовите <xref:System.Threading.CountdownEvent.Signal%2A?displayProperty=nameWithType>, чтобы уменьшить значение счетчика события.

В отличие от <xref:System.Threading.ManualResetEvent> или <xref:System.Threading.ManualResetEventSlim>, которые позволяют разблокировать несколько потоков с помощью сигнала от одного потока, <xref:System.Threading.CountdownEvent> может разблокировать один или несколько потоков с помощью сигналов от нескольких потоков.

Дополнительные сведения см. в статье о [CountdownEvent](countdownevent.md) и справочной документации по API <xref:System.Threading.CountdownEvent>.

### <a name="barrier-class"></a>Класс Barrier	

Класс <xref:System.Threading.Barrier?displayProperty=nameWithType> представляет барьер выполнения потоков. Поток, который вызывает метод <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType>, сообщает, что он достиг барьера и ожидает, пока другие участвующие потоки не достигнут барьера. Когда все участвующие потоки достигают барьера, их выполнение продолжается, а барьер сбрасывается и может использоваться повторно.

Можно использовать <xref:System.Threading.Barrier>, если одному или нескольким потокам требуются результаты других потоков для перехода к следующему этапу вычисления.

Дополнительные сведения см. в статье о [Barrier](barrier.md) и справочной документации по API <xref:System.Threading.Barrier>.

## <a name="interlocked-class"></a>Interlocked класс

Класс <xref:System.Threading.Interlocked?displayProperty=nameWithType> предоставляет статические методы, которые выполняют простые атомарные операции над переменной. К этим атомарным операциям относится добавление, инкремент и декремент, обмен и условный обмен, зависящий от сравнения, а также операция чтения 64-разрядного целого числа.

Дополнительные сведения см. в справочной документации по API <xref:System.Threading.Interlocked>.

## <a name="spinwait-structure"></a>Структура SpinWait

Структура <xref:System.Threading.SpinWait?displayProperty=nameWithType> обеспечивает поддержку ожидания спин-блокировки. Ее можно использовать, когда потоку нужно дождаться возникновения события или выполнения условия, но фактическое время ожидания будет меньше периода, требуемого для применения дескриптора ожидания или других способов блокировки потока. Используя <xref:System.Threading.SpinWait>, можно задать короткий интервал времени для цикла ожидания, а затем вернуть управление (например, с помощью ожидания или спящего режима), только если условие не было выполнено в течение заданного времени.

Дополнительные сведения см. в статье о [SpinWait](spinwait.md) и справочной документации по API <xref:System.Threading.SpinWait>.

## <a name="see-also"></a>См. также

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Потокобезопасные коллекции](../collections/thread-safe/index.md)
- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
