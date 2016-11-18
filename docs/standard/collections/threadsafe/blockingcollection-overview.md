---
title: "Общие сведения о коллекции BlockingCollection"
description: "Общие сведения о коллекции BlockingCollection"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a1a867de-53c2-49ca-9a1a-e5770a942724
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 64a01b5e21e012dfaae07a02f5fb27932be9cf98

---

# <a name="blockingcollection-overview"></a>Общие сведения о коллекции BlockingCollection

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) — это потокобезопасный класс коллекции, обеспечивающий следующие возможности:

*   реализует шаблон "производитель-получатель";

*   поддерживает параллельное добавление и извлечение элементов несколькими потоками;

*   допускает указание максимальной емкости;

*   поддерживает операции вставки и удаления, блокирующиеся при опустошении или заполнении коллекции;

*   поддерживает условные операции вставки и удалении, не блокирующиеся или блокирующиеся лишь на определенное время;

*   инкапсулирует все типы коллекций, реализующие интерфейс [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1);

*   поддерживает отмену с помощью токенов отмены;

*   поддерживает два вида перечисления с помощью оператора `foreach`: 

    1. перечисление "только для чтения";
    
    2. перечисление, при котором элементы по мере перечисления удаляются.
    
## <a name="bounding-and-blocking-support"></a>Поддержка границ и блокировки 

[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) поддерживает границы и блокировку. Поддержка границ означает возможность задать максимальную емкость коллекции. Границы важны в ряде сценариев, поскольку они позволяют контролировать максимальный размер коллекции в памяти, предотвращая ситуации, в которых потоки-создатели слишком сильно обгоняют потоки-потребители.

Элементы коллекции могут параллельно добавляться из нескольких задач или потоков. Если коллекция достигает максимальной емкости, то потоки-создатели перейдут в состояние блокировки, пока не будет удален хотя бы один элемент. Элементы коллекции могут параллельно удаляться несколькими потребителями. Если коллекция становится пустой, то потоки-потребители перейдут в состояние блокировки, пока поток-создатель не добавит хотя бы один элемент. Поток-создатель может вызвать метод `CompleteAdding`, чтобы указать, что он больше не будет добавлять элементы. Потребители могут отслеживать свойство `IsCompleted`, позволяющее определить, что коллекция опустела, а новые элементы добавляться не будут. В следующем примере демонстрируется простая коллекция `BlockingCollection` с максимальной емкостью в 100 элементов. Задача-создатель добавляет элементы в коллекцию на протяжении всего времени сохранения истинности некоторого внешнего условия, а после этого вызывает метод `CompleteAdding`. Задача-потребитель извлекает элементы, пока свойство `IsCompleted` не примет логическое значение "true".

```csharp
// A bounded collection. It can hold no more 
// than 100 items at once.
BlockingCollection<Data> dataItems = new BlockingCollection<Data>(100);


// A simple blocking consumer with no cancellation.
Task.Run(() => 
{
    while (!dataItems.IsCompleted)
    {

        Data data = null;
        // Blocks if number.Count == 0
        // IOE means that Take() was called on a completed collection.
        // Some other thread can call CompleteAdding after we pass the
        // IsCompleted check but before we call Take. 
        // In this example, we can simply catch the exception since the 
        // loop will break on the next iteration.
        try
        {
            data = dataItems.Take();
        }
        catch (InvalidOperationException) { }

        if (data != null)
        {
            Process(data);
        }
    }
    Console.WriteLine("\r\nNo more items to take.");
});

// A simple blocking producer with no cancellation.
Task.Run(() =>
{
    while (moreItemsToAdd)
    {
        Data data = GetData();
        // Blocks if numbers.Count == dataItems.BoundedCapacity
        dataItems.Add(data);
    }
    // Let consumer know we are done.
    dataItems.CompleteAdding();
});
```

Полный пример см. в разделе [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](how-to-add-and-take-items.md).

## <a name="timed-blocking-operations"></a>Операции с временной блокировкой

При использовании операций `TryAdd` и `TryTake` ограниченных коллекций, использующих временную блокировку, метод предпринимает попытку добавления или удаления элемента. Если элемент доступен, то он заносится в указанную по ссылке переменную, после чего метод возвращает значение "`true`". Если по прошествии определенного времени ожидания элемент так и не удается извлечь, метод возвращает значение "`false`". После этого поток может перейти к другой полезной работе, прежде чем повторить попытку обращения к коллекции. Пример доступа с временной блокировкой см. во втором примере из раздела [Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](how-to-add-and-take-items.md).

## <a name="cancelling-add-and-take-operations"></a>Отмена операций Add и Take

Операции Add и Take обычно выполняются в цикле. Отменить цикл можно, передав в метод `TryAdd` или `TryTake` токен `CancellationToken` и проверяя значение его свойства `IsCancellationRequested` на каждой итерации. Если значение "`true`", то разработчик может обработать запрос отмены, освободив ресурсы и завершив цикл. В следующем примере показана перегрузка метода `TryAdd`, которая принимает токен отмены, а также код, использующий эту перегрузку:

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="specifying-the-collection-type"></a>Указание типа коллекции

При создании класса `BlockingCollection<T>;` можно указать не только ограничиваемую емкость, но и тип используемой коллекции. Например, можно задать тип [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) для использования принципа "первым поступил — первым обслужен", или [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) для использования принципа "последним поступил — первым обслужен". Использовать можно любой класс коллекции, реализующий интерфейс [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1). Тип коллекции, используемый в классе `BlockingCollection<T>` по умолчанию — это `ConcurrentQueue<T>`. В следующем примере кода показывается, как создать строковую коллекцию `BlockingCollection<T>` емкостью в 1000 элементов, которая использует класс [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1):

```csharp
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );
```

## <a name="ienumerable-support"></a>Поддержка интерфейса IEnumerable

`BlockingCollection<T>` предоставляет метод `GetConsumingEnumerable`, позволяющий потребителям использовать оператор `foreach` для удаления элементов коллекции до тех пор, пока коллекция не будет исчерпана (состояния, в котором коллекция пуста и новые элементы не будут добавляться). Дополнительные сведения см. в разделе [Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](how-to-use-foreach-to-remove.md).

## <a name="using-many-blockingcollections-as-one"></a>Использование нескольких коллекций BlockingCollection в качестве одной коллекции

В сценариях, где потребителю необходимо одновременно извлекать элементы из нескольких коллекций, можно создавать массивы `BlockingCollection<T>` и использовать такие статические методы, как `TakeFromAny` и `AddToAny`, позволяющие добавлять и извлекать элементы любой коллекции в массиве. Если одна из коллекций заблокирована, метод немедленно переходит к другой, пока не найдет коллекцию, способную выполнить операцию. Дополнительные сведения см. в разделе [Практическое руководство. Использование массивов для блокировки коллекций в конвейере](how-to-use-arrays-of-blockingcollections.md).

## <a name="see-also"></a>См. также

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Коллекции и структуры данных](../index.md)

[Потокобезопасные коллекции](index.md)




<!--HONumber=Nov16_HO3-->


