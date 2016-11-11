---
title: "Потокобезопасные коллекции"
description: "Потокобезопасные коллекции"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 92d5515d-f5d6-4a09-8bbb-31865d678643
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 421d46585b5d83f5772fa6596ad581c8c6acbf71

---

# <a name="threadsafe-collections"></a>Потокобезопасные коллекции

Пространство имен [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) содержит несколько классов коллекций, которые являются потокобезопасными и масштабируемыми. Несколько потоков могут безопасно и эффективно добавлять и удалять элементы из таких коллекций, не требуя при этом дополнительной синхронизации в пользовательском коде. При написании нового кода следует использовать классы параллельных коллекций каждый раз, когда коллекция будет записывать одновременно для нескольких потоков. Если выполняется только чтение из общей коллекции, можно использовать классы в пространстве имен [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic). Не рекомендуется использовать классы коллекций [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections), если в качестве целевой среды выполнения не требуется платформа .NET Framework версии 1.1 или более ранней версии.

## <a name="finegrained-locking-and-lockfree-mechanisms"></a>Механизм блокировки мелких фрагментов данных и механизм, свободный от блокировки

Отдельные из типов параллельных коллекций используют механизмы упрощенной синхронизации, например [SpinLock](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinLock), [SpinWait](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinWait), [SemaphoreSlim](https://docs.microsoft.com/dotnet/core/api/System.Threading.SemaphoreSlim) и [CountdownEvent](https://docs.microsoft.com/dotnet/core/api/System.Threading.CountdownEvent). Эти типы синхронизации обычно используют цикличную работу для коротких промежутков перед помещением потока в фактическое состояние `Wait`. При условии, что время ожидания предполагается очень коротким, цикличность требует значительно меньших затрат компьютерных ресурсов, чем ожидание, которое включает в себя переход в режим ядра, требующий больших затрат компьютерных ресурсов. Для классов коллекций, которые используют цикличность, эта эффективность означает, что множество потоков могут добавлять и удалять большое количество элементов.

Классы [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) и [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) вообще не используют блокировки. Вместо этого для достижения потокобезопасности они используют операции Interlocked.

> [!NOTE]
> Так как классы параллельных коллекций поддерживают интерфейс [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection), они предоставляют реализации для свойств `IsSynchronized` и `SyncRoot`, даже если эти свойства не имеют значения. `IsSynchronized` всегда возвращает значение `false`, а свойство `SyncRoot` всегда имеет значение NULL.

В следующей таблице перечислены типы коллекций в пространстве имен [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent).

Тип | Описание
---- | -----------
[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) | Предоставляет возможности блокировки и ограничения для всех типов, которые реализуют интерфейс [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1). Дополнительные сведения см. в разделе [Общие сведения о коллекции BlockingCollection](blockingcollection-overview.md).
[ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) | Потокобезопасная реализация неупорядоченной коллекции элементов.
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) | Потокобезопасная реализация словаря пар "ключ-значение".
[ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) | Потокобезопасная реализация очереди с типом "первым поступил — первым обслужен" (FIFO).
[ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) | Потокобезопасная реализация стека с типом "последним поступил — первым обслужен" (LIFO).
[IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) | Это интерфейс, тип которого должен быть реализован для использования в классе `BlockingCollection`.

## <a name="thread-synchronization-in-the-net-framework-version-10-and-20-collections"></a>Синхронизация потоков в пространстве имен Collections на платформах .NET Framework версий 1.0 и 2.0

Доступные на платформе .NET Framework 1.0 коллекции находятся в пространстве имен [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections). Эти коллекции, которые содержат часто используемые класс [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) и класс [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable), предоставляют некоторую потокобезопасность посредством свойства `Synchronized`, которое возвращает потокобезопасную программу-оболочку вокруг коллекции. Работа программы оболочки заключается в блокировке всей коллекции при каждой операции добавления или удаления. Поэтому каждый поток, который пытается получить доступ к коллекции, должен ждать своей очереди для получения блокировки. Такой подход не является масштабируемым и может привести к значительному снижению производительности для больших коллекций. Также такой подход не защищен полностью от состояния гонки. 

Доступные на платформе .NET Framework 2.0 классы коллекций находятся в пространстве имен [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic). Они включают классы [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) и так далее. Эти классы предоставляют улучшенную безопасность типа и производительность по сравнению с классами `System.Collections`. Однако классы коллекций `System.Collections.Generic` не обеспечивают синхронизацию потоков. Пользовательский код должен обеспечивать всю синхронизацию при параллельном добавлении элементов в несколько потоков или удалении элементов из них.

Рекомендуются классы параллельных коллекций `System.Collections.Concurrent`, так как они предоставляют не только безопасность типа классов коллекций `System.Collections.Generic`, но и большую эффективность, более полную потокобезопасность по сравнению с коллекциями `System.Collections`.

## <a name="related-topics"></a>Связанные разделы

Заголовок | Описание
----- | -----------
[Общие сведения о коллекции BlockingCollection](blockingcollection-overview.md) | Приводится описание функциональных возможностей, которые предоставляются типом `BlockingCollection<T>`.
[Преимущества использования потокобезопасных коллекций](when-to-use-a-thread-safe-collection.md) | Приводится описание ситуаций, когда лучше всего использовать потокобезопасную коллекцию.
[Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из нее](how-to-add-and-remove-items.md) | Приводится описание порядка добавления и удаления элементов из класса `ConcurrentDictionary<TKey, TValue>`.
[Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](how-to-add-and-take-items.md) | Приводится описание порядка добавления и получения элементов из заблокированной коллекции без использования перечислителя, доступного только для чтения.
[Практическое руководство. Добавление функций границы и блокировки в коллекцию](how-to-add-bounding-and-blocking.md ) | Приводится описание порядка использования всех классов коллекций в качестве базового механизма хранения для коллекции `IProducerConsumerCollection<T>;`.
[Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](how-to-use-foreach-to-remove.md ) | Приводится описание порядка использования оператора `foreach` для удаления всех элементов в заблокированной коллекции.
[Практическое руководство. Использование массивов для блокировки коллекций в конвейере](how-to-use-arrays-of-blockingcollections.md) | Приводится описание порядка одновременного использования нескольких заблокированных коллекций для реализации конвейера.
[Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag](how-to-create-an-object-pool.md) | Показано, как применить параллельный контейнер для повышения производительности в сценариях, где можно повторно использовать объекты вместо постоянного создания новых.

## <a name="reference"></a>Ссылка

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)






 





<!--HONumber=Nov16_HO1-->


